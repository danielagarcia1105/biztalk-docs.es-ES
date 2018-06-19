---
title: Arquitectura del adaptador de recepción de SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aca9b5ef1fd1130feeebad3ec6fdf072d3bf88d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224988"
---
# <a name="swift-receive-adapter-architecture"></a>Arquitectura del adaptador de recepción de SWIFT
En BizTalk Server, el adaptador de recepción se hospeda dentro de su propio espacio de memoria, lo que significa que se crea un proceso independiente para ejecutar el host. Este host se genera mediante la definición de un subsistema en la configuración de vínculo SWIFTNet (SNL).  
  
 El ejecutable del servidor se configura como un subsistema en la configuración de SNL (paramfile) y se genera al ejecutar el comando de inicio de SWIFTNet. Finaliza la aplicación de SNL server ejecutando el comando de detención de SWIFTNet. SNL administra la duración del ejecutable del servidor.  
  
> [!NOTE]
>  El escenario de oficina de servicio requiere que el adaptador para varios miembros SWIFT que se ejecuta en su propio contexto de seguridad del servicio. Esto puede admitirse mediante la configuración de un individuo ubicación por cada miembro y la creación de varias instancias del ejecutable del servidor de recepción, cada una de ellas dedicada a una ubicación de recepción.  
  
 En BizTalk Server, el adaptador de recepción admite los siguientes patrones de comunicación para interactuar con el motor de mensajería de BizTalk:  
  
-   Unidireccional: este modo es necesario cuando el adaptador de recepción (servidor) está funcionando en modo diferido. En el modo diferido, el adaptador envía una confirmación de forma predeterminada para los mensajes entrantes. Los valores predeterminados para la confirmación pueden configurarse en las propiedades del adaptador. Respuesta de nivel de negocio puede enviarse más tarde por la aplicación de LOB a través del adaptador de envío.  
  
    > [!NOTE]
    >  En el caso de modo diferido, todos los valores deben llenar en la configuración del adaptador, ya que el adaptador es la construcción de la respuesta.  
  
-   Solicitud-respuesta: en este modo, el adaptador envía la solicitud de SWIFT de BizTalk y espera respuesta. El adaptador de contar con tiempo de espera si no hay ninguna respuesta de la aplicación de LOB. El valor de tiempo de espera es configurable en configuración del adaptador. El valor predeterminado es 60 segundos.  
  
     El adaptador de recepción puede recibir la devolución de llamada de SNL solo en un subproceso. Esto significa que el adaptador de recepción puede recibir más mensajes de SNL solo después de enviar el primer mensaje. Por lo tanto, el tamaño del lote de forma predeterminada se establece en 1.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [URI del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [La inicialización del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [Contexto de seguridad del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [Modos sincrónico y diferido del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [Adaptador de almacenamiento y reenvío de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)