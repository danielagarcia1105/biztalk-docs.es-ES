---
title: Crear instancias e inicializar un adaptador de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f14a6262a8f0ed816700f3e3c34307487874d25
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983341"
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a>Crear instancias e inicializar un adaptador de recepción
Inmediatamente después de que se hayan creado instancias de un adaptador de recepción, el motor de mensajería lo inicializa, el motor llama a QueryInteraface para IBTTransportControl. A continuación, llama a IBTTransportControl<strong>. Inicializar</strong> pasando el proxy de transporte del adaptador, que guarda el adaptador en una variable miembro. A continuación, el motor llama **QueryInterface** para **IPersistPropertyBag**. Se trata de una interfaz opcional; Si el adaptador la implementa, la configuración del controlador se pasa al adaptador en el **carga** llamada al método. La última fase de la inicialización de un adaptador de recepción implica pasar la configuración del extremo al adaptador. Durante esta fase el motor llama a **IBTTransportConfig.AddReceiveEndpoint** una vez para cada punto de conexión activo, pasando el URI para el punto de conexión, la configuración específica del adaptador para el punto de conexión y la configuración de BizTalk para ese punto de conexión.  
  
 La ilustración siguiente muestra esta secuencia de llamadas a la API. El adaptador implementa las interfaces que se muestran en azul.  
  
 ![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")  
  
 **Sugerencia para la implementación:** en general, los adaptadores deberían no bloquear el motor de mensajería en las llamadas como **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**y **IBTTransportConfig.AddReceiveEndpoint**. Realizar un procesamiento excesivo en estas llamadas puede tener un efecto negativo en el tiempo de inicio del servicio.  
  
 En el inicio del servicio se crean todos los adaptadores de recepción que tienen una ubicación de recepción asociada o más. Todos los adaptadores de recepción son asíncronos y admiten el procesamiento por lotes. Pueden estar en curso o aislados. Para obtener más información acerca de las variables de adaptador de recepción, vea [Variables de adaptador](../core/adapter-variables.md).