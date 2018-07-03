---
title: Implementación de aplicaciones y características de administración | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- what's new, Installation Wizard
- what's new, BTSTask command-line tool
- what's new, Import Wizard
- deploying, what's new
- what's new, Export Wizard
- what's new, deploying
- applications, what's new
- what's new, applications
ms.assetid: 2d09d6b1-1003-406f-81da-14e21a1cbc81
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cea9ffd127381a41e10ec6e4921ae21bd4ce74a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011085"
---
# <a name="application-deployment-and-management-features"></a>Características de implementación y administración de aplicaciones
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye varias características que le ayudarán con la implementación de soluciones empresariales de BizTalk:  
  
- **Aplicación de BizTalk.** Una aplicación de BizTalk proporciona un modo de ver y administrar los elementos, denominados "artefactos", que constituyen la solución empresarial de BizTalk. Entre los artefactos se incluyen los ensamblados, orquestaciones, asignaciones, esquemas, certificados de seguridad, directivas de reglas de negocio, archivos de configuración de BAM, enlaces, etc., necesarios para que funcione una solución empresarial. Puede agregar artefactos a una aplicación de BizTalk y, después, ver, empaquetar, implementar y administrar todos los que contiene una aplicación como una entidad única desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Puede crear una, dos o más aplicaciones de BizTalk para administrar los artefactos en su solución empresarial. También puede usar el Asistente para exportación para exportar la aplicación y sus artefactos y, a continuación, el Asistente para importación para importar el archivo .msi a otro grupo de BizTalk donde se puede volver a crear la aplicación. Después, puede usar el Asistente para instalación para instalar la aplicación. Estos asistentes se describen posteriormente en este tema. Todos los procedimientos de implementación descritos en esta documentación incluyen instrucciones para usar la consola de administración. También puede usar la herramienta de la línea de comandos BTSTask para muchas tareas administrativas y en esta documentación también se incluyen los procedimientos para su uso.  
  
- **Asistente para la importación.** Utilice el Asistente para importación, disponible desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, para importar artefactos desde un archivo .msi a una aplicación de BizTalk. Si la aplicación especificada no existe, el Asistente para importación la crea. El asistente también registra y almacena los artefactos en el archivo .msi en la base de datos de administración de BizTalk. Para obtener más instrucciones sobre cómo utilizar el Asistente para importación para importar los artefactos, consulte [importando aplicaciones de BizTalk, enlaces y directivas](../core/importing-biztalk-applications-bindings-and-policies.md).  
  
- **Asistente para la instalación.** Puede iniciar el Asistente para instalación como paso final del Asistente para importación. El asistente instala la aplicación en el equipo local para que pueda ejecutar la aplicación en él. Para obtener instrucciones, consulte [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md). También puede iniciar el Asistente para importación si hace doble clic en un archivo .msi de aplicación. Para obtener más información, consulte [cómo instalar una aplicación de BizTalk](../core/how-to-install-a-biztalk-application.md).  
  
- **Asistente para exportación.** El Asistente para exportación, también disponible desde la consola de administración de BizTalk Server, se usa para generar un archivo .msi desde una aplicación de BizTalk. Después, puede usar el Asistente para importación para importar el archivo .msi a un grupo de BizTalk diferente. Esto facilita la tarea de agregar recursos a una aplicación o bien crea de forma automática una aplicación en el nuevo grupo de BizTalk. Para obtener más información sobre cómo usar el Asistente para exportación, consulte [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md).  
  
- **Herramienta de línea de comandos BTSTask.** BTSTask es compatible con las características de implementación de aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], lo que le permite realizar muchas operaciones desde la línea de comandos. Para obtener más información, consulte [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md).  
  
  Para ayudarle a familiarizarse con estas nuevas características de implementación, se recomienda que realice los pasos en [Tutorial: implementar una aplicación básica de BizTalk](../core/walkthrough-deploying-a-basic-biztalk-application.md).  
  
## <a name="see-also"></a>Vea también  
 [Descripción de la implementación y administración de aplicaciones de BizTalk](../core/understanding-biztalk-application-deployment-and-management.md)