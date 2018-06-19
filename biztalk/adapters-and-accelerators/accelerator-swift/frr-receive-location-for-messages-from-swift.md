---
title: FRR ubicación de recepción para mensajes de SWIFT. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: d15989de-56f9-4d62-8394-f4fd6e971495
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d609cfc8c5177581f32ee0957a6a7ae7c1fe9a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207564"
---
# <a name="frr-receive-location-for-messages-from-swift"></a>FRR ubicación de recepción para mensajes de SWIFT.
Para habilitar la conciliación de respuesta FIN (FRR), debe configurar un FRR recibe el componente de canalización para recibir un mensaje de AAS y prepararlo para su procesamiento mediante [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. La canalización de recepción contiene los siguientes componentes:  
  
-   El Desensamblador SWIFT en la fase de desensamblado  
  
-   El componente de canalización de descodificador de SWIFT FRR en la fase de descodificador  
  
-   El componente de canalización de resolución de SWIFT FRR CorrelationSet en la fase de resolución de entidades  
  
 Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe un PAN/NAN, SWIFT FRR descodificador lee la propiedad de contexto de comentarios de MQ para determinar si la respuesta es un panorámica o un valor NAN. Establece el transporte independiente [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]valores _FRRTransportLevelAck un valor booleano en true para una panorámica o false para un valor NAN.  
  
 El componente de canalización de resolución de SWIFT FRR CorrelationSet sobrescribe la propiedad de FRRCorrelationToken del mensaje de respuesta, que usa la orquestación FRR, con el valor de la MQMD. Propiedad CorrelId.