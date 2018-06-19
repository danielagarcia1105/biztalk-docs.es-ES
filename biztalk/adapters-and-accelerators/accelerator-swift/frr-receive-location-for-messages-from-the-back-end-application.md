---
title: FRR ubicación de recepción para los mensajes de la aplicación de Back-End | Documentos de Microsoft
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
ms.openlocfilehash: 41d50f83feceac0238742cd474f70ecc1449f906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207540"
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a>FRR ubicación de recepción para los mensajes de la aplicación de Back-End
Para habilitar la conciliación de respuesta FIN (FRR), debe configurar un FRR ubicación de recepción que recibe mensajes de la aplicación de back-end y los enruta a BizTalk MessageBox para su uso por la orquestación FRR. La ubicación de recepción enruta un mensaje a través de una canalización de recepción FRR personalizada que debe crear con los siguientes componentes de canalización:  
  
-   El Desensamblador SWIFT en la fase de desensamblado  
  
-   El componente de canalización de descodificador de SWIFT FRR en la fase de descodificador  
  
-   El componente de canalización de resolución de SWIFT FRR CorrelationSet en la fase de resolución de entidades  
  
 El puerto de recepción controla los mensajes que tienen [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == False y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND == True. El mecanismo de transporte es lo que dicta la aplicación back-end.  
  
 Este puerto de recepción utiliza la misma canalización de recepción personalizada que se usa por la ubicación de recepción para los mensajes de SWIFT. Sin embargo, la canalización lleva a cabo funciones diferentes para las dos ubicaciones de recepción. En la ubicación de recepción de mensajes de la aplicación de back-end, el componente de canalización de resolución de SWIFT FRR CorrelationSet inicializa el token de correlación.