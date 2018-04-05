---
title: Adaptador de Windows SharePoint Services | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters
ms.assetid: cbfc9bf3-912d-4849-ba8c-07a116888bbd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a6f1365b11ce93717223ec35e395165e8d0e551
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="windows-sharepoint-services-adapter"></a>Adaptador de Windows SharePoint Services
El adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Microsoft Windows SharePoint Services proporciona una mayor integración de BizTalk Server con Windows SharePoint Services y Microsoft Office. El uso del adaptador de Windows SharePoint Services en la solución [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite obtener las funciones siguientes:  
  
-   Fácil acceso a los mensaje de entrada y salida mediante Windows SharePoint Services.  
  
-   Capacidad de editar mensajes XML mediante aplicaciones de Office tales como Microsoft Office InfoPath.  
  
-   Transformaciones bidireccionales de mensajes XML desde y hacia InfoPath.  
  
 El adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] consta de los siguientes componentes:  
  
|||  
|-|-|  
|Adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] de CSOM|Usa el modelo de objetos del cliente de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] (CSOM). El adaptador se instala con la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. No es necesario ningún paso de instalación adicional.<br /><br /> El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación ***automáticamente*** instala el cliente objeto modelo SharePoint redistribuible, que también está disponible en [http://go.microsoft.com/fwlink/p/?LinkId=263482](http://go.microsoft.com/fwlink/p/?LinkId=263482).|  
|Servicio Web de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] de SSOM|**Opción obsoleta**. Con esta opción, se utiliza el modelo de objetos cliente de servicio (SSOM) de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].<br /><br /> El servicio web se instala en el PC de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], lo que puede ser en el mismo PC que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o en uno distinto.<br /><br /> Para instalar el servicio web, ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalación en el [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] equipo y compruebe **adaptador de Windows SharePoint Services**.|  
  
 [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) proporciona más información sobre la [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] instalación.  
  
> [!NOTE]
>  En este momento, no se admite la autenticación federada. Se admiten únicamente el nombre de usuario y contraseña.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [CSOM: Adaptador de servicios de SharePoint](../core/csom-sharepoint-services-adapter.md)  
  
-   [SSOM: Servicio Web de adaptador SharePoint Services](../core/ssom-sharepoint-services-adapter-web-service.md)  
  
## <a name="see-also"></a>Vea también  
 [Uso de adaptadores](../core/using-adapters.md)   
 [Desarrollar aplicaciones de BizTalk Server](../core/developing-biztalk-server-applications.md)