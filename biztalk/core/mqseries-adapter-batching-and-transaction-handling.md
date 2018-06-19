---
title: MQSeries control de transacciones y procesamiento por lotes de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- transactions, MQSeries adapters
- MQSeries adapters, transactions
- MQSeries adapters, IBM WebSphere MQ queues
- MQSeries adapters, batching
- batching, MQSeries adapters
ms.assetid: 2e43fca9-acbd-4fd3-8df3-5f7398553830
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffcdec02c464b9398acbece35657e0c3d1dc4432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262988"
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a>Control de transacciones y procesamiento por lotes del adaptador de MQSeries
El adaptador de MQSeries detiene una transacción sólo si no recibe todos los datos. Los límites de una transacción para el adaptador son el extremo del adaptador (cola de MQSeries en el servidor MQSeries) y la base de datos de cuadro de  mensajes.  
  
 Si la aplicación de BizTalk invalida un mensaje, el adaptador mueve el mensaje a la cola de suspensión. No obstante, puesto que aun entonces es una transacción válida desde el punto de vista del adaptador (el adaptador recibió todos los datos), el adaptador confirma la transacción.  
  
 Se puede controlar el tratamiento de transacciones y procesamiento por lotes estableciendo propiedades al configurar el adaptador. Para obtener más información, consulte [configurar el adaptador de MQSeries](../core/configuring-the-mqseries-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Propiedades del adaptador de MQSeries](../core/mqseries-adapter-properties.md)