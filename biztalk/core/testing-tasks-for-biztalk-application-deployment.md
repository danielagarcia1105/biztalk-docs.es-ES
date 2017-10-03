---
title: "Tareas de prueba para la implementación de aplicación de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying [applications], testing
- testing, deploying
- testing, tasks
ms.assetid: fb043755-6d01-4ceb-b189-5a5f286c2b37
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfd4385c4de076c8c89b409177204ee8fce5548b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="testing-tasks-for-biztalk-application-deployment"></a>Tareas de prueba para la implementación de una aplicación de BizTalk
A continuación se explican los pasos necesarios para implementar los artefactos de una aplicación de BizTalk en un entorno de prueba a fines de realización de pruebas y depuración.  
  
1.  **Copie el archivo .msi en el entorno de prueba.** Como se describe en [tareas de desarrollo para la implementación de aplicación de BizTalk](../core/development-tasks-for-biztalk-application-deployment.md), cuando una aplicación de BizTalk está lista para probarse, el programador exporta los artefactos de la aplicación a un archivo MSI. Una solución completa puede constar de una o más aplicaciones de BizTalk, por lo que puede que reciba varios archivos .msi para hacer pruebas. Puede copiar el archivo .msi a su equipo de pruebas y, a continuación, como se describe en el siguiente paso, importar los artefactos del archivo .msi en BizTalk Server. También puede usar el archivo .msi para instalar las aplicaciones en los equipos que las ejecutarán.  
  
2.  **Importe la aplicación desde el archivo MSI.** Puede usar el Asistente para importación, disponible en la consola de administración de BizTalk Server, para importar los artefactos del archivo .msi a una aplicación en la instancia actual de BizTalk Server. Para obtener más información, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Si la aplicación especificada no existe, el proceso de importación la crea. Puede ver la aplicación y modificar su configuración y contenido desde la consola de administración de BizTalk Server. Esto podría ser necesario, por ejemplo, para modificar los enlaces de su entorno de prueba. Para obtener más información, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md). Si se ha agregado a la aplicación un archivo de enlace que tiene los enlaces apropiados para su entorno de prueba, puede aplicarlos durante el proceso de importación. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
3.  **Instalar la aplicación.** Ahora puede instalar la aplicación en los servidores en los que desee ejecutarla. Si la aplicación incluye artefactos basados en archivos, debe instalarla para que pueda funcionar. Para instalar la aplicación, haga doble clic en el archivo .msi. Se instalan y registran los artefactos de la aplicación en el equipo local para que se pueda ejecutar la aplicación. Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
4.  **Probar la aplicación.** Ahora puede probar la aplicación. Una vez que el programador corrija los errores que encuentre y le proporcione un archivo .msi actualizado, puede volver a realizar los pasos 1, 2 y 3 de nuevo.  
  
5.  **Exporte archivos de enlace y agréguelos de nuevo a la aplicación (opcional).** Para facilitar la importación posterior de la aplicación en el entorno de prueba a fin de probar los cambios o adiciones, se recomienda exportar los enlaces de la aplicación y, a continuación, agregarlos de nuevo a la aplicación, mediante la especificación de un entorno de destino de prueba para los enlaces. Cuando, posteriormente, importe de nuevo el archivo .msi de la aplicación en la instancia de BizTalk Server de su equipo de prueba, puede especificar la aplicación de esos enlaces. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
6.  **Generar un archivo .msi para implementar la aplicación en el entorno de ensayo**. Una vez que haya terminado de probar su aplicación de BizTalk, puede implementarla en su entorno de ensayo. Para ello, utilice al Asistente para exportación para generar un nuevo archivo .msi, tal como se describe anteriormente en el paso 2. A continuación, puede pasar el archivo .msi al administrador de TI responsable de la implementación de ensayo. El Administrador de TI usará el archivo .msi para importar la aplicación a BizTalk Server en los equipos de almacenamiento provisional e instalar la aplicación en los equipos que vayan a ejecutarla, tal y como se describe en [tareas de almacenamiento provisional para la implementación de aplicación de BizTalk](../core/staging-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>Vea también  
 [Tareas de implementación de aplicaciones](../core/application-deployment-tasks.md)