---
title: Creación de puertos y hosts HTTP de PeopleSoft | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d991642b45a636c50ea12148d07efd8b93917754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997165"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a>Creación de puertos y hosts HTTP de PeopleSoft
La arquitectura de publicación de mensajes en PeopleSoft se conoce como Integration Broker. Los componentes principales de Integration Broker son:  
  
- Puerta de enlace  
  
- Nodo de publicación  
  
- Nodo de suscriptor  
  
  Los tres funcionan conjuntamente para publicar un mensaje en una dirección URL para una escucha HTTP. Debe configurar el nodo de publicación. PeopleSoft tiene un nodo de publicación predeterminad, conocido también como nodo de mensaje local. Debe activar el nodo y las transacciones para el nodo de publicación. Debe configurar el nodo de suscripción con el tipo como nodo externo y, a continuación, activar el nodo y las transacciones. Para este nodo, también configura el tipo para que sea HTTP, y configura la información de conexión.  
  
  Para crear un host y un puerto HTTP de PeopleSoft donde PeopleSoft envíe los eventos, se usa PeopleSoft Integration Broker. Asegúrese de que el mensaje esté activo y enrutado mediante el procedimiento descrito en [cómo comprobar el estado de actividad de un mensaje](../core/how-to-verify-activity-status-of-a-message.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo comprobar el estado de actividad de un mensaje](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [Cómo configurar la puerta de enlace de integración y el conector de salida HTTP](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [Cómo crear un nuevo nodo de puerta de enlace](../core/how-to-create-a-new-gateway-node.md)  
  
-   [Cómo agregar una transacción](../core/how-to-add-a-transaction.md)  
  
-   [Cómo probar el nodo HTTP](../core/how-to-test-the-http-node.md)