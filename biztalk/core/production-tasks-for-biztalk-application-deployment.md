---
title: Tareas de producción para la implementación de aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], assemblies
- applications, deploying
- assemblies, warnings
- deploying [applications], warnings
- deploying [applications], tasks
- assemblies, deploying
- deploying [applications], production
ms.assetid: e77d8921-42ef-4c51-aab2-66c086aad955
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 260afd4522d28bdd2a485a1a11edc045c7fde880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265036"
---
# <a name="production-tasks-for-biztalk-application-deployment"></a>Tareas de producción para la implementación de una aplicación de BizTalk
A continuación se explican los pasos necesarios para implementar una aplicación de BizTalk en un entorno de producción.  
  
> [!IMPORTANT]
>  No implemente nunca ensamblados en un equipo de producción desde Visual Studio. Para que esto último sea posible, Visual Studio debe anular la implementación, separar, detener y dar de baja ensamblados que existen en la misma aplicación o en aplicaciones distintas. Aunque esto resulta necesario y apropiado en un entorno de desarrollo, puede producir consecuencias inesperadas no deseadas en un entorno de producción. Además, para evitar la posibilidad de que alguien intente implementar un ensamblado desde Visual Studio en un equipo de producción, se recomienda que no instale Visual Studio en un equipo de producción.  
  
> [!IMPORTANT]
>  Preste atención al actualizar aplicaciones de las que dependan otras aplicaciones en el entorno de producción para no interrumpir la actividad de las otras aplicaciones en ejecución. Para obtener más información, consulte [consideraciones importantes para actualizar aplicaciones](../core/important-considerations-for-updating-applications.md).  
  
1.  **Copie el archivo .msi en el entorno de producción.** Como se describe en [tareas de prueba para la implementación de aplicación de BizTalk](../core/testing-tasks-for-biztalk-application-deployment.md), cuando la aplicación de almacenamiento provisional ha completado y está listo para producción, el Administrador de TI responsable de la configuración de almacenamiento provisional de BizTalk proporciona un archivo .msi para se usa para la implementación de producción. Puede copiar este archivo .msi en los equipos de producción y, a continuación, como se describe en el siguiente paso, importar la aplicación de BizTalk desde el archivo .msi en BizTalk Server. También puede usar el archivo .msi para instalar la aplicación en los equipos que la ejecutarán. Una solución de BizTalk completa puede constar de una o más aplicaciones, por lo que puede que reciba varios archivos .msi para implementarlos.  
  
2.  **Importe la aplicación desde el archivo MSI.** Puede usar el Asistente para importación, disponible en la consola de administración de BizTalk Server, para importar el contenido del archivo .msi a una aplicación de la instancia actual de BizTalk Server. Para obtener más información, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). Si la aplicación especificada no existe, se crea al importar el archivo .msi. A continuación, puede ver la aplicación y modificar su configuración y contenido desde la consola de administración. Esto puede ser necesario, por ejemplo, para configurar certificados y extremos, como direcciones URL, así como para modificar los enlaces para el entorno de producción. Para obtener más información, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md). Si se agregó un archivo de enlace a la aplicación que tiene los enlaces correspondientes del entorno de producción, puede aplicarlos durante el proceso de importación. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
3.  **Instale e inicie la aplicación.** Ahora puede instalar la aplicación en todos los equipos que la van a ejecutar, e iniciarla en la consola de administración. Para instalar la aplicación, haga doble clic en el archivo .msi. Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
4.  **Exporte archivos de enlace y agréguelos de nuevo a la aplicación (opcional).** Para facilitar la posterior reimportación de la aplicación al entorno de producción para implementar cambios o adiciones, puede serle útil exportar los enlaces de la aplicación y, a continuación, volver a agregárselos, especificando un entorno de destino de producción para los enlaces. Cuando, posteriormente, importe de nuevo el archivo .msi de la aplicación a la instancia de BizTalk Server del entorno de producción, puede especificar que se apliquen esos enlaces. Para obtener más información, consulte [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
5.  **Exportar la aplicación a un nuevo archivo .msi (opcional).** Si realiza cambios de configuración o las adiciones a la aplicación y desea que los cambios se reflejen en el archivo .msi (por ejemplo, para implementar la aplicación en otros grupos de BizTalk), puede exportar un nuevo archivo .msi, tal y como se describe en [cómo exportar un Aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Tareas de implementación de aplicaciones](../core/application-deployment-tasks.md)