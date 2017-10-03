---
title: "Implementación de aplicaciones y herramientas de administración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de85b52b-7eb7-4cf1-b8b4-41f7488b4d2f
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3dede31c82d79ac6c40ae087dfffb7f30c2402c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="application-deployment-and-management-tools"></a>Herramientas de implementación y administración de aplicaciones

## <a name="overview"></a>Información general
Este tema describe brevemente las herramientas que puede usar para implementar y administrar una aplicación de BizTalk, y a continuación resume las operaciones que puede realizar con cada herramienta. Al final del tema encontrará una tabla con un resumen de las tareas que puede realizar mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y BTSTask.  
  
-   **Consola de administración de BizTalk Server.** El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, una consola de administración de Microsoft (MMC), es la herramienta de administración principal para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Proporciona una interfaz de usuario gráfica para realizar todas las operaciones de implementación y administración de una aplicación de BizTalk. Por ejemplo, desde la consola de administración puede iniciar los asistentes para importación, instalación y exportación, así como agregar y quitar artefactos de una aplicación y realizar otras modificaciones en la aplicación.  
  
     También puede generar archivos .msi de BizTalk para sus aplicaciones de BizTalk a través del Asistente para exportación de archivos MSI o BTSTask, que se describe a continuación. A continuación puede instalar la aplicación en un equipo desde el archivo .msi o importarla desde el archivo .msi a otro grupo de BizTalk. Para obtener más información acerca de la consola de administración, consulte [mediante la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md).  
  
-   **Herramienta de línea de comandos BTSTask.** BTSTask permite realizar muchas tareas de administración de la aplicación desde la línea de comandos. Para obtener más información sobre el uso de BTSTask, vea [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md).  
  
-   **API de programación y secuencias de comandos**. Puede usar el Instrumental de administración de Microsoft Windows (WMI) para crear y ejecutar scripts que automaticen las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
-   **Visual Studio.** El programador puede crear ensamblados de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y use el comando implementar para implementarlos automáticamente en una aplicación de BizTalk. Para obtener más información, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
     .  
  
    > [!IMPORTANT]
    >  Nunca se debe implementar un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] que se ejecute en un equipo de producción. Puede interferir con las aplicaciones en ejecución. Para obtener más información, consulte [prácticas recomendadas para implementar una aplicación de BizTalk](../core/best-practices-for-deploying-a-biztalk-application.md).  

## <a name="tool-by-the-task"></a>Herramienta de la tarea  
 La siguiente tabla resume las tareas que puede realizar mediante la consola de administración y BTSTask.  
  
|Tarea|Herramienta|  
|----------|----------|  
|Exportar un archivo .msi de aplicación|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Consola de administración <br/>: Exporta el Asistente para archivos MSI<br />-BTSTask|  
|Importar un archivo .msi de aplicación|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Consola de administración <br/>: Asistente para importación de MSI<br />-BTSTask|  
|Crear o eliminar una aplicación|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Consola de administración<br />-BTSTask|  
|Instalar una aplicación|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <br/>: Asistente para la instalación (o haga doble clic en el archivo .msi de aplicación)|  
|Desinstalar una aplicación|BTSTask (o use el panel de control Agregar o quitar programas)|  
|Agregar artefactos a una aplicación o quitar artefactos de una aplicación|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Consola de administración<br />-BTSTask|  
|Importar y exportar enlaces |-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Consola de administración<br />-BTSTask|  
|Importar y exportar directivas|-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Consola de administración<br />-BTSTask|  
|Iniciar y detener una aplicación|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Cambiar el estado de un artefacto: iniciar, detener, habilitar, deshabilitar, dar de alta y dar de baja|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Editar las propiedades de un artefacto|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Crear un puerto de envío, un grupo de puertos de envío, una ubicación de recepción o un puerto de recepción|Consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
  
## <a name="see-also"></a>Vea también  
[Herramientas de administración y rendimiento](../core/administration-tools.md)  
 [Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)