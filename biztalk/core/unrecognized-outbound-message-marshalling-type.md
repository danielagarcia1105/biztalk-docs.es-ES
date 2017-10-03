---
title: "Cálculo de referencias de tipo de mensaje saliente no reconocido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3928bde0d81a4fe22b7c16af41c3a4b6d5c7121c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unrecognized-outbound-message-marshalling-type"></a>Tipo de serialización de mensaje saliente no reconocido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Tipo de serialización de mensaje saliente no reconocido; se esperaba UseBodyElement o UseTemplate.|  
  
## <a name="explanation"></a>Explicación  
 La propiedad WCF.OutboundBodyLocation se estableció en un valor distinto de UseBodyElement o UseTemplate, en un componente de canalización o una orquestación personalizados.  
  
## <a name="user-action"></a>Acción del usuario  
 Establezca la propiedad WCF.OutboundBodyLocation en un valor válido. Los valores válidos son "UseBodyElement" o "UseTemplate". Se trata de un cambio de código.   
Para obtener más información acerca de los mensajes salientes, vea los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:  
  
-   [Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [Configurar los adaptadores de WCF](../core/configuring-the-wcf-adapters.md)