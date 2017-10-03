---
title: Ver los patrones de intercambio de mensajes compatibles en el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6662f17-b4f8-45fe-a22f-5d027dc9f2ff
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77fee95033e669bf584220461b330afbb9fd25b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="view-the-supported-message-exchange-patterns-in-the-wcf-lob-adapter-sdk"></a>Ver los patrones de intercambio de mensajes compatibles en el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] admite varios de los patrones de mensajería compatibles con subyacente [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] incluida la comunicación unidireccional y solicitud y respuesta. Transportes diferentes admiten patrones de mensajería diferentes y lo que afecta a los tipos de interacciones que admiten.  
  
 Los patrones que se muestran en la tabla siguiente se controlan mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].  
  
|Patrón|Description|  
|-------------|-----------------|  
|Unidireccional entrante|Mensajes entrantes se reciben desde el sistema de línea de negocio pero se espera ninguna respuesta desde el adaptador.|  
|Solicitudes y respuestas entrantes|Mensajes entrantes se reciben desde el sistema de línea de negocio que espera una respuesta adecuada del adaptador.|  
|Unidireccional saliente|Los mensajes salientes se envían al sistema de línea de negocio pero se espera ninguna respuesta desde el adaptador.|  
|Salida de solicitudes y respuestas|Los mensajes salientes se envían al sistema de línea de negocio con una respuesta que se espera que el adaptador.|  
|Con sesión entrante|Mensajes entrantes se reciben desde el sistema de línea de negocio dentro de una sesión única. Se espera ninguna respuesta por el sistema de línea de negocio en el adaptador.|  
|Salida de la sesión|Los mensajes salientes se envían al sistema de línea de negocio dentro de una sesión única. Se espera ninguna respuesta desde el sistema de línea de negocio por el adaptador.|  
  
 La elección del patrón de mensaje le guiará por la funcionalidad de la aplicación de destino.  
  
## <a name="planning-for-sessions"></a>Planeación de las sesiones  
 Un patrón de mensajería puede utilizar una sesión cuando desea asegurarse de que todos los mensajes intercambiados entre el adaptador y el sistema de línea de negocio deben formar parte de la misma conversación. Normalmente se utilizan sesiones cuando se necesita la garantía de entrega, pero también pueden usarse para admitir otros requisitos que puedan tener un programador de adaptadores para el intercambio de mensajes.  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se basa en el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] para compatibilidad con la sesión. Para obtener más información acerca de las sesiones, consulte [sesiones, Instancing y simultaneidad](https://msdn.microsoft.com/library/ms731193.aspx). 
  
## <a name="see-also"></a>Vea también  
 [Planear y diseñar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)