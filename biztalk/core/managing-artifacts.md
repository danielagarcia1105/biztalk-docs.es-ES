---
title: Administrar artefactos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ccca48682f009a24f538015b055c45dd79a9587
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-artifacts"></a><span data-ttu-id="aad75-102">Administrar artefactos</span><span class="sxs-lookup"><span data-stu-id="aad75-102">Managing Artifacts</span></span>
<span data-ttu-id="aad75-103">En esta sección se describe cómo administrar artefactos; se incluye una explicación de cómo agregarlos a una aplicación de BizTalk y de cómo quitarlos de ella, además del modo de configurar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="aad75-103">This section describes how to manage artifacts, including how to add and remove them from a BizTalk application and how to configure their properties.</span></span>  
  
 <span data-ttu-id="aad75-104">Los artefactos son los elementos contenidos en una aplicación de BizTalk y que resultan necesarios para que ésta se ejecute.</span><span class="sxs-lookup"><span data-stu-id="aad75-104">Artifacts are the items contained in a BizTalk application that are required for it to run.</span></span> <span data-ttu-id="aad75-105">Para obtener información general sobre cómo se utilizan los artefactos en una aplicación de BizTalk, consulte [¿qué es una aplicación de BizTalk?](../core/what-is-a-biztalk-application.md)</span><span class="sxs-lookup"><span data-stu-id="aad75-105">For background information about how artifacts are used in a BizTalk application, see [What Is a BizTalk Application?](../core/what-is-a-biztalk-application.md)</span></span> <span data-ttu-id="aad75-106">Para obtener información general sobre los artefactos, vea [arquitectura en tiempo de ejecución](../core/runtime-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="aad75-106">For background information about artifacts, see [Runtime Architecture](../core/runtime-architecture.md).</span></span> <span data-ttu-id="aad75-107">Para obtener información acerca de cómo manipular artefactos al crear y modificar una aplicación de BizTalk, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md).</span><span class="sxs-lookup"><span data-stu-id="aad75-107">For information about how you manipulate artifacts when you create and modify a BizTalk application, see [Creating and Modifying BizTalk Applications](../core/creating-and-modifying-biztalk-applications.md).</span></span>  

## <a name="tracking-artifacts"></a><span data-ttu-id="aad75-108">Artefactos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="aad75-108">Tracking artifacts</span></span>
<span data-ttu-id="aad75-109">Está realizando el seguimiento de una parte importante de la administración de los artefactos que se crea.</span><span class="sxs-lookup"><span data-stu-id="aad75-109">A big part of managing the artifacts you create is tracking.</span></span> <span data-ttu-id="aad75-110">La consola de administración de BizTalk Server permite configurar diversas opciones de seguimiento durante el tiempo de ejecución para orquestaciones, puertos de envío, puertos de recepción y canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="aad75-110">You can configure various tracking options during run time for orchestrations, send ports, receive ports, and pipelines using the BizTalk Server Administration console.</span></span> <span data-ttu-id="aad75-111">Se pueden cambiar las opciones de seguimiento de un elemento en cualquier momento, sin necesidad de interrumpir el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="aad75-111">You can change the tracking options for an item at any time, without interrupting the business process.</span></span>

<span data-ttu-id="aad75-112">Las opciones de configuración del seguimiento permiten realizar el seguimiento de los siguientes tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="aad75-112">The tracking configuration settings allow you to track the following types of data:</span></span>

- <span data-ttu-id="aad75-113">Datos de eventos de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="aad75-113">Inbound and/or outbound event data.</span></span> <span data-ttu-id="aad75-114">Por ejemplo, Id. del mensaje, horas de inicio y detención del artefacto.</span><span class="sxs-lookup"><span data-stu-id="aad75-114">For example, message ID, start and stop times for the artifact.</span></span>

- <span data-ttu-id="aad75-115">Propiedades de mensajes de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="aad75-115">Inbound and/or outbound message properties.</span></span> <span data-ttu-id="aad75-116">Por ejemplo, propiedades generales y promocionadas de cada mensaje que procesa el artefacto.</span><span class="sxs-lookup"><span data-stu-id="aad75-116">For example, general and promoted properties for each message that the artifact processes.</span></span>

- <span data-ttu-id="aad75-117">Cuerpos y partes de mensajes de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="aad75-117">Inbound and/or outbound message bodies and parts.</span></span> <span data-ttu-id="aad75-118">Por ejemplo, el cuerpo y las partes de cada mensaje que procesa el artefacto.</span><span class="sxs-lookup"><span data-stu-id="aad75-118">For example, body and parts for each message that the artifact processes.</span></span>

- <span data-ttu-id="aad75-119">Orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="aad75-119">Orchestrations.</span></span> <span data-ttu-id="aad75-120">Datos de ejecución correspondientes a formas de orquestación.</span><span class="sxs-lookup"><span data-stu-id="aad75-120">Execution data for orchestration shapes.</span></span>

<span data-ttu-id="aad75-121">[Ver datos de instancia y realiza el seguimiento de mensaje](../core/viewing-tracked-message-and-instance-data.md) proporciona alguna información válida.</span><span class="sxs-lookup"><span data-stu-id="aad75-121">[Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md) provides some good info.</span></span> 


> [!TIP]
> <span data-ttu-id="aad75-122">Si establece opciones de seguimiento en una canalización, las opciones de seguimiento se establecen globalmente para todos los puertos que usa la canalización.</span><span class="sxs-lookup"><span data-stu-id="aad75-122">If you set tracking options on a pipeline, then the tracking options are set globally for every port that uses the pipeline.</span></span> <span data-ttu-id="aad75-123">Esto hace mucho más datos de seguimiento que tenga la intención y puede afectar al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="aad75-123">This results in far more data being tracked than you may intend, and may impact system performance.</span></span> <span data-ttu-id="aad75-124">Durante el desarrollo, esto puede ser normal.</span><span class="sxs-lookup"><span data-stu-id="aad75-124">During development, this may be normal.</span></span> <span data-ttu-id="aad75-125">En escenarios de producción, se recomienda habilitar las opciones de seguimiento en los puertos de envío y puertos, en lugar de las canalizaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="aad75-125">In production scenarios, we recommend you enable any tracking options on the send ports and receive ports, instead of the pipelines.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="aad75-126">En esta sección</span><span class="sxs-lookup"><span data-stu-id="aad75-126">In this section</span></span>  
  
-   [<span data-ttu-id="aad75-127">Administrar orquestaciones</span><span class="sxs-lookup"><span data-stu-id="aad75-127">Managing Orchestrations</span></span>](../core/managing-orchestrations.md)  
  
-   [<span data-ttu-id="aad75-128">Administrar vínculos de rol</span><span class="sxs-lookup"><span data-stu-id="aad75-128">Managing Role Links</span></span>](../core/managing-role-links.md)  
  
-   [<span data-ttu-id="aad75-129">Administrar puertos de envío y grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="aad75-129">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [<span data-ttu-id="aad75-130">Administrar puertos de recepción</span><span class="sxs-lookup"><span data-stu-id="aad75-130">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)  
  
-   [<span data-ttu-id="aad75-131">Administrar ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="aad75-131">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)  
  
-   [<span data-ttu-id="aad75-132">Administración de directivas</span><span class="sxs-lookup"><span data-stu-id="aad75-132">Managing Policies</span></span>](../core/managing-policies.md)  
  
-   [<span data-ttu-id="aad75-133">Administrar esquemas</span><span class="sxs-lookup"><span data-stu-id="aad75-133">Managing Schemas</span></span>](../core/managing-schemas.md)  
  
-   [<span data-ttu-id="aad75-134">Administración de mapas</span><span class="sxs-lookup"><span data-stu-id="aad75-134">Managing Maps</span></span>](../core/managing-maps.md)  
  
-   [<span data-ttu-id="aad75-135">Administrar canalizaciones</span><span class="sxs-lookup"><span data-stu-id="aad75-135">Managing Pipelines</span></span>](../core/managing-pipelines.md)  
  
-   [<span data-ttu-id="aad75-136">Administración de recursos</span><span class="sxs-lookup"><span data-stu-id="aad75-136">Managing Resources</span></span>](../core/managing-resources.md)