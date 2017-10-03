---
title: "Cómo establecer propiedades de implementación en Visual Studio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2c6752e-c50d-4dd0-ac07-bf36ca10559c
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 079167f7607f434e48e29e90029468cd952c5620
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-deployment-properties-in-visual-studio"></a>Cómo establecer propiedades de implementación en Visual Studio
Para poder implementar una solución de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en una aplicación de BizTalk, primero debe establecer propiedades del proyecto. Si una solución de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] contiene varios proyectos, debe configurar por separado las propiedades para cada proyecto.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar los procedimientos de este tema, deberá iniciar sesión con una cuenta que tenga permisos de lectura y escritura en el sistema de archivos local. La cuenta de administradores del equipo local cuenta con este permiso.  
  
### <a name="to-enable-project-deployment-in-configuration-manager"></a>Procedimiento para habilitar la implementación del proyecto en el Administrador de configuración  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] haga clic en **generar** en el menú principal, a continuación, haga clic en **Configuration Manager**.  
  
2.  Compruebe el **implementar** opción para cada proyecto que necesite implementarse desde la solución abierta.  
  
### <a name="to-configure-project-properties"></a>Para configurar las propiedades del proyecto  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] el Explorador de soluciones, haga clic en un proyecto para el que desea configurar las propiedades y, a continuación, haga clic en **propiedades**.  
  
2.  Haga clic en el **implementación** ficha en el Diseñador de proyectos.  
  
3.  Configurar propiedades del proyecto, como se describe en la tabla siguiente y, a continuación, haga clic en **Aceptar**.  
  
4.  Repita los pasos 1, 2 y 3 para cada proyecto de la solución.  
  
    |Propiedad|Valor|Explicación|  
    |--------------|-----------|-----------------|  
    |Application Name|\<Name>|Nombre de la aplicación de BizTalk en la que se van a implementar los ensamblados de este proyecto. Si la aplicación ya existe, los ensamblados se agregarán a ella cuando implemente el proyecto. En cambio, si no existe, se creará la aplicación. Si se deja este campo en blanco, los ensamblados se implementarán en la aplicación de BizTalk predeterminada en el grupo actual. Los nombres que incluyen espacios deben flanquearse con comillas dobles (").|  
    |Base de datos de configuración|\<Nombre de la base de datos de administración de BizTalk >|Nombre de la base de datos de administración de BizTalk del grupo; el nombre predeterminado es BizTalkMgmtDb.|  
    |Server|\<Nombre del servidor >|Nombre de la instancia del servidor SQL Server que aloja la base de datos de administración de BizTalk en el equipo local. En las instalaciones de un solo equipo, suele ser el nombre del equipo local. **Nota:** si mueve este proyecto de BizTalk a otro equipo, probablemente necesitará modificar la propiedad del servidor para reflejar el nuevo nombre del equipo antes de poder implementar el ensamblado.|  
    |Volver a implementar|True o False|Si se define en True (valor predeterminado), puede volver a implementar los ensamblados de BizTalk sin cambiar el número de versión.|  
    |Instalar caché de ensamblados total (GAC)|True o False|Si se define en True (valor predeterminado), los ensamblados se instalan en la caché de ensamblados global (GAC) del equipo local al instalar la aplicación. Establézcalo en False solo si tiene intención de usar otras herramientas en esta instalación, como gacutil.|  
    |Reiniciar instancias de host|True o False|Si se define en True, se reinician de forma automática todas las instancias de host que se ejecutan en el equipo local cuando el ensamblado se vuelve a implementar. En cambio, si se define en False (valor predeterminado), debe reiniciar manualmente las instancias de host al volver a implementar un ensamblado. **Nota:** si está volviendo a implementar ensamblados desde el nivel de solución, instancias de host se reiniciará una vez para cada proyecto que tenga esta opción se establece en True. Esto puede ocasionar varios reinicios. Si tiene intención de volver a implementar desde el nivel de solución, se recomienda establecer esta propiedad en True en solo un proyecto de la solución para evitar que la instancia de host se reinicie varias veces. Esto debe establecerse en el último proyecto que se vaya a volver a implementar en la solución. Además, si se detiene una instancia de host cuando esté llevando a cabo la nueva implementación, no se iniciará.|  
    |Habilitar pruebas de unidades|True o False|Especifica si se deben habilitar las pruebas de unidades para el proyecto.|  
  
## <a name="see-also"></a>Vea también  
 [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)