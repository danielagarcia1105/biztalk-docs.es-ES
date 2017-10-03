---
title: "Ubicación de recepción para que no se encontraron metadatos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb45272f7d3ef4491b59d5b019eb4499bcf5dff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receive-location-for-metadata-not-found"></a>No se encontró la ubicación de recepción para los metadatos
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se encontró la ubicación de recepción "{0}" para los metadatos. (Compruebe la asignación de la ubicación de recepción en Web.config y asegúrese de que la ubicación de recepción existe.)|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente para metadatos.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificada por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.  
  
 Para obtener más información sobre las ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Publicar servicios WCF](../core/publishing-wcf-services.md)  
  
-   [Cómo configurar un WCF-BasicHttp ubicación de recepción](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Cómo configurar un WCF-WSHttp ubicación de recepción](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar un WCF-CustomIsolated ubicación de recepción](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Tutorial: Publicar servicios WCF con el adaptador WCF-NetMsmq](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)