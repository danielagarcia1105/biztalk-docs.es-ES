---
title: Ubicación de recepción para que no se encontró una dirección | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1242ffc77976fb2ffcc469752d13a6f6366d7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268772"
---
# <a name="receive-location-for-address-not-found"></a>No se encontró la ubicación de recepción para la dirección
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|No se encontró la ubicación de recepción de dirección "{0}". (La ubicación de recepción de BizTalk puede estar deshabilitada.)|  
  
## <a name="explanation"></a>Explicación  
 Este error indica que una ubicación de recepción WCF aislada publicada no encontró la ubicación de recepción correspondiente.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice lo siguiente: en la consola de administración de BizTalk, asegúrese de que la ubicación de recepción especificada por el atributo receiveLocationName en el archivo Web.config que el Asistente de publicación de WCF de BizTalk genera existe y se ha iniciado.  
  
 Para obtener más información sobre la creación de ubicaciones de recepción, vea los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Publicar servicios WCF con WCF aislado adaptadores de recepción](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Cómo configurar un WCF-BasicHttp ubicación de recepción](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Cómo configurar un WCF-WSHttp ubicación de recepción](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Cómo configurar un WCF-CustomIsolated ubicación de recepción](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Tutorial: Publicar servicios WCF con el adaptador WCF-BasicHttp](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)