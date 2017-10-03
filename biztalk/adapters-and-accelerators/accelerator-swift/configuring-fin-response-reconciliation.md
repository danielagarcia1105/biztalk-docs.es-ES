---
title: "Configuración de conciliación de respuesta FIN | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring
- configuring, FIN Response Reconciliation
ms.assetid: dc934530-76ff-4cdb-b182-46f9ea0343b7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 384a2ea27e3d208864c8b16ec52562e6e1cfa28e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fin-response-reconciliation"></a>Configuración de conciliación de respuesta FIN
Debe realizar los pasos en las secciones siguientes para configurar el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] característica Conciliación de respuesta de FIN (FRR), tal como se muestra en la ilustración siguiente.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-frr-configuration.jpg "A4SWIFT_FRR_Configuration")  
  
 En el Asistente para la instalación de A4SWIFT, puede elegir instalar reparación de mensajes y nuevo envío y FRR, o reparación de mensajes y nuevo envío sin FRR o FRR sin reparación de mensajes y nuevo envío. Como resultado, las instrucciones de esta sección no se da por supuesto que está instalando y configurando la reparación de mensajes y nuevo envío. , Sin embargo, se da por supuesto que ha llevado a cabo los pasos descritos en la [configurar el tiempo de ejecución de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/configuring-the-a4swift-runtime.md).  
  
 Esta sección contiene:  
  
-   [Enlazar e iniciar la orquestación FRR](../../adapters-and-accelerators/accelerator-swift/binding-and-starting-the-frr-orchestration.md)  
  
-   [Crear el FRR la canalización de recepción](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-pipeline.md)  
  
-   [Crear la FRR ubicación de recepción para recibir de la aplicación de Back-End](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-the-back-end-application.md)  
  
-   [Crear la FRR ubicación de recepción para la recepción de SWIFT.](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-receive-location-for-receiving-from-swift.md)  
  
-   [Crear la canalización de envío FRR](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-pipeline.md)  
  
-   [Crear el puerto de envío FRR para enviar para SWIFT](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-port-for-sending-to-swift.md)  
  
-   [Creación de los puertos de envío FRR para enviar a los controladores personalizados](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)