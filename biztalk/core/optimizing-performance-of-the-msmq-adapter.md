---
title: Optimizar el rendimiento del adaptador de MSMQ | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e554de9b00869db4a258f03984fe1ebc71e99c38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a>Optimizar el rendimiento del adaptador de MSMQ
La optimización del adaptador de MSMQ no es la misma para envío y para recepción. Para la recepción, la optimización se controla definiendo una propiedad en la ubicación de recepción. Para el envío, la optimización puede controlarse mediante una orquestación.  
  
## <a name="receive-optimization"></a>Optimización de recepción  
 En el caso de la recepción, el adaptador puede utilizar un único subproceso de ejecución. Si el adaptador utiliza un único subproceso o varios subprocesos depende del valor de la **procesamiento ordenado** propiedad en la ubicación de recepción, como se indica a continuación:  
  
-   Cuando la propiedad es **True**, el adaptador funciona en un solo subproceso. Esto limita el adaptador a un solo mensaje a la vez y permite ahorrar memoria. Tenga en cuenta que este procedimiento define **tamaño de lote** a uno (1), independientemente del valor asignado a él en la hoja de propiedades.  
  
-   Cuando **procesamiento ordenado** es **False**, el adaptador ejecuta varios subprocesos y puede procesar varios mensajes a la vez, incrementando así el rendimiento.  
  
 Debe establecer **procesamiento ordenado** a **True** si desea limitar sobre la administración de recursos del servidor, o si el número o el tamaño de los mensajes pudiese agotar la memoria disponible.  
  
 También puede controlar el uso de memoria si reduce el valor de **tamaño de lote** en la ubicación de recepción. Cuanto más pequeño sea el tamaño del lote, menor número de mensajes se guardará en memoria, lo que implica un menor consumo de memoria.  
  
 La colocación de los puertos de envío y de las ubicaciones de recepción en equipos distintos también permite reducir el consumo de memoria.  
  
## <a name="send-optimization"></a>Optimización de envío  
 En el caso de los envíos, el procesamiento de un solo mensaje se consigue utilizando la orquestación de ejemplo. La orquestación de ejemplo envía un solo mensaje y espera a recibir la confirmación para enviar el mensaje siguiente. Para obtener más información, consulte [cómo crear ubicaciones de recepción de MSMQ y puertos de envío desde el código](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).  
  
## <a name="remote-transactional-read-operations"></a>Operaciones de lectura transaccionales remotas  
 Con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], el adaptador de MSMQ puede realizar operaciones de lectura remotas desde colas MSMQ transaccionales.  Esto se debe a que MSMQ 4.0 y las versiones posteriores admiten operaciones de lectura remotas transaccionales.  Sin embargo, las operaciones de lectura transaccionales suelen ser operaciones lentas. Para optimizar el rendimiento, se deben usar únicamente cuando no hay ninguna otra opción.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md)   
 [Cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md)   
 [Configurar el adaptador MSMQ](../core/configuring-the-msmq-adapter.md)