---
title: "Conciliación de respuesta FIN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- FRR
- FIN Response Reconciliation
- SAA
- NAKs
- FRR, about FRR
- acknowledgements
- FIN Response Reconciliation, about FIN Response Reconciliation
- FIN Response Reconciliation, acknowledgements
ms.assetid: 987b932b-e487-4ca8-acd0-410d71df8e6d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5452dbacb8a9a20c8d2e62d62f6043aaea2d18da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation"></a>Conciliación de respuesta FIN
La característica de conciliación de respuesta de FIN (FRR) de [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reconcilia una respuesta FIN con el correspondiente mensaje original enviado por [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. Esto establece el estado del mensaje original y permite [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] para tomar medidas en función de ese estado. Sin conciliación, esto no sería posible. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]¿sabe que, correctamente (o sin éxito) envía el mensaje original a AAS y tendría la respuesta que recibió de AAS, que indica el estado de la transmisión, pero no sería capaz de realizar la conexión entre los dos. FRR establece esa conexión.  
  
 Las respuestas FIN son confirmaciones (ACK) o confirmaciones negativas (NAKs) enviadas por AAS a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)], o enviados por la red SWIFT a AAS y, a continuación, reenvía AAS a [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. La presencia o ausencia de dichas confirmaciones define el estado de negocios del mensaje. Puede supervisar este estado a través de informes de supervisión de la actividad económica (BAM).  
  
 También puede implementar un comportamiento de la aplicación personalizada alrededor de FRR. Un controlador personalizado puede implementar su propia lógica para controlar conjuntos conciliados de respuestas FIN. Para obtener un ejemplo de un controlador personalizado que procesa los mensajes que se correlacionan FRR con un mensaje MTS21_FIN_ACKNAK NAK, consulte [FRR NAK controlador ejemplo](../../adapters-and-accelerators/accelerator-swift/frr-nak-handler-sample.md).  
  
 La orquestación FRR se instala de forma predeterminada el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa de instalación. Es necesario para configurar el sistema FRR mediante la creación de una canalización de recepción, ubicaciones de recepción y puertos de envío. También debe configurar FRR para especificar cuánto tiempo debe esperar para NAKs diferidas y para las respuestas en general. Para obtener más información acerca de la administración y configuración de FRR, consulte [conciliación de respuesta de FIN de configurar](../../adapters-and-accelerators/accelerator-swift/configuring-fin-response-reconciliation.md) y [conciliación de respuesta de FIN de administrar](../../adapters-and-accelerators/accelerator-swift/administering-fin-response-reconciliation.md).  
  
 Esta sección contiene:  
  
-   [Tipos de respuesta FIN](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)  
  
-   [Procesamiento de FRR](../../adapters-and-accelerators/accelerator-swift/frr-processing.md)  
  
-   [Orquestación de FRR](../../adapters-and-accelerators/accelerator-swift/frr-orchestration.md)  
  
-   [FRR ubicación de recepción para los mensajes de la aplicación de Back-End](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-the-back-end-application.md)  
  
-   [Puerto de envío FRR mensajes SWIFT](../../adapters-and-accelerators/accelerator-swift/frr-send-port-for-messages-to-swift.md)  
  
-   [FRR ubicación de recepción para mensajes de SWIFT.](../../adapters-and-accelerators/accelerator-swift/frr-receive-location-for-messages-from-swift.md)  
  
-   [FRR puertos de envío de mensajes a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/frr-send-ports-for-messages-to-the-custom-handlers.md)  
  
-   [Control conciliado conjuntos de mensajes](../../adapters-and-accelerators/accelerator-swift/handling-reconciled-message-sets.md)