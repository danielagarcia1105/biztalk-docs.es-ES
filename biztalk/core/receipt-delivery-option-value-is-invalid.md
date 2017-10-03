---
title: "No es válido el valor Receipt-Delivery-Option | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f14541cd9c296e6a4527e7c2958123e072be8c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receipt-delivery-option-value-is-invalid"></a>El valor Receipt-Delivery-Option no es válido
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|InvalidReceiptDeliveryOptionError|  
|Texto del mensaje|Valor Receipt-Delivery-Option: "{0}" no es válido.  {1}|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que Receipt-Delivery-Option en el mensaje AS2 recibido no es una dirección URL válida y no se ajusta a las especificaciones de AS2 RFC 4130.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie Receipt-Delivery-Option en el mensaje AS2 para que incluya una dirección URL válida y se ajuste a las especificaciones del apartado 7.3 de AS2 RFC 4130; a continuación, vuelva a enviar el mensaje AS2.