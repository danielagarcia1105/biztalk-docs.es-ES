---
title: "Cómo implementar un ensamblado de BizTalk desde Visual Studio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69d70c52-3e71-4eb2-876e-b467c7ca24b7
caps.latest.revision: "39"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07810f513c3530b214eb1405462db1e6ac96ed84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-a-biztalk-assembly-from-visual-studio"></a>Cómo implementar un ensamblado de BizTalk desde Visual Studio
En este tema se proporcionan instrucciones sobre el uso del Explorador de soluciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] o el símbolo del sistema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para implementar los ensamblados de BizTalk desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en una aplicación de BizTalk. Aunque se pueda implementar un solo ensamblado desde el nivel de proyecto (haciendo clic con el botón secundario en el proyecto y haciendo clic en Implementar) o implementar todos los ensamblados en la solución al mismo tiempo desde el nivel de solución (haciendo clic con el botón secundario en la solución y haciendo clic en Implementar), recomendamos encarecidamente que se implementen todos al mismo tiempo desde el nivel de solución.  
  
 En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], si se querían implementar varios ensamblados en una solución y alguno de ellos tenía una dependencia en cualquiera de los demás ensamblados, había que implementar individualmente los ensamblados en orden inverso a sus dependencias. Por ejemplo, si Ensamblado1 tenía una dependencia en Ensamblado2, había que implementar primero el Ensamblado 2 y, a continuación, el Ensamblado1.  
  
 Esto sigue siendo así al implementar ensamblados desde el nivel de proyecto. Sin embargo, con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], al implementar ensamblados desde el nivel de solución y no desde el nivel de proyecto, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se ocupa automáticamente de todos los pasos de la implementación, incluida la implementación de los ensamblados en el orden correcto. Por lo tanto, para simplificar la implementación, cuando otro ensamblado tenga una dependencia en el ensamblado que se esté implementando, se deberán implementar los ensamblados en el nivel de solución.  
  
 Al seleccionar la opción para implementar un proyecto o una solución desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], el ensamblado o ensamblados se crean e implementan automáticamente en la aplicación de BizTalk especificada en el grupo local de BizTalk. Si la aplicación aún no existe en el grupo, la implementación también crea la aplicación. Los ensamblados y los artefactos que contienen se registran y sus datos se guardan en la base de datos de administración (de configuración) de BizTalk correspondiente al grupo de BizTalk. Además, si se especifica esta opción en las propiedades de implementación del proyecto, los ensamblados se agregan a la caché de ensamblados global (GAC).  
  
 Un "artefacto" es cualquier elemento de una aplicación de BizTalk, incluidos los recursos con los que se trabaja en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tales como ensamblados y orquestaciones, así como otros elementos que se crean o se agregan posteriormente después de implementar la aplicación, tales como puertos de envío y recepción, certificados y scripts. Una vez implementado el ensamblado, se pueden ver y administrar sus artefactos en el nodo Aplicaciones de la consola de administración de [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]. Cada aplicación se almacena en su propia carpeta, con subcarpetas que muestran los artefactos de la aplicación. Para obtener más información, consulte [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md). Para obtener más información sobre cómo crear y administrar aplicaciones, consulte [implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md).  
  
 Antes de implementar un ensamblado, hay que llevar a cabo los pasos siguientes:  
  
-   Crear un archivo de clave de ensamblado de nombre seguro y lo ha asignado a cada proyecto, como se describe en [cómo configurar un archivo de clave de ensamblado de nombre seguro](../core/how-to-configure-a-strong-name-assembly-key-file.md).  
  
-   Establezca las propiedades de implementación para el proyecto, como se describe en [cómo establecer propiedades de implementación en Visual Studio](../core/how-to-set-deployment-properties-in-visual-studio.md).  
  
-   Si se ha implementado anteriormente el ensamblado, habilitar la opción de nueva implementación para el proyecto. Para obtener instrucciones y otra información importante acerca de la reimplementación, vea [cómo volver a implementar un ensamblado de BizTalk desde Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md).  
  
> [!IMPORTANT]
>  No se deben realizar las tareas que se describen en este tema en un equipo de producción. Durante el proceso de desarrollo, el programador suele volver a implementar ensamblados de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para que ello sea posible, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] puede anular la implementación artefactos que existan en la misma aplicación o en aplicaciones distintas, y desenlazarlos, detenerlos y darlos de baja. Aunque esto resulta necesario y apropiado en un entorno de desarrollo, puede producir consecuencias inesperadas no deseadas en un entorno de producción. Además, para evitar la posibilidad de que alguien intente implementar un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en un equipo de producción, se recomienda que no instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en un equipo de producción.  
  
> [!NOTE]
>   La directiva de seguridad en tiempo de ejecución de .NET Framework impide de forma predeterminada la implementación de ensamblados desde un recurso compartido de red. Si intenta implementar un ensamblado desde un recurso compartido de red y experimenta dificultades, consulte al administrador de seguridad de .NET Framework o vea la sección sobre administración de directivas de seguridad en la colección combinada de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos de este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. If, en **implementación** propiedades, se ha habilitado la opción instalar un ensamblado en la caché global de ensamblados (GAC), a continuación, también necesitará permisos de lectura/escritura en la GAC. La cuenta de administradores del equipo local cuenta con este permiso. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
## <a name="to-deploy-a-biztalk-assembly-or-assemblies"></a>Para implementar un ensamblado o ensamblados de BizTalk  
  
#### <a name="using-visual-studio-solution-explorer"></a>Mediante el Explorador de soluciones de Visual Studio  
  
-   En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en un proyecto de BizTalk o la solución y, a continuación, haga clic en **implementar**.  
  
     El ensamblado del proyecto o los ensamblados de la solución se implementan en la aplicación de BizTalk especificada. El estado del proceso de generación e implementación se muestra en la esquina inferior izquierda de la página.  
  
#### <a name="using-the-visual-studio-command-prompt"></a>Mediante el símbolo del sistema de Visual Studio  
  
1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
2.  Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:  
  
     **Devenv / deploy***Nombreconfigsolución* *nombresolución* [**/proyecto** *Nombre_proyecto*] [**/ projectconfig** *Nombreconfigproyecto*]    
  
     Ejemplo:  
  
     **Devenv / implementar Release "C:\Documents and settings\someuser\mis documentos\Visual Studio\Projects\MySolution\MySolution.sln" / "MyBizTalkApp\MyBizTalkApp.csproj" projectconfig versión del proyecto**  
  
    |Parámetro|Valor|  
    |---------------|-----------|  
    |**/ deploy**|Implementa una solución después de una creación o una nueva creación.|  
    |*Nombreconfigsolución*|Nombre de la configuración de la solución que se utilizará para generar la solución nombrada en NombreSolución.|  
    |*SolutionName*|Ruta completa y nombre del archivo de solución.|  
    |**/ proyecto***Nombre_proyecto* |Ruta y nombre del archivo del proyecto dentro de la solución. Puede especificar una ruta relativa desde la carpeta NombreSolución al archivo del proyecto, el nombre para mostrar del proyecto o la ruta completa y el nombre del archivo del proyecto.|  
    |**/projectconfig***Nombreconfigproyecto* |Nombre de la configuración de generación de un proyecto que se va a utilizar al generar el proyecto.|  
  
     Es posible que la primera vez que implemente un ensamblado que contenga una orquestación reciba un mensaje de advertencia que le indique que el archivo de enlace no contiene la orquestación. Ello se debe a que las orquestaciones no se enlazan automáticamente al host en el momento de la implementación. Deberá realizar este paso manualmente.  
  
## <a name="see-also"></a>Vea también  
 [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)