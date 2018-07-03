---
title: FRR ubicación de recepción para mensajes de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 2dc4666e90510e7076a3f901ce6fc95b07ef16c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002085"
---
# <a name="frr-receive-location-for-messages-from-swift"></a>FRR ubicación de recepción para mensajes de SWIFT
Para habilitar la conciliación de respuestas de FIN (FRR), debe configurar un FRR recibe el componente de canalización para recibir un mensaje de SAA y prepararla para el procesamiento por [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. La canalización de recepción contiene los siguientes componentes:  
  
- En la fase de desensamblado del desensamblador de SWIFT  
  
- El componente de canalización de descodificador de FRR SWIFT en la fase de descodificador  
  
- El componente de canalización de SWIFT FRR CorrelationSet solucionador en la fase de resolución de entidades  
  
  Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe un panorámica o NAN, SWIFT FRR descodificador lee la propiedad de contexto de MQ comentarios para determinar si la respuesta es un panorámica o un NAN. Establece el transporte agnóstico [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]valores _FRRTransportLevelAck un valor booleano true para una panorámica o false para un NAN.  
  
  El componente de canalización de resolución de SWIFT FRR CorrelationSet sobrescribe la propiedad de FRRCorrelationToken del mensaje de respuesta, que utiliza la orquestación de FRR, con el valor en el MQMD. Propiedad CorrelId.