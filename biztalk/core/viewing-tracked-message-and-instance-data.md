---
title: Ver mensajes de seguimiento y datos de instancia | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, HAT
- HAT, about HAT
ms.assetid: e3cc7bef-90c7-4375-9f6c-7df00391132e
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592fa5c85913a69f4536055cdd790d638b15bc32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288220"
---
# <a name="viewing-tracked-message-and-instance-data"></a><span data-ttu-id="c9ac6-102">Visualización de datos de instancias y mensajes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c9ac6-102">Viewing Tracked Message and Instance Data</span></span>
<span data-ttu-id="c9ac6-103">Puede usar datos históricos y de seguimiento para ayudar a solucionar problemas de las aplicaciones de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-103">You can use historical and tracked data to help troubleshoot your BizTalk Server applications.</span></span> <span data-ttu-id="c9ac6-104">Por ejemplo, los administradores del sistema pueden usar datos históricos y de seguimiento para realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9ac6-104">For example, system administrators can use historical and tracked data to:</span></span>  
  
-   <span data-ttu-id="c9ac6-105">Ver los eventos de mensajes de seguimiento, las propiedades de mensajes y los cuerpos de mensajes en las distintas etapas del flujo de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-105">View tracked message events, message properties, and message bodies at various stages in a message’s flow.</span></span> <span data-ttu-id="c9ac6-106">Estos datos se pueden utilizar con fines de auditoría o de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-106">This data can be used for troubleshooting or auditing purposes.</span></span>  
  
-   <span data-ttu-id="c9ac6-107">Reproducir la ejecución de una instancia de orquestación específica.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-107">Replay the execution of a specific orchestration instance.</span></span>  
  
-   <span data-ttu-id="c9ac6-108">Hacer un seguimiento de los eventos que emiten reglas para reconstruir la secuencia de eventos en un punto posterior del tiempo.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-108">Track rule firing events to reconstruct the sequence of events at a later point in time.</span></span>  
  
-   <span data-ttu-id="c9ac6-109">Consultar mensajes mediante la especificación de criterios, tal como el esquema de mensaje y los pares propiedad o valor de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-109">Query for messages by specifying criteria such as message schema and message property/value pairs.</span></span> <span data-ttu-id="c9ac6-110">Por tanto, una vez ubicado el mensaje, los usuarios pueden determinar hasta qué punto ha progresado el mensaje en el flujo de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-110">Having thus located the message, users can determine the point in the message flow to which the message has progressed.</span></span> <span data-ttu-id="c9ac6-111">Los usuarios más avanzados también pueden crear consultas personalizadas de SQL Server para mensajes.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-111">Advanced users can also create custom SQL Server queries for messages.</span></span>  
  
-   <span data-ttu-id="c9ac6-112">Buscar datos archivados en una base de datos archivada.</span><span class="sxs-lookup"><span data-stu-id="c9ac6-112">Search for archived data in an archived database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9ac6-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c9ac6-113">In This Section</span></span>  
  
-   [<span data-ttu-id="c9ac6-114">Lista de comprobación: Seguimiento de datos de instancias y mensajes</span><span class="sxs-lookup"><span data-stu-id="c9ac6-114">Checklist: Message and Instance Data Tracking</span></span>](../core/checklist-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="c9ac6-115">Prácticas recomendadas para el seguimiento de datos de instancias y mensajes</span><span class="sxs-lookup"><span data-stu-id="c9ac6-115">Best Practices for Message and Instance Data Tracking</span></span>](../core/best-practices-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="c9ac6-116">Consideraciones de seguridad para el seguimiento de datos de instancias y mensajes</span><span class="sxs-lookup"><span data-stu-id="c9ac6-116">Security Considerations for Message and Instance Data Tracking</span></span>](../core/security-considerations-for-message-and-instance-data-tracking.md)  
  
-   [<span data-ttu-id="c9ac6-117">Comprender los datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c9ac6-117">Understanding Tracked Data</span></span>](../core/understanding-tracked-data.md)  
  
-   [<span data-ttu-id="c9ac6-118">Ver los datos históricos y de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c9ac6-118">Viewing Historical and Tracked Data</span></span>](../core/viewing-historical-and-tracked-data.md)  
  
-   [<span data-ttu-id="c9ac6-119">Cómo seleccionar un origen de datos activos o archivados</span><span class="sxs-lookup"><span data-stu-id="c9ac6-119">How to Select a Live or Archived Data Source</span></span>](../core/how-to-select-a-live-or-archived-data-source.md)  
  
-   [<span data-ttu-id="c9ac6-120">Cómo cambiar el valor de QueryTimeout de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c9ac6-120">How to Change the Tracking QueryTimeout Value</span></span>](../core/how-to-change-the-tracking-querytimeout-value.md)  
  
-   [<span data-ttu-id="c9ac6-121">Cómo guardar una consulta de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c9ac6-121">How to Save a Tracking Query</span></span>](../core/how-to-save-a-tracking-query.md)  
  
-   [<span data-ttu-id="c9ac6-122">Cómo abrir una consulta de seguimiento guardada</span><span class="sxs-lookup"><span data-stu-id="c9ac6-122">How to Open a Saved Tracking Query</span></span>](../core/how-to-open-a-saved-tracking-query.md)  
  
-   [<span data-ttu-id="c9ac6-123">Ver flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="c9ac6-123">Viewing Message Flow</span></span>](../core/viewing-message-flow.md)  
  
-   [<span data-ttu-id="c9ac6-124">Depuración de una orquestación</span><span class="sxs-lookup"><span data-stu-id="c9ac6-124">Debugging an Orchestration</span></span>](../core/debugging-an-orchestration.md)  
  
-   [<span data-ttu-id="c9ac6-125">Trabajar con la lista de resultados</span><span class="sxs-lookup"><span data-stu-id="c9ac6-125">Working with the Results List</span></span>](../core/working-with-the-results-list.md)