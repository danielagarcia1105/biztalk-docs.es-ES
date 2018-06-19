---
title: 'Paso 2: Crear la Orchestration2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08d65525-77a9-4be2-a509-40ea60fa7401
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13973edb14fbaed331a33eff429d623a33c3ff71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276756"
---
# <a name="step-2-create-the-orchestration"></a><span data-ttu-id="dbbf8-102">Paso 2: Crear la orquestación</span><span class="sxs-lookup"><span data-stu-id="dbbf8-102">Step 2: Create the Orchestration</span></span>
<span data-ttu-id="dbbf8-103">La configuración de orquestación se realiza de la siguiente forma, mediante un proyecto denominado BeginDocTest:</span><span class="sxs-lookup"><span data-stu-id="dbbf8-103">The orchestration setup is as follows using a project called BeginDocTest:</span></span>  
  
 <span data-ttu-id="dbbf8-104">• Puertos</span><span class="sxs-lookup"><span data-stu-id="dbbf8-104">• Ports</span></span>  
  
 <span data-ttu-id="dbbf8-105">• Mensajes</span><span class="sxs-lookup"><span data-stu-id="dbbf8-105">• Messages</span></span>  
  
 <span data-ttu-id="dbbf8-106">• Envío y recepción</span><span class="sxs-lookup"><span data-stu-id="dbbf8-106">• Send and Receive</span></span>  
  
 <span data-ttu-id="dbbf8-107">• Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="dbbf8-107">• Construct Message</span></span>  
  
 <span data-ttu-id="dbbf8-108">• Transformaciones</span><span class="sxs-lookup"><span data-stu-id="dbbf8-108">• Transforms</span></span>  
  
 <span data-ttu-id="dbbf8-109">La orquestación no realiza ningún control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-109">The orchestration does not do any exception handling.</span></span> <span data-ttu-id="dbbf8-110">J.D.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-110">J.D.</span></span> <span data-ttu-id="dbbf8-111">Edwards EnterpriseOne realiza las operaciones BeginDoc y operaciones siguientes dentro de una transacción implícita que se revertirán si la conexión agota el tiempo de espera. Por lo tanto, la orquestación de BizTalk no necesita hacer nada para revertir los cambios que realiza J.D.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-111">Edwards EnterpriseOne performs the BeginDoc and subsequent operations within an implicit transaction that it will rollback if the connection times out. The BizTalk orchestration thus does not need to do anything to rollback changes J.D.</span></span> <span data-ttu-id="dbbf8-112">Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-112">Edwards EnterpriseOne makes.</span></span> <span data-ttu-id="dbbf8-113">Sin embargo, el tiempo de espera provocará una excepción en la orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-113">However, a time out will cause an exception in the BizTalk orchestration.</span></span> <span data-ttu-id="dbbf8-114">BizTalk registrará la excepción en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-114">BizTalk will record the exception in the event log.</span></span> <span data-ttu-id="dbbf8-115">Si desea agregar control de excepciones a la orquestación, vea "Cómo agregar un bloque de excepción de filtrado " y "Cómo agregar un bloque de compensación" en la ayuda principal de Microsoft BizTalk 2006.</span><span class="sxs-lookup"><span data-stu-id="dbbf8-115">If you want to add exception handling to the orchestration, see "How to Add a Catch Exception Block" and "How to Add a Compensation Block" in the Microsoft BizTalk 2006 main help.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbbf8-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dbbf8-116">In This Section</span></span>  
  
-   [<span data-ttu-id="dbbf8-117">Tarea 1: Crear los puertos</span><span class="sxs-lookup"><span data-stu-id="dbbf8-117">Task 1: Create the Ports</span></span>](../core/task-1-create-the-ports1.md)  
  
-   [<span data-ttu-id="dbbf8-118">Tarea 2: Crear los mensajes</span><span class="sxs-lookup"><span data-stu-id="dbbf8-118">Task 2: Create the Messages</span></span>](../core/task-2-create-the-messages2.md)  
  
-   [<span data-ttu-id="dbbf8-119">Tarea 3: Configurar el envío y recepción formas</span><span class="sxs-lookup"><span data-stu-id="dbbf8-119">Task 3: Configure the Send and Receive Shapes</span></span>](../core/task-3-configure-the-send-and-receive-shapes2.md)  
  
-   [<span data-ttu-id="dbbf8-120">Tarea 4: Configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="dbbf8-120">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape1.md)  
  
-   [<span data-ttu-id="dbbf8-121">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="dbbf8-121">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)