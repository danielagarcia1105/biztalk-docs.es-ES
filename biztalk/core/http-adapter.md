---
title: Adaptador de HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9be9fac6fdb65c4516c671b6c0e30096e83a27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256052"
---
# <a name="http-adapter"></a>Adaptador de HTTP
El adaptador de HTTP se emplea para intercambiar información entre Microsoft BizTalk Server y una aplicación por medio del protocolo HTTP. HTTP es el protocolo principal para el intercambio de mensajes entre empresas. Las aplicaciones pueden enviar mensajes a un servidor mediante el envío de solicitudes HTTP POST o HTTP GET a una dirección URL de HTTP concreta. El adaptador HTTP recibe solicitudes HTTP y las envía al servidor BizTalk Server para su procesamiento. Del mismo modo, BizTalk Server puede transmitir mensajes a aplicaciones remotas mediante el envío de solicitudes HTTP POST a una dirección URL de HTTP concreta.  
  
 El adaptador HTTP se compone de dos adaptadores: un adaptador de recepción y un adaptador de envío. El adaptador de recepción HTTP es una extensión de la Interfaz de programación de aplicaciones para servidores de Internet (ISAPI) de los Servicios de Internet Information Server de Microsoft (IIS) que aloja el proceso IIS y controla las ubicaciones de recepción que utilizan el adaptador de HTTP. El adaptador de envío de HTTP controla los puertos de envío que utilizan el adaptador de HTTP.  
  
 En esta sección se explica la compatibilidad con el procesamiento por lotes y el flujo de trabajo de los adaptadores de envío y recepción de HTTP.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Adaptador de recepción HTTP](../core/http-receive-adapter.md)  
  
-   [Adaptador de envío HTTP](../core/http-send-adapter.md)  
  
-   [Configurar el adaptador HTTP](../core/configuring-the-http-adapter.md)  
  
-   [Recomendaciones de seguridad del adaptador HTTP](../core/http-adapter-security-recommendations.md)