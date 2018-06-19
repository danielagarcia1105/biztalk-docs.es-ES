---
title: FRR puertos de envío de mensajes a los controladores personalizados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6babc312ddad7d77a96e29bc9e59ec9298aa6ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207836"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a>FRR puertos de envío de mensajes a los controladores personalizados
Para habilitar a los controladores personalizados para FRR, debe crear una serie de puertos de envío FRR, cada uno de los cuales enruta una copia de un mensaje original de un tipo determinado para los controladores personalizados. Estos puertos de envío deben tienen los siguientes componentes de canalización:  
  
-   El ensamblador SWIFT en la fase de ensamblado  
  
-   El componente de canalización SWIFTSendFrrComponent en la fase de codificación  
  
 Para todos los mensajes excepto los mensajes de SWIFT FINÉS categoría 0 a 9 y que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   BTS. Operación que se establece en el valor necesario para cada tipo de mensaje. Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).  
  
 Para los mensajes de FIN de SWIFT categoría 0 a 9 y que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceTyp ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrFailed == true  
  
-   BTS. Operación ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason se establece en el valor necesario para cada tipo de mensaje. Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).