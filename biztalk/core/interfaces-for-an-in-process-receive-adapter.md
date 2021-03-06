---
title: Interfaces para un proceso en el adaptador de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ed668d9-7512-4026-a8f3-df05aeed4df6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d608f9e511b1a3cb0ba94f30fbe3cd1eb7c9e87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965869"
---
# <a name="interfaces-for-an-in-process-receive-adapter"></a>Interfaces de un adaptador de recepción de tipo En curso
El motor de mensajería crea instancias y configura los adaptadores de tipo En curso, pasando el proxy de transporte para permitir que el adaptador tenga acceso a su funcionalidad. Para habilitar la configuración y el enlace al proxy de transporte, los adaptadores deben implementar las interfaces de configuración siguientes:  
  
- **IBTTransport**  
  
- **IBTTransportControl**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
  Opcionalmente, si el adaptador desea recibir información del controlador durante la inicialización, tiene que implementar **IPersistPropertyBag**.  
  
  El motor de mensajería crea una instancia de un adaptador, lo inicializa y establece la configuración de las ubicaciones de recepción. El motor de mensajería se pasa una bolsa de propiedades a un adaptador en el **AddReceiveEndpoint** llamada al método. La bolsa de propiedades contiene la configuración de la ubicación de recepción y del controlador de recepción. La configuración se almacena en la base de datos en forma de bolsa de propiedades de estilo XML. El motor de mensajería lee el XML y rehidrata una bolsa de propiedades desde el XML. Después de que se agregue un extremo (ubicación de recepción) como mínimo, el adaptador puede comenzar a enviar mensajes.  
  
> [!NOTE]
>  Los adaptadores deben no bloque motor de mensajería llama como **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, y **IBTTransportConfig.AddReceiveEndpoint**. La realización de un procesamiento excesivo en estas llamadas afectará al tiempo de inicio del servicio.  
  
 La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción de tipo En curso.  
  
 ![](../core/media/ebiz-sdk-devadapter11.gif "ebiz_sdk_devadapter11")  
Flujo de trabajo correspondiente a un adaptador de recepción de tipo En curso  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md)   
 [Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [Adaptador de recepción de las interfaces para un aislado](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [Interfaces para admite lote del adaptador de recepción](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [Interfaces para un transaccional compatible con lotes del adaptador de recepción](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [Interfaces para un adaptador de recepción sincrónico de solicitud-respuesta](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)