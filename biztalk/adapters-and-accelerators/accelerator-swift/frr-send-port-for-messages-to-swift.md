---
title: Puerto de envío de FRR para mensajes a SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1732e5e41cd60f6c98f435197e2e9c6284e4dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991741"
---
# <a name="frr-send-port-for-messages-to-swift"></a>Puerto de envío de FRR para mensajes a SWIFT
Para habilitar la conciliación de respuestas de FIN (FRR), debe configurar un puerto de envío FRR que envía un mensaje a AAS a través del adaptador de BizTalk para MQSeries. Este rutas de puerto de envío un mensaje a través de un FRR personalizado componente de canalización que se debe crear con los siguientes componentes de canalización de envío:  
  
- En la fase de ensamblado del ensamblador de SWIFT  
  
- El componente de canalización SWIFTAsmFrrMQSeriesHelper en la fase de codificación  
  
  El componente de canalización SWIFTAsmFrrMQSeriesHelper establece la propiedad MQMD_MsgID del mensaje saliente en el valor de la propiedad FRRCorrelationToken. También asigna y promociona otras propiedades de contexto necesarios comenzando con "MQ" con valores establecidos en el tiempo de diseño de canalización. La canalización de envío incluye cada propiedad definida para MQSeries como una propiedad configurable. Cada valor predeterminado es "No se usa".  
  
  El puerto de envío controla los mensajes que tienen [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed == False y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND == True. El mecanismo de transporte es el adaptador de BizTalk para MQSeries. Para obtener información acerca de las propiedades de transporte, como el tamaño de fragmentación, consulte la documentación de MQSeries.