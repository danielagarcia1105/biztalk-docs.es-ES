---
title: "Cómo volver a implementar un ensamblado de BizTalk desde Visual Studio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c4bb627-48de-4874-bb25-af2c513dbc51
caps.latest.revision: "41"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 361d2bccc783e7bfc7aa6cb0cd1f3eab51d8e640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-redeploy-a-biztalk-assembly-from-visual-studio"></a>Cómo volver a implementar un ensamblado de BizTalk desde Visual Studio
Durante el desarrollo de un ensamblado, suele resultar necesario implementarlo, probarlo, modificarlo y volver a implementarlo varias veces. En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], si se quería volver a implementar un ensamblado sin cambiar el número de versión, primero había que detener, dar de baja y desenlazar manualmente los artefactos incluidos en el ensamblado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y, a continuación, quitar el ensamblado de la base de datos (de configuración) de Administración de BizTalk. Además, después de volver a implementar el ensamblado, había que enlazar, dar de alta e iniciar sus artefactos en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Sin embargo, con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], al activar la opción Volver a implementar en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleva a cabo automáticamente todos los pasos necesarios para volver a implementar el ensamblado. Aunque se pueda volver a implementar un ensamblado desde el nivel de proyecto (haciendo clic con el botón secundario en el proyecto en el Explorador de soluciones y haciendo clic en Implementar) para volver a implementar un ensamblado individual, recomendamos encarecidamente que siempre se vuelvan a implementar los ensamblados desde el nivel de solución (haciendo clic con el botón secundario en la solución y haciendo clic en Implementar). De este modo, se vuelven a implementar todos los ensamblados de la solución al mismo tiempo y se controlan todos los pasos implicados cuando existen dependencias, como se explica más adelante.  
  
> [!IMPORTANT]
>  Aunque hay pocas situaciones en las que sería necesario volver a implementar en el nivel de proyecto, como norma, siempre se debe volver implementar en el nivel de solución.  
  
 Al volver a implementar un ensamblado, tenga en cuenta los siguientes puntos importantes:  
  
-   **Debe instalar al nuevo ensamblado en la GAC.** Al implementar un ensamblado, siempre debe instalar la nueva versión del ensamblado en la GAC, como se describe en [cómo instalar un ensamblado en la GAC](../core/how-to-install-an-assembly-in-the-gac.md). Puede hacerlo una vez que lo ha vuelto a implementar.  
  
-   **Siempre debe implementar en el nivel de solución cuando existen dependencias.** Si una solución cuenta con varios ensamblados y uno o varios tienen una dependencia en el ensamblado que desea volver a implantar, debe volver a implantar los ensamblados en el nivel de solución. Ello se debe a que, al volver a implementar un ensamblado en el nivel de proyecto, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] detendrá, dará de baja, desenlazará y quitará los artefactos en todos los ensamblados que dependan de este ensamblado o de los que éste dependa. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no llevará a cabo los pasos adicionales para implementar, enlazar, dar de alta e iniciar los artefactos. Sin embargo, al volver a implementar la solución completa, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lleva a cabo automáticamente todos los pasos necesarios para anular la implementación y volver a implementar todos los artefactos en la solución según sus dependencias.  
  
-   **Debe volver a implementar manualmente los ensamblados dependientes.** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] siempre anula la implementación de ensamblados dependientes, pero en los casos siguientes, deberá llevar a cabo los pasos adicionales para implementar, enlazar y dar de alta los artefactos en cada ensamblado dependiente después de volver a implementar el ensamblado del que éste depende:  
  
    -   Si vuelve a implementar un ensamblado en el nivel de proyecto y otro ensamblado de la misma solución depende de él.  
  
    -   Si vuelve a implementar un ensamblado en el nivel de solución, pero existe un ensamblado dependiente en una solución diferente.  
  
     Por ejemplo, si volviera a implementar sólo el Ensamblado 3 que se muestra en el diagrama siguiente, siguiendo la nueva implementación debería implementar, enlazar y dar de alta los artefactos del Ensamblado 2 y, a continuación, hacer lo mismo con los artefactos del Ensamblado 1.  
  
     ![Ensamblados con dependencias](../core/media/assemblydependencies.gif "AssemblyDependencies")  
  
     Un enfoque alternativo es evitar la implementación innecesaria de los ensamblados principales que no han cambiado.  Por ejemplo, en el diagrama anterior, si hay otros ensamblados que dependen de Ensamblado 2 y Ensamblado 3, y ninguno de ellos se ha actualizado.  Desactive el **implementar** opción en el Administrador de configuración de ensamblado 2 y los proyectos de ensamblado 3. De esta forma, no se anulará la implementación de los ensamblados externos que dependen de ellos, lo que requeriría una nueva implementación. Para obtener más información, consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).  
  
-   **Debe reiniciar instancias de host.** Al volver a implementar un ensamblado que contiene una orquestación sin cambiar el número de versión del ensamblado, el ensamblado existente se sobrescribe en la base de datos de Administración de BizTalk. Sin embargo, antes de que el cambio se haga efectivo, deberá reiniciar cada instancia de host correspondiente al host al que está enlazada la orquestación. Puede especificar la opción para que todas las instancias de host del equipo local se reinicien automáticamente al volver a implementar un ensamblado. Para obtener instrucciones, consulte [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). También manualmente puede detener e iniciar cada instancia de host, como se describe en [cómo detener una instancia de Host](../core/how-to-stop-a-host-instance.md) y [cómo iniciar una instancia de Host](../core/how-to-start-a-host-instance.md).  
  
> [!IMPORTANT]
>  Puesto que la opción Volver a implementar omite el control de la versión, recomendamos que la utilice únicamente durante el desarrollo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo el procedimiento de este tema, debe haber iniciado sesión con una cuenta que sea miembro de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. Además, la cuenta debe tener permisos de lectura y escritura en el sistema de archivos local y en la caché de ensamblados global (GAC). La cuenta de administradores del equipo local tiene estos permisos.  
  
## <a name="to-redeploy-a-biztalk-solution"></a>Para volver a implementar una solución de BizTalk  
  
#### <a name="using-visual-studio-solution-explorer"></a>Mediante el Explorador de soluciones de Visual Studio  
  
1.  Asegúrese de que está habilitada la opción de volver a implementar en las propiedades de implementación para cada proyecto de la solución, como se describe en [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). Esta opción está habilitada de forma predeterminada.  
  
2.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en una solución de BizTalk y, a continuación, haga clic en **implementar**.  
  
     Los ensamblados de la solución se implementan en la aplicación de BizTalk especificada. El estado del proceso de generación e implementación se muestra en la esquina inferior izquierda de la página.  
  
#### <a name="using-the-visual-studio-command-prompt"></a>Mediante el símbolo del sistema de Visual Studio  
  
1.  Asegúrese de que está habilitada la opción de volver a implementar en las propiedades de implementación para cada proyecto de la solución, como se describe en [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md). Esta opción está habilitada de forma predeterminada.  
  
2.  Iniciar **símbolo del sistema de Visual Studio**.  
  
3.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **Devenv / deploy***Nombreconfigsolución* *nombresolución*   
  
     Ejemplo:  
  
     **Devenv /Deploy Release "C:\Documents and settings\someuser\mis documentos\Visual Studio\Projects\MySolution\MySolution.sln"**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ deploy**|Implementa una solución después de una creación o una nueva creación.|  
    |*Nombreconfigsolución*|Nombre de la configuración de la solución que se utilizará para generar la solución nombrada en NombreSolución.|  
    |*SolutionName*|Ruta completa y nombre del archivo de solución.|  
  
## <a name="see-also"></a>Vea también  
 [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)