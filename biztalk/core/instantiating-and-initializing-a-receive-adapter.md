---
title: "Crear instancias e inicializar un adaptador de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 565712faecf11b728c4f552798b1e3daebf962f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>Crear instancias e inicializar un adaptador de recepción
Inmediatamente después de que se hayan creado instancias de un adaptador de recepción, el motor de mensajería lo inicializa, el motor llama a QueryInteraface para IBTTransportControl. A continuación, llama a IBTTransportControl**. Inicializar** pasando proxy de transporte del adaptador, que conserva el adaptador en una variable miembro. A continuación, el motor llama **QueryInterface** para **IPersistPropertyBag**. Se trata de una interfaz opcional; Si el adaptador la implementa, la configuración del controlador se pasa al adaptador en la **carga** llamada al método. La última fase de la inicialización de un adaptador de recepción implica pasar la configuración del extremo al adaptador. Durante esta fase el motor llama **IBTTransportConfig.AddReceiveEndpoint** una vez para cada extremo activo, pasando el URI para el punto de conexión, la configuración específica del adaptador para el punto de conexión y la configuración de BizTalk para ese extremo.  
  
 La ilustración siguiente muestra esta secuencia de llamadas a la API. El adaptador implementa las interfaces que se muestran en azul.  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **Sugerencia para la implementación:** en general, adaptadores no deberían bloquear el motor de mensajería en las llamadas como **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**y **IBTTransportConfig.AddReceiveEndpoint**. Realizar un procesamiento excesivo en estas llamadas puede tener un efecto negativo en el tiempo de inicio del servicio.  
  
 En el inicio del servicio se crean todos los adaptadores de recepción que tienen una ubicación de recepción asociada o más. Todos los adaptadores de recepción son asíncronos y admiten el procesamiento por lotes. Pueden estar en curso o aislados. Para obtener información adicional acerca de las variables del adaptador de recepción, vea [Variables de adaptador](../core/adapter-variables.md).