---
title: OutboundCustomHeaders no tiene el formato correcto | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6097762b-01c9-48b8-8cee-ccd6b11d28d4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b81a8c9c605f646a8ac0b6df2045af05eb58e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="outboundcustomheaders-does-not-have-correct-format"></a>OutboundCustomHeaders no tiene el formato correcto
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|OutboundCustomHeaders no tiene un formato correcto.|  
  
## <a name="explanation"></a>Explicación  
 El valor de WCF. InboundHeaders o WCF. OutboundCustomHeaders no tiene el formato siguiente: \<encabezados >...\</headers >.  
  
## <a name="user-action"></a>Acción del usuario  
 Ajustar los valores de propiedad con \<encabezados > elemento.  
  
 Para obtener más información, vea el recurso siguiente en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   [Usar encabezados SOAP en mensajes WCF con componentes de canalización](../core/using-soap-headers-in-wcf-messages-with-pipeline-components.md)