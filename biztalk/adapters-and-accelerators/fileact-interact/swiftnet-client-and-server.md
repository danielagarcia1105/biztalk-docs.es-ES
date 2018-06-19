---
title: Servidor y cliente SWIFTNet | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ea3a1b974a26f90d03bb65675c1c4e8966720f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224660"
---
# <a name="swiftnet-client-and-server"></a>SWIFTNet cliente y servidor
SWIFT utiliza los términos cliente y servidor para describir el envío y recepción. Un cliente SWIFT es un proceso que llama el vínculo de SWIFTNet (SNL) para iniciar la comunicación a través de SWIFTNet. En BizTalk Server, esto se denomina el adaptador de envío. Un servidor de SWIFT es un programa que llama a la SNL al tráfico entra a través de SWIFTNet. En BizTalk Server, esto se denomina el adaptador de recepción.  
  
 No confunda el cliente SWIFT y el servidor con el cliente empresarial y el servidor. Por ejemplo, un cliente (organización) se basa en los servicios proporcionados por un servidor (organización). Si desea que el servidor (organización) iniciar una comunicación con el cliente (organización), debe usar una aplicación de cliente SNL para hacerlo y el cliente (organización) debe tener una aplicación de servidor SNL para recibir el tráfico entrante. Esto se describe en la siguiente ilustración.  
  
 ![Relación SWIFTNet entre el cliente y servidor](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")  
  
 SNL se da por supuesto que las aplicaciones cliente y servidor son archivos ejecutables que se inicia desde la línea de comandos. Ambos se vinculan a la DLL de API de SNL, que se comunica con el proceso de instancia real de SNL.  
  
## <a name="snl-client-applications"></a>Aplicaciones de cliente SNL  
 Las aplicaciones de cliente SNL se basan en la API de SwCall se describe a continuación. Técnicamente hablando, una aplicación cliente típica se puede describir como sigue:  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 Cliente SNL aplicaciones deben ejecutarse en un proceso dedicado, porque SNL hace referencia al contexto de cliente por Id. de proceso SNL sincroniza las llamadas que utilizan recursos Tuxedo SwCall. Como resultado, solo un subproceso de cliente único a la vez puede ejecutar de manera eficaz un SwCall.  
  
 El cliente admite el modo de comunicación sincrónica. Esto significa que la rentabilidad de la SWCall se produce cuando vuelve la respuesta del servidor. El siguiente SwCall puede realizarse después de esta devolución.  
  
## <a name="snl-server-applications"></a>Aplicaciones de SNL server  
 Las aplicaciones de servidor SNL son ligeramente más complejas que las aplicaciones cliente. Las aplicaciones de servidor registrar las funciones de devolución de llamada antes de realizar una llamada de bloqueo en la DLL de SNL. Técnicamente hablando, una aplicación de servidor típicos se puede describir como sigue:  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 La aplicación de servidor puede llamar a la API SwCall mientras se encuentra en la función de devolución de llamada. En algunos casos, debe llamar a SwCall para poder generar el resultado deseado o respuesta. Sin embargo, una aplicación de servidor nunca puede iniciar una comunicación a través de la red. Una aplicación de servidor nunca puede ser una aplicación cliente.  
  
 En la ilustración siguiente, la llamada con la etiqueta **inicializar** es una abstracción para el proceso de inicialización de la API de SNL, que requiere varias llamadas. La llamada con la etiqueta **SwCallback()** se repetirá varias veces, y la etiqueta de la llamada **SwCall()** es opcional.  
  
 ![Funcionalidad de SNL Server](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")  
  
 Todas las llamadas entre el servidor y la DLL de la API de SNL son llamadas a funciones sincrónicas convención de llamada estándar de C++.  
  
## <a name="see-also"></a>Vea también  
 [Descripción de FileAct e interactuar de arquitectura de adaptador](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)   
 [Arquitectura del adaptador de envío SWIFT](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)   
 [Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)