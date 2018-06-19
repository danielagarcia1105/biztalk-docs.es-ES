---
title: Tareas de almacenamiento provisional para la implementación de aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, staging
- deploying [applications], staging
- applications, deploying
- deploying [applications], tasks
ms.assetid: de60eddb-da13-412a-94f9-331387b5930e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f03d0cfd5db587a84a080d5963d6696e123ef2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278276"
---
# <a name="staging-tasks-for-biztalk-application-deployment"></a>Tareas de ensayo para la implementación de una aplicación de BizTalk
A continuación se explican los pasos necesarios para implementar una aplicación de BizTalk en un entorno de ensayo.  
  
1.  **Copie el archivo .msi en su entorno de ensayo.** Como se describe en [tareas de prueba para la implementación de aplicación de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md), cuando BizTalk ha completado la comprobación de aplicación y está listo para el almacenamiento provisional, el equipo de pruebas proporciona uno o más .msi archivos para el almacenamiento provisional. (Una solución completa puede constar de una o más aplicaciones de BizTalk, por lo que puede que reciba varios archivos .msi para los ensayos).  Puede copiar ese archivo .msi a sus equipos de ensayo y a continuación, como se describe en el siguiente paso, importar la aplicación de BizTalk del archivo .msi en un grupo de BizTalk del entorno de ensayo. También puede usar el archivo .msi para instalar la aplicación en los equipos que la ejecutarán.  
  
2.  **Importe la aplicación desde el archivo MSI.** Puede usar el Asistente para importación, disponible en la consola de administración de BizTalk Server, para importar el contenido del archivo .msi a una aplicación de un grupo de BizTalk en el entorno de ensayo. Para obtener más información, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Si la aplicación especificada no existe, se crea al importar el archivo .msi. Puede ver la aplicación y modificar su configuración y contenido desde la consola de administración de BizTalk Server. Esto puede serle necesario, por ejemplo, para modificar los enlaces de su entorno de ensayo. Para obtener más información, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md). Si se ha agregado a la aplicación un archivo de enlace que tiene los enlaces apropiados para su entorno de ensayo, puede aplicarlos durante el proceso de importación. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
3.  **Exporte archivos de enlace y agréguelos de nuevo a la aplicación (opcional).** Para facilitar la posterior reimportación de la aplicación a su entorno de ensayo si se realizan cambios o adiciones en ella, puede serle útil exportar los enlaces de la aplicación y, a continuación, volver a agregárselos, especificando un entorno de destino de ensayo para los enlaces. Cuando, posteriormente, importe de nuevo el archivo .msi de la aplicación en la instancia de BizTalk Server de su equipo de ensayo, puede especificar la aplicación de esos enlaces. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
4.  **Instalar la aplicación.** Ahora puede instalar la aplicación en todos los equipos que vayan a ejecutarla. Puede instalar la aplicación mediante el Asistente para instalación o simplemente haciendo doble clic en el archivo .msi. Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
5.  **Probar la aplicación para comprobar la configuración y los enlaces.** Ahora puede probar la aplicación para asegurarse de que funciona según lo previsto en el entorno de ensayo. Una vez que usted o el programador hayan realizado los cambios pertinentes, puede volver a seguir los pasos 1 a 4.  
  
6.  **Generar un archivo .msi para implementar la aplicación en el entorno de producción**. Una vez que haya terminado de configurar su aplicación de BizTalk para el entorno de producción y comprobado la configuración, puede implementarla en su entorno de producción. Para ello, utilice el Asistente para exportación para generar un nuevo archivo .msi, tal y como se describe en [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md). A continuación puede pasar el archivo .msi al administrador de TI responsable de la implementación de producción. El Administrador de TI usará el archivo .msi para importar la aplicación a BizTalk Server en los equipos de producción, así como para instalarlo en los equipos que vayan a ejecutarla, tal y como se describe en [tareas de producción para la implementación de aplicación de BizTalk](../core/production-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>Vea también  
 [Tareas de implementación de aplicaciones](../core/application-deployment-tasks.md)