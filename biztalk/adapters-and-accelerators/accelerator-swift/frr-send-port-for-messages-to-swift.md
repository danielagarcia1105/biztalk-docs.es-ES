---
title: "Puerto de envío FRR mensajes SWIFT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a442b45f57009b839b4e184ef9662b253ba32b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-port-for-messages-to-swift"></a>Puerto de envío FRR mensajes SWIFT
Para habilitar la conciliación de respuesta FIN (FRR), debe configurar un puerto de envío FRR que envía un mensaje a AAS a través del adaptador de BizTalk para MQSeries. Este rutas de puerto de envío un mensaje a través de un FRR personalizado componente de canalización que debe crear con los siguientes componentes de canalización de envío:  
  
-   El ensamblador SWIFT en la fase de ensamblado  
  
-   El componente de canalización SWIFTAsmFrrMQSeriesHelper en la fase de codificación  
  
 El componente de canalización SWIFTAsmFrrMQSeriesHelper establece la propiedad MQMD_MsgID del mensaje saliente en el valor de la propiedad FRRCorrelationToken. También asigna y promociona otras propiedades de contexto necesario a partir de "MQ" con los valores establecidos en el tiempo de diseño de canalización. La canalización de envío incluye cada propiedad definida para MQSeries como una propiedad configurable. Cada valor predeterminado es "No usado".  
  
 El puerto de envío controla los mensajes que tienen [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == False y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND == True. El mecanismo de transporte es el adaptador de BizTalk para MQSeries. Para obtener información acerca de las propiedades de transporte, como el tamaño de la fragmentación, consulte la documentación de MQSeries.