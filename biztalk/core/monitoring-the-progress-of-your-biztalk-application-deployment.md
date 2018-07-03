---
title: Supervisar el progreso de la implementación de aplicaciones de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, deploying
- applications, monitoring
- deploying [applications], monitoring
- monitoring, applications
ms.assetid: a69a8288-0203-440f-9805-52786525e193
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07beea810ff64c807685b8170009d5204ede1af7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001157"
---
# <a name="monitoring-the-progress-of-your-biztalk-application-deployment"></a>Supervisar el progreso de implementación de la aplicación de BizTalk
Es posible supervisar el progreso de implementación de la aplicación de BizTalk de dos formas:  
  
- **Registro de instalación de BizTalk**: puede consultar el registro de instalación que genera BizTalk Server. Registros de instalación se encuentran en %SystemDrive%\Documents and Settings\\<*usuario actual*\>\Application data\microsoft\biztalk Server\Deployment.  
  
- **Registro de eventos local**: puede realizar un seguimiento del progreso de una instalación en el registro de eventos local. Por lo tanto, puede hacer un seguimiento de las acciones de instalación personalizadas servidor a servidor.  
  
- **Registro de Windows Installer**: Microsoft Windows Installer crea un archivo de registro en el equipo local que registra las acciones de una acción personalizada. Puede especificar este archivo de registro mediante la opción /log del comando msiexec. Para obtener más información, consulte la documentación de Windows Installer.  
  
> [!IMPORTANT]
>  Al implementar o anular la implementación de un esquema de propiedades, se pueden exponer datos confidenciales y, por lo tanto, información confidencial durante el seguimiento. Siempre que se implemente o se anule la implementación de un ensamblado que contenga un esquema de propiedades, el visor de eventos registrará un evento en el registro de eventos de aplicación de Windows. Debería comprobar el registro de eventos de estos mensajes para asegurarse de que todas las actividades de implementación de ensamblados están en línea con las directivas de datos confidenciales. (El mensaje generado en el registro de eventos para la implementación es: "El usuario"{1}"ha implementado el ensamblado"{0}"que contiene esquemas de propiedad". El mensaje generado en el registro de eventos para la anulación de implementación es: "El usuario"{1}"anulado la implementación del ensamblado"{0}"que contiene esquemas de propiedad".)  
  
## <a name="see-also"></a>Vea también  
 [Implementación de aplicaciones de BizTalk](../core/deploying-biztalk-applications.md)