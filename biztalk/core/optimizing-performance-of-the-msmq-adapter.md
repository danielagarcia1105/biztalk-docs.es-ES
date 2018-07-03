---
title: Optimizar el rendimiento del adaptador de MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729aaddba023d854d7ecfeb5644357f2383bc6b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011589"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a>Optimizar el rendimiento del adaptador de MSMQ
La optimización del adaptador de MSMQ no es la misma para envío y para recepción. Para la recepción, la optimización se controla definiendo una propiedad en la ubicación de recepción. Para el envío, la optimización puede controlarse mediante una orquestación.  
  
## <a name="receive-optimization"></a>Optimización de recepción  
 En el caso de la recepción, el adaptador puede utilizar un único subproceso de ejecución. Si el adaptador utiliza un único subproceso o varios subprocesos depende de la configuración de la **procesamiento ordenado** propiedad en la ubicación de recepción, como se indica a continuación:  
  
- Cuando la propiedad es **True**, el adaptador opera en un único subproceso. Esto limita el adaptador a un solo mensaje a la vez y permite ahorrar memoria. Tenga en cuenta que esto se define eficazmente **tamaño de lote** a uno (1), independientemente del valor asignado en la hoja de propiedades.  
  
- Cuando **procesamiento ordenado** es **False**, el adaptador ejecuta varios subprocesos y puede procesar varios mensajes a la vez, incrementando así el rendimiento.  
  
  Debe establecer **procesamiento ordenado** a **True** si coloca una prima sobre la administración de recursos del servidor, o si el número o tamaño de los mensajes pudiese agotar la memoria disponible.  
  
  También puede controlar el uso de memoria al reducir el valor de **tamaño de lote** en la ubicación de recepción. Cuanto más pequeño sea el tamaño del lote, menor número de mensajes se guardará en memoria, lo que implica un menor consumo de memoria.  
  
  La colocación de los puertos de envío y de las ubicaciones de recepción en equipos distintos también permite reducir el consumo de memoria.  
  
## <a name="send-optimization"></a>Optimización de envío  
 En el caso de los envíos, el procesamiento de un solo mensaje se consigue utilizando la orquestación de ejemplo. La orquestación de ejemplo envía un solo mensaje y espera a recibir la confirmación para enviar el mensaje siguiente. Para obtener más información, consulte [cómo crear ubicaciones de recepción de MSMQ y los puertos de envío desde el código](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md).  
  
## <a name="remote-transactional-read-operations"></a>Operaciones de lectura transaccionales remotas  
 Con MSMQ de BizTalk Server es capaz de realizar operaciones de lectura remotas desde colas MSMQ transaccionales adaptador.  Esto se debe a que MSMQ 4.0 y las versiones posteriores admiten operaciones de lectura remotas transaccionales.  Sin embargo, las operaciones de lectura transaccionales suelen ser operaciones lentas. Para optimizar el rendimiento, se deben usar únicamente cuando no hay ninguna otra opción.  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar ubicación de recepción de MSMQ](../core/how-to-configure-an-msmq-receive-location.md)   
 [Cómo configurar un puerto de envío MSMQ](../core/how-to-configure-an-msmq-send-port.md)   
 [Configuración del adaptador de MSMQ](../core/configuring-the-msmq-adapter.md)