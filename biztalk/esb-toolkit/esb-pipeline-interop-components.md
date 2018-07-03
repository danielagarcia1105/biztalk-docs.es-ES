---
title: Los componentes de interoperabilidad de canalización ESB | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25f9fb9d-d3d4-4df8-8e81-38b432f42ccf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 794ce6407d10fc820444384550357f10d24f7723
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024250"
---
# <a name="esb-pipeline-interop-components"></a><span data-ttu-id="e671f-102">Componentes de interoperabilidad de canalización ESB</span><span class="sxs-lookup"><span data-stu-id="e671f-102">ESB Pipeline Interop Components</span></span>
<span data-ttu-id="e671f-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona componentes de soporte técnico y servicios, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e671f-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides support components and services, including the following:</span></span>  
  
- <span data-ttu-id="e671f-104">**Componentes de canalización JMS.**</span><span class="sxs-lookup"><span data-stu-id="e671f-104">**JMS pipeline components.**</span></span> <span data-ttu-id="e671f-105">Estos componentes reconocerán, validación y exponen los metadatos y el contenido de los mensajes que cumplen el formato de MQRFH2 de JMS usado por los sistemas de mensajería de IBM MQ Series.</span><span class="sxs-lookup"><span data-stu-id="e671f-105">These components recognize, validate, and expose metadata and the content of messages that conform to the JMS MQRFH2 format used by IBM MQ Series messaging systems.</span></span> <span data-ttu-id="e671f-106">Esta funcionalidad permite una [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] aplicación para recibir mensajes desde y enviar mensajes a sistemas JMS a través de MQ Series.</span><span class="sxs-lookup"><span data-stu-id="e671f-106">This functionality allows a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] application to receive messages from and send messages to JMS systems over MQ Series.</span></span> <span data-ttu-id="e671f-107">Los componentes automáticamente promoción la información de encabezado en y disminuir el nivel del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="e671f-107">The components automatically promote header information into, and demote it from, the message content.</span></span>  
  
- <span data-ttu-id="e671f-108">**Componentes de canalización de Namespace.**</span><span class="sxs-lookup"><span data-stu-id="e671f-108">**Namespace pipeline components.**</span></span> <span data-ttu-id="e671f-109">Estos componentes pueden agregar o quitar espacios de nombres en el contenido de los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="e671f-109">These components can add or remove namespaces in the content of XML messages.</span></span> <span data-ttu-id="e671f-110">Esto permite que las aplicaciones reparar los espacios de nombres en conflicto o agregar espacios de nombres que faltan para evitar conflictos de espacio de nombres dentro de las orquestaciones de aplicación y de base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="e671f-110">This allows applications to repair conflicting namespaces or add missing namespaces to prevent namespace collisions within the Message Box database and application orchestrations.</span></span> <span data-ttu-id="e671f-111">Los componentes también permiten a BizTalk Server consumir POX (Plain Old XML) sin modificar los sistemas externos de publicación.</span><span class="sxs-lookup"><span data-stu-id="e671f-111">The components also allow BizTalk Server to consume POX (Plain Old XML) without modifying external publishing systems.</span></span>  
  
  <span data-ttu-id="e671f-112">Para obtener más información acerca de los componentes de canalización ESB, consulte [mediante los componentes de soporte técnico de canalización](../esb-toolkit/using-the-pipeline-support-components.md).</span><span class="sxs-lookup"><span data-stu-id="e671f-112">For more information about the ESB pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>