---
title: Ubicación para los mensajes de recepción de FRR desde la aplicación Back-End | Microsoft Docs
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
ms.assetid: da0ad616-800f-493f-822f-eca1224722ab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9133a4499e655003ec2cc3d2e0d654e5a225f58b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981533"
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a>Ubicación para los mensajes de recepción de FRR desde la aplicación Back-End
Para habilitar la conciliación de respuestas de FIN (FRR), debe configurar un FRR ubicación de recepción que recibe los mensajes de la aplicación de back-end y los enruta a BizTalk MessageBox para su uso por la orquestación de FRR. La ubicación de recepción enruta un mensaje a través de una canalización de recepción FRR personalizado que se debe crear con los siguientes componentes de canalización:  
  
- En la fase de desensamblado del desensamblador de SWIFT  
  
- El componente de canalización de descodificador de FRR SWIFT en la fase de descodificador  
  
- El componente de canalización de SWIFT FRR CorrelationSet solucionador en la fase de resolución de entidades  
  
  El puerto de recepción controla los mensajes que tienen [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == False y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND == True. El mecanismo de transporte es todo lo que dicta la aplicación back-end.  
  
  Este puerto de recepción utiliza la misma canalización de recepción personalizada que se usa por la ubicación de recepción para los mensajes de SWIFT. Sin embargo, la canalización lleva a cabo funciones diferentes para las dos ubicaciones de recepción. En la ubicación de recepción de mensajes de la aplicación de back-end, el componente de canalización de resolución de SWIFT FRR CorrelationSet inicializa el token de correlación.