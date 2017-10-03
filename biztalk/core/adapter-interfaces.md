---
title: Interfaces de adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7398aeb-7c1c-400e-a552-d0ab39e55a0b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717adcf5d4a706a7cc072b42b224ab0f9f8cc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-interfaces"></a><span data-ttu-id="cc7dc-102">Interfaces de adaptador</span><span class="sxs-lookup"><span data-stu-id="cc7dc-102">Adapter Interfaces</span></span>
<span data-ttu-id="cc7dc-103">Hay tres interfaces que los adaptadores personalizados deben implementar y dos interfaces que son opcionales.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-103">There are three interfaces that custom adapters must implement, and two interfaces that are optional.</span></span>  
  
## <a name="mandatory-interfaces"></a><span data-ttu-id="cc7dc-104">Interfaces obligatorias</span><span class="sxs-lookup"><span data-stu-id="cc7dc-104">Mandatory interfaces</span></span>  
 <span data-ttu-id="cc7dc-105">Todos los adaptadores deben implementar las interfaces siguientes.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-105">All adapters must implement the following interfaces.</span></span>  
  
### <a name="ibasecomponent"></a><span data-ttu-id="cc7dc-106">IBaseComponent</span><span class="sxs-lookup"><span data-stu-id="cc7dc-106">IBaseComponent</span></span>  
 <span data-ttu-id="cc7dc-107">Esta información de la interfaz del **nombre**, **versión**, y **descripción** del adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-107">This interface details the **Name**, **Version**, and **Description** of the adapter.</span></span>  
  
### <a name="ibttransport"></a><span data-ttu-id="cc7dc-108">IBTTransport</span><span class="sxs-lookup"><span data-stu-id="cc7dc-108">IBTTransport</span></span>  
 <span data-ttu-id="cc7dc-109">Esta información de la interfaz del **tipo de transporte** y **ClassID** del adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-109">This interface details the **Transport Type** and **ClassID** of the adapter.</span></span>  
  
### <a name="ibtbatchcallback"></a><span data-ttu-id="cc7dc-110">IBTBatchCallback</span><span class="sxs-lookup"><span data-stu-id="cc7dc-110">IBTBatchCallback</span></span>  
 <span data-ttu-id="cc7dc-111">Es una interfaz de devolución de llamada a través de la que el adaptador recibe información de estado y de errores de un lote de mensajes enviados al motor de mensajería.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-111">This interface is a callback interface through which the adapter receives status and error information for a batch of messages it submits to the Messaging Engine.</span></span>  
  
## <a name="optional-interfaces"></a><span data-ttu-id="cc7dc-112">Interfaces opcionales</span><span class="sxs-lookup"><span data-stu-id="cc7dc-112">Optional interfaces</span></span>  
 <span data-ttu-id="cc7dc-113">Los adaptadores, en función de sus necesidades, puede que implementen o no las interfaces siguientes.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-113">Adapters may or may not implement the following interfaces, depending on their needs.</span></span>  
  
### <a name="ipersistpropertybag"></a><span data-ttu-id="cc7dc-114">IPersistPropertyBag</span><span class="sxs-lookup"><span data-stu-id="cc7dc-114">IPersistPropertyBag</span></span>  
 <span data-ttu-id="cc7dc-115">Es una interfaz de configuración a través de la que se entrega la configuración del controlador al adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-115">This is a configuration interface through which handler configuration is delivered to the adapter.</span></span> <span data-ttu-id="cc7dc-116">Solo es necesaria para los adaptadores que tienen información de configuración del controlador.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-116">This interface is required only for adapters that have handler configuration information.</span></span>  
  
### <a name="ibttransportcontrol"></a><span data-ttu-id="cc7dc-117">IBTTransportControl</span><span class="sxs-lookup"><span data-stu-id="cc7dc-117">IBTTransportControl</span></span>  
 <span data-ttu-id="cc7dc-118">Esta interfaz se usa para inicializar y finalizar un adaptador.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-118">This interface is used to initialize and terminate an adapter.</span></span> <span data-ttu-id="cc7dc-119">El proxy de transporte del adaptador se pasa al adaptador a través de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-119">The adapter's transport proxy is passed to it through this interface.</span></span> <span data-ttu-id="cc7dc-120">Esta interfaz no es necesaria para los adaptadores aislados.</span><span class="sxs-lookup"><span data-stu-id="cc7dc-120">This interface is not required for isolated adapters.</span></span>