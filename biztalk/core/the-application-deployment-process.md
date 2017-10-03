---
title: "El proceso de implementación de aplicaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, deploying
- deploying [applications], how to
ms.assetid: 29486c37-6aa7-46fd-a457-916fd235f448
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd88dbb730b31362042e68b3a25c4ccc66531882
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-application-deployment-process"></a>Proceso de implementación de aplicaciones
El siguiente diagrama muestra los pasos generales implicados en la implementación de una aplicación de BizTalk. Para obtener información detallada acerca de las tareas implicadas durante las fases de desarrollo, prueba, ensayo y producción de implementación de aplicaciones, consulte [tareas de implementación de aplicación](../core/application-deployment-tasks.md).  
  
 ![Proceso de implementación de aplicación](../core/media/appdeploymentprocess.gif "AppDeploymentProcess")  
  
1.  **Implementar desde Visual Studio los ensamblados en una solución de BizTalk.** En este paso se crean los ensamblados y se importan, junto con las orquestaciones, las canalizaciones, los esquemas y las asignaciones que contienen (denominados "artefactos") a la base de datos de administración de BizTalk local. La implementación también los asocia a la aplicación de BizTalk que ha especificado en las propiedades del proyecto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para obtener instrucciones, consulte [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md). Después de implementar una solución, puede ver y administrar los ensamblados implementados y sus artefactos desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o mediante la herramienta de la línea de comandos BTSTask. Los artefactos se pueden administrar de forma individual o juntos, agrupados en la aplicación.  
  
2.  **Agregar y configurar artefactos.** Puede agregar artefactos, como scripts y archivos Léame, a la aplicación mediante la consola de administración o BTSTask. También puede configurar artefactos, como los puertos de envío y recepción, las ubicaciones de recepción y las orquestaciones mediante la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [cómo crear o agregar un artefacto](../core/how-to-create-or-add-an-artifact.md). Consulte también [administrar artefactos](../core/managing-artifacts.md). También puede generar archivos de enlace y agregarlos a la aplicación si desea aplicar diferentes enlaces a diferentes entornos en los que podría importar la aplicación. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
3.  **Exportar la aplicación a un archivo MSI.** Puede usar el Asistente para exportar archivos MSI o la herramienta BTSTask para exportar los artefactos de la aplicación a un archivo .msi que se usará para importar la aplicación a un nuevo grupo de BizTalk, así como para instalar la aplicación en los equipos donde se ejecutará. Para obtener instrucciones, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
4.  **Importar la aplicación a otro grupo de BizTalk e instale la aplicación en los equipos que vayan a ejecutarla.** Puede usar el Asistente para importación de MSI o la herramienta BTSTask para importar la aplicación de BizTalk desde el archivo .msi, creado en el Paso 3, a otro grupo de BizTalk con el fin de crear la aplicación y sus artefactos en el nuevo grupo. A continuación, use el archivo .msi para instalar la aplicación en los equipos que la ejecutarán. Esto se debe realizar antes de ejecutar la aplicación. Si ya desea realizar pruebas en la aplicación, puede importarla a un grupo de BizTalk en un entorno de prueba e instalarla. Si la aplicación ya está preparada para realizar los ensayos o la producción, puede importarla a uno de estos entornos e instalarla. Para obtener instrucciones, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Consulte también [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
5.  **Inicie la aplicación y comprobar que funciona correctamente.** Puede iniciar la aplicación desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, como se describe en [cómo iniciar y detener una aplicación de BizTalk](../core/how-to-start-and-stop-a-biztalk-application.md). A continuación, puede probar la aplicación, como se describe en [tareas de prueba para la implementación de aplicación de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación de aplicaciones de BizTalk y administración](../core/understanding-biztalk-application-deployment-and-management.md)   
 [¿Qué es una aplicación de BizTalk?](../core/what-is-a-biztalk-application.md)