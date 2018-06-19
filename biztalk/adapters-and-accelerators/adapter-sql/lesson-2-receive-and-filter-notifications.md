---
title: 'Lección 2: Recibir y filtrar notificaciones | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5ec679c-1c67-4bf4-aa88-0787373343f5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f28d0479510078b3717d68f99976808ee19aa7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222556"
---
# <a name="lesson-2-receive-and-filter-notifications"></a><span data-ttu-id="625cf-102">Lección 2: Recibir y filtrar notificaciones</span><span class="sxs-lookup"><span data-stu-id="625cf-102">Lesson 2: Receive and Filter Notifications</span></span>
<span data-ttu-id="625cf-103">En esta lección, empezar a crear una orquestación que recibe las notificaciones de cambios en el **empleado** tabla.</span><span class="sxs-lookup"><span data-stu-id="625cf-103">In this lesson, you start creating an orchestration that receives notifications for changes to the **Employee** table.</span></span> <span data-ttu-id="625cf-104">Una vez que la orquestación recibe la notificación, extrae el tipo de notificación y si el tipo de notificación es para una operación de inserción en el **empleado** tabla, una condición "if" se usa para realizar las tareas subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="625cf-104">After the orchestration receives the notification, it extracts the type of notification and if the notification type is for an Insert operation on the **Employee** table, an “if” condition is used to perform subsequent tasks.</span></span> <span data-ttu-id="625cf-105">En esta lección, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="625cf-105">In this lesson, you will perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="625cf-106">Agregar un unidireccional puerto de recepción y un **recepción** forma a la orquestación para recibir el mensaje de notificación.</span><span class="sxs-lookup"><span data-stu-id="625cf-106">Add a one-way receive port and a **Receive** shape to the orchestration to receive the notification message.</span></span>  
  
2.  <span data-ttu-id="625cf-107">Agregar un **expresión** forma que contenga una consulta xpath para extraer el tipo de notificación.</span><span class="sxs-lookup"><span data-stu-id="625cf-107">Add an **Expression** shape that contains an xpath query to extract the type of notification.</span></span>  
  
3.  <span data-ttu-id="625cf-108">Después de que se conoce el tipo de notificación, agregar un filtro a la orquestación mediante la inclusión de un **decidir** forma.</span><span class="sxs-lookup"><span data-stu-id="625cf-108">After the notification type is known, add a filter to the orchestration by including a **Decide** shape.</span></span> <span data-ttu-id="625cf-109">Esta forma se decide si la notificación es para una notificación de inserción y, a continuación, realiza las operaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="625cf-109">This shape decides whether the notification is for an Insert notification and then performs subsequent operations.</span></span> <span data-ttu-id="625cf-110">Si la notificación no es para una operación de inserción, la orquestación no hace nada.</span><span class="sxs-lookup"><span data-stu-id="625cf-110">If the notification is not for an Insert operation, the orchestration does not do anything.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="625cf-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="625cf-111">In This Section</span></span>  
  
-   [<span data-ttu-id="625cf-112">Paso 1: Agregar formas de orquestación para recibir una notificación</span><span class="sxs-lookup"><span data-stu-id="625cf-112">Step 1: Add Orchestration Shapes to Receive Notification</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-add-orchestration-shapes-to-receive-notification.md)  
  
-   [<span data-ttu-id="625cf-113">Paso 2: Extraer el tipo de notificación de mensaje de notificación</span><span class="sxs-lookup"><span data-stu-id="625cf-113">Step 2: Extract Notification Type from Notification Message</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-extract-notification-type-from-notification-message.md)  
  
-   [<span data-ttu-id="625cf-114">Paso 3: Agregar un filtro para las notificaciones de inserción</span><span class="sxs-lookup"><span data-stu-id="625cf-114">Step 3: Add a Filter for Insert Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-add-a-filter-for-insert-notifications.md)