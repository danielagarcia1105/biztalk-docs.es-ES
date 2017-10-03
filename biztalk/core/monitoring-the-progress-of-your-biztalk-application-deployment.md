---
title: "Supervisar el progreso de la implementación de aplicaciones de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eaa81067f5a413c689a4a51ac6b102d80782e2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a>Supervisar el progreso de implementación de la aplicación de BizTalk
Es posible supervisar el progreso de implementación de la aplicación de BizTalk de dos formas:  
  
-   **Registro de instalación de BizTalk**: puede consultar la instalación de registro que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera. Los registros de instalación se encuentran en %SystemDrive%\Documents and Settings\\<*usuario actual*> \Application Data\Microsoft\\[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]\Deployment.  
  
-   **Registro de eventos local**: puede realizar un seguimiento del progreso de una instalación en el registro de eventos local. Por lo tanto, puede hacer un seguimiento de las acciones de instalación personalizadas servidor a servidor.  
  
-   **Registro de Windows Installer**: Microsoft Windows Installer crea un archivo de registro en el equipo local que registra las acciones de una acción personalizada. Puede especificar este archivo de registro mediante la opción /log del comando msiexec. Para obtener más información, consulte la documentación de Windows Installer.  
  
> [!IMPORTANT]
>  Al implementar o anular la implementación de un esquema de propiedades, se pueden exponer datos confidenciales y, por lo tanto, información confidencial durante el seguimiento. Siempre que se implemente o se anule la implementación de un ensamblado que contenga un esquema de propiedades, el visor de eventos registrará un evento en el registro de eventos de aplicación de Windows. Debería comprobar el registro de eventos de estos mensajes para asegurarse de que todas las actividades de implementación de ensamblados están en línea con las directivas de datos confidenciales. (El mensaje generado en el registro de eventos para la implementación es: "el usuario"{{1}"implementado el ensamblado"{0}"que contiene esquemas de propiedad". El mensaje generado en el registro de eventos para la anulación es: "el usuario"{{1}"anularse el ensamblado que contiene esquemas de propiedad" {0}".")  
  
## <a name="see-also"></a>Vea también  
 [Implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)