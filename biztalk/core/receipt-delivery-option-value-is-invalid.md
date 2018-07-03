---
title: No es válido el valor Receipt-Delivery-Option | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8966e3d95e89aff023300a9834ab1bca2915421f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994853"
---
# <a name="receipt-delivery-option-value-is-invalid"></a>El valor Receipt-Delivery-Option no es válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                           InvalidReceiptDeliveryOptionError                            |
|  Texto del mensaje   |                 Valor de Receipt-Delivery-Option: "{0}" no es válido.  {1}                  |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que Receipt-Delivery-Option en el mensaje AS2 recibido no es una dirección URL válida y no se ajusta a las especificaciones de AS2 RFC 4130.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cambie Receipt-Delivery-Option en el mensaje AS2 para que incluya una dirección URL válida y se ajuste a las especificaciones del apartado 7.3 de AS2 RFC 4130; a continuación, vuelva a enviar el mensaje AS2.