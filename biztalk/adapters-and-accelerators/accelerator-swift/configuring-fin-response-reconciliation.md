---
title: Configuración de conciliación de respuestas de FIN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f2260c8e6096e2bef926fea45aaf778f4bdfa3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997909"
---
# <a name="configuring-fin-response-reconciliation"></a>Configuración de conciliación de respuestas de FIN
Debe realizar los pasos en las secciones siguientes para configurar Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] característica de conciliación de respuesta de FIN (FRR), tal como se muestra en la ilustración siguiente.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 En el Asistente para instalación de A4SWIFT, puede elegir instalar reparación de mensajes y nuevo envío y FRR, o reparación de mensajes y nuevo envío sin FRR o FRR sin reparación de mensajes y nuevo envío. Como resultado, las instrucciones de esta sección no suponen que está instalando y configurando la reparación de mensajes y nuevo envío. Sin embargo,, suponga que ha realizado los pasos descritos en la [configurar el tiempo de ejecución de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).  
  
 Esta sección contiene:  
  
-   [Enlace e inicio de la orquestación de FRR](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [Creación de la canalización de recepción de FRR](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [Creación de la ubicación de recepción de FRR para recibir de la aplicación back-end](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [Creación de la ubicación de recepción de FRR para recibir de SWIFT](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [Creación de la canalización de envío de FRR](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [Creación del puerto de envío de FRR para enviar a SWIFT](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [Creación de los puertos de envío de FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)