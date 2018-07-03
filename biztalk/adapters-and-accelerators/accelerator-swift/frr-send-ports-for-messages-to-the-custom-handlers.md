---
title: Puertos de envío de FRR para mensajes a los controladores personalizados | Microsoft Docs
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
ms.openlocfilehash: df8ba2b085268f2c0c272b81b27768db716b63c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996157"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a>Puertos de envío de FRR para mensajes a los controladores personalizados
Para habilitar los controladores personalizados para FRR, debe crear una serie de puertos de envío FRR, cada uno de los cuales enruta una copia de un mensaje original de un tipo determinado a los controladores personalizados. Estos puertos de envío deben los siguientes componentes de canalización:  

- En la fase de ensamblado del ensamblador de SWIFT  

- El componente de canalización SWIFTSendFrrComponent en la fase de codificación  

  Para todos los mensajes excepto los mensajes de FIN de SWIFT categoría 0 al 9 que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  

- BTS. Operación establece en el valor necesario para cada tipo de mensaje. Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).  

  Para los mensajes de categoría de 0 a 9 SWIFT FIN que no se envían correctamente, el puerto de envío debe tener los siguientes filtros:  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceTyp ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrFailed == true  

- BTS. Operación ==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason establecido en el valor necesario para cada tipo de mensaje. Para obtener los valores posibles para el BTS. Propiedad de operación, vea la tabla de [crear los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md).
