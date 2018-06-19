---
title: Los componentes de interoperabilidad de canalización ESB | Documentos de Microsoft
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
ms.openlocfilehash: ccf4d4353e6928b998d31e8096ee642cd80bb60a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294132"
---
# <a name="esb-pipeline-interop-components"></a><span data-ttu-id="63562-102">Componentes de interoperabilidad de canalización ESB</span><span class="sxs-lookup"><span data-stu-id="63562-102">ESB Pipeline Interop Components</span></span>
<span data-ttu-id="63562-103">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] proporciona compatibilidad con componentes y servicios, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="63562-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides support components and services, including the following:</span></span>  
  
-   <span data-ttu-id="63562-104">**Componentes de canalización JMS.**</span><span class="sxs-lookup"><span data-stu-id="63562-104">**JMS pipeline components.**</span></span> <span data-ttu-id="63562-105">Estos componentes reconocerán, validar y exponen los metadatos y el contenido de los mensajes que se ajusta al formato de JMS MQRFH2 utilizado por los sistemas de mensajería de IBM MQ Series.</span><span class="sxs-lookup"><span data-stu-id="63562-105">These components recognize, validate, and expose metadata and the content of messages that conform to the JMS MQRFH2 format used by IBM MQ Series messaging systems.</span></span> <span data-ttu-id="63562-106">Esta funcionalidad permite un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] aplicación para recibir mensajes desde y enviar mensajes a sistemas JMS en MQ Series.</span><span class="sxs-lookup"><span data-stu-id="63562-106">This functionality allows a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] application to receive messages from and send messages to JMS systems over MQ Series.</span></span> <span data-ttu-id="63562-107">Los componentes automáticamente promoción la información de encabezado en y disminuir el nivel del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="63562-107">The components automatically promote header information into, and demote it from, the message content.</span></span>  
  
-   <span data-ttu-id="63562-108">**Componentes de canalización de Namespace.**</span><span class="sxs-lookup"><span data-stu-id="63562-108">**Namespace pipeline components.**</span></span> <span data-ttu-id="63562-109">Estos componentes pueden agregar o quitar espacios de nombres en el contenido de los mensajes XML.</span><span class="sxs-lookup"><span data-stu-id="63562-109">These components can add or remove namespaces in the content of XML messages.</span></span> <span data-ttu-id="63562-110">Esto permite a las aplicaciones reparar los espacios de nombres en conflicto o agregar espacios de nombres que faltan para evitar conflictos de espacio de nombres dentro de las orquestaciones de aplicación y de base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="63562-110">This allows applications to repair conflicting namespaces or add missing namespaces to prevent namespace collisions within the Message Box database and application orchestrations.</span></span> <span data-ttu-id="63562-111">Los componentes también permiten que el servidor BizTalk Server consumir POX (Plain Old XML) sin modificar de sistemas externos de publicación.</span><span class="sxs-lookup"><span data-stu-id="63562-111">The components also allow BizTalk Server to consume POX (Plain Old XML) without modifying external publishing systems.</span></span>  
  
 <span data-ttu-id="63562-112">Para obtener más información acerca de los componentes de canalización ESB, consulte [con los componentes de compatibilidad de canalización](../esb-toolkit/using-the-pipeline-support-components.md).</span><span class="sxs-lookup"><span data-stu-id="63562-112">For more information about the ESB pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>