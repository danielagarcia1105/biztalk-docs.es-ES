---
title: "¿Qué es el adaptador de MQSeries? | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f72d0012050fc8022b53120377aeb648641d21f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-mqseries-adapter"></a>¿Qué es el adaptador de MQSeries?
El adaptador de MQSeries permite enviar y recibir mensajes a sistemas de MQSeries mediante Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 El adaptador funciona con MQSeries Server para Windows. Este diseño garantiza un servicio de mensajería confiable, pues MQSeries Server para Windows es compatible con el Coordinador de transacciones distribuidas de Microsoft (MSDTC).  
  
 El adaptador admite servidores MQSeries y administradores de cola de MQSeries agrupados, así como servidores de BizTalk.  
  
 El adaptador de MQSeries permite hacer lo siguiente:  
  
-   Enviar mensajes a colas de definición remota, colas locales, colas de transmisión y colas de alias de MQSeries desde BizTalk Server.  
  
-   Recibir mensajes procedentes de colas de transmisión, colas locales y colas de alias de MQSeries.  
  
-   Enviar y recibir mensajes desde MQSeries Server para Windows (MQSeries Server puede ejecutarse en el mismo equipo que BizTalk Server, o bien en una instalación remota). Sólo tendrá que implementar una copia de MQSAgent (el componente COM+ del adaptador) como base para todas las instalaciones de BizTalk Server.  
  
-   Realizar sondeos de MQSeries Server con un intervalo de espera.  
  
-   Utilizar puertos de envío dinámicos para controlar el adaptador.  
  
-   Crear colas de forma dinámica en tiempo de ejecución  
  
-   Recibir dinámicamente los mensajes procedentes de colas basadas en MQSeries MatchOptions.  
  
-   Asignar propiedades de contexto a propiedades de encabezado para la transmisión y recepción de mensajes. Se pueden obtener y definir propiedades de encabezado de MQSeries (incluidas MQMD, MQXQH, MQCIH y MQIIH) mediante propiedades de contexto de BizTalk Server.  
  
-   Habilitar la correlación con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o MQSeries Server mediante la creación del identificador de correlación.  
  
-   Solicitar la entrega transaccional y no transaccional de mensajes para envío y recepción.  
  
> [!NOTE]
>  Cuando se usan características como MQSeries que hacen llamadas del Modelo de objetos componentes distribuido (DCOM) al servidor, asegúrese de que no tiene un servidor de seguridad con NAT (Traducción de direcciones de red) habilitado. El cliente debe poder obtener acceso al servidor mediante su dirección IP real y los servidores de seguridad con NAT traducen esta dirección en algo que el cliente no reconoce.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Componentes del adaptador de MQSeries](../core/components-of-the-mqseries-adapter.md)  
  
-   [Arquitectura del adaptador de MQSeries](../core/mqseries-adapter-architecture.md)  
  
-   [Uso del adaptador de MQSeries](../core/using-the-mqseries-adapter.md)  
  
-   [Seguridad del adaptador de MQSeries](../core/mqseries-adapter-security.md)