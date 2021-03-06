---
title: Adaptador de recepción de las interfaces para un aislado | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c6b195e-76bf-4c3e-a324-5513bc24fed1
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 129a0d16100ed7f38f49d0cfa5cc329446c3e72e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997189"
---
# <a name="interfaces-for-an-isolated-receive-adapter"></a>Interfaces de un adaptador de recepción aislado
Aisladas de recepción adaptadores se hospedan en un espacio de proceso distinta la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso. Para interactuar con el motor de mensajería, un adaptador de recepción aislado se registra a sí mismo en el inicio de modo que el motor pueda configurarlo y controlarlo. El adaptador crea el proxy de transporte, las consultas para la interfaz **IBTTransportProxy**y llama a **IBTTransportProxy.RegisterIsolatedReceiver** para registrar su  **IBTTransportConfig** interfaz de devolución de llamada con el motor de mensajería. Esta llamada sincrónica se produce antes de que el adaptador envía su primer mensaje a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto permite que el motor de mensajería devuelva la llamada al adaptador y le indique qué extremos están activos y en cuáles hay que escuchar los mensajes entrantes. Los adaptadores aislados deben implementar las interfaces siguientes:  
  
- **IBTTransport**  
  
- **IBTTransportConfig**  
  
- **IBaseComponent**  
  
- **IPersistPropertyBag**  
  
  Para registrar el adaptador, es necesario que el adaptador pase una ubicación de recepción configurada y habilitada. El proceso del host del adaptador debe ser miembro del grupo Usuarios de hosts aislados de BizTalk. Además, se consulta el adaptador para garantizar que tiene el Id. de clase correcto y que se está ejecutando en el equipo configurado para dicha instancia de host.  
  
  Cuando el adaptador haya registrado correctamente con el proxy de transporte, el motor de mensajería pasa la información de configuración y la otra ubicaciones al adaptador de recepción mediante una llamada a la **carga** método de la  **IPersistPropertyBag** interfaz y la **AddReceiveEndpoint** método de la **IBTTransportConfig** interfaz respectivamente.  
  
  Cuando reciba un aislado adaptador finaliza el procesamiento de mensajes y se va a terminar, debe llamar a la **TerminateIsolatedReceiver** método de la **IBTTransportProxy** interfaz.  
  
  La ilustración siguiente muestra las interacciones de objetos implicadas en la creación de un adaptador de recepción aislado.  
  
  ![](../core/media/ebiz-sdk-devadapter9.gif "ebiz_sdk_devadapter9")  
  Flujo de trabajo correspondiente a la inicialización de un adaptador de recepción aislado  
  
> [!NOTE]
>  Se recomienda que el adaptador de realizar un seguimiento de las solicitudes en ejecución a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El adaptador debe bloquear la **Terminate** método hasta que llegue a cero el recuento del trabajo. En el lado de recepción, este trabajo incluye cualquier solicitud pendiente que no se han publicado en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Tenga en cuenta que los mensajes de respuesta no suelen entregarse a un adaptador de recepción después de **Terminate** se llama. En general, tras el adaptador llama a la **Terminate** método, el motor de mensajería no acepta solicitudes para publicar nuevos mensajes, con excepción de los mensajes de respuesta para los pares petición-respuesta.  
> 
> [!NOTE]
>  Un proceso puede alojar varias instancias de adaptadores aislados, mientras que un proceso puede alojar un adaptador.  
  
## <a name="see-also"></a>Vea también  
 [Variables de adaptador](../core/adapter-variables.md)   
 [Desarrollar un adaptador de recepción](../core/developing-a-receive-adapter.md)   
 [Crear instancias e inicializar un adaptador de recepción](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [Interfaces para un proceso en el adaptador de recepción](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [Interfaces para admite lote del adaptador de recepción](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [Interfaces para un transaccional compatible con lotes del adaptador de recepción](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)   
 [Interfaces para un adaptador de recepción sincrónico de solicitud-respuesta](../core/interfaces-for-a-synchronous-request-response-receive-adapter.md)