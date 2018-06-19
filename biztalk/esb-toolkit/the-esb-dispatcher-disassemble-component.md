---
title: El distribuidor ESB desensamblar componente | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1f5e46b-8f41-47f8-b22b-b9e9eaac6475
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c846ca716aef72d43e4f4a6ed75a2b20a81c351a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294692"
---
# <a name="the-esb-dispatcher-disassemble-component"></a><span data-ttu-id="9d61e-102">El distribuidor ESB desensamblar componente</span><span class="sxs-lookup"><span data-stu-id="9d61e-102">The ESB Dispatcher Disassemble Component</span></span>
<span data-ttu-id="9d61e-103">El componente de distribuidor de ESB desensamblar puede establecer dinámicamente las propiedades de la ubicación de punto de conexión para los mensajes salientes de forma similar para el componente de distribuidor.</span><span class="sxs-lookup"><span data-stu-id="9d61e-103">The ESB Dispatcher Disassemble component can dynamically set endpoint location properties for outbound messages in a similar way to the Dispatcher component.</span></span> <span data-ttu-id="9d61e-104">Este componente de canalización combina el procesamiento por lotes funcionalidad de mensaje de BizTalk de Microsoft (heredando de la clase de desensamblador XML denominado **XmlDasmComp**) con el mecanismo que se puede ejecutar itinerario ESB de envío de mensajes Servicios de mensajería en una canalización de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9d61e-104">This pipeline component combines Microsoft BizTalk message de-batching functionality (by inheriting from the XML disassembler class named **XmlDasmComp**) with the message dispatching mechanism that can execute ESB itinerary messaging services in a BizTalk pipeline.</span></span>