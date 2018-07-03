---
title: Tipo de serialización de mensaje saliente no reconocido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e675112b-12f3-47ff-95f7-ce1a05db120e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda3e7bd3d20e39bb59c2c1fbe14dfc964fd541a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023434"
---
# <a name="unrecognized-outbound-message-marshalling-type"></a>Tipo de serialización de mensaje saliente no reconocido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]               |
|    Identificador del evento     |                                           0                                            |
|  Origen del evento   |                                           0                                            |
|    Componente    |                                           0                                            |
|  Nombre simbólico  |                                           0                                            |
|  Texto del mensaje   | Tipo de serialización de mensaje saliente no reconocido; se esperaba UseBodyElement o UseTemplate. |
  
## <a name="explanation"></a>Explicación  
 La propiedad WCF.OutboundBodyLocation se estableció en un valor distinto de UseBodyElement o UseTemplate, en un componente de canalización o una orquestación personalizados.  
  
## <a name="user-action"></a>Acción del usuario  
 Establezca la propiedad WCF.OutboundBodyLocation en un valor válido. Los valores válidos son "UseBodyElement" o "UseTemplate". Se trata de un cambio de código.   
Para obtener más información sobre la mensajería saliente, consulte los siguientes recursos en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ayuda:  
  
-   [Configuración de puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [Configuración de adaptadores de WCF](../core/configuring-the-wcf-adapters.md)