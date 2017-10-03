---
title: TransportType (nodo ReceiveHandler) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransportType node [binding file]
ms.assetid: d893b3ac-8e2c-41fb-926c-cea23f6f93b3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df0e041a322b8bb9a144b9ea2bdab5ebb58ac01e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-receivehandler-node"></a><span data-ttu-id="c8147-102">TransportType (nodo ReceiveHandler)</span><span class="sxs-lookup"><span data-stu-id="c8147-102">TransportType (ReceiveHandler Node)</span></span>
<span data-ttu-id="c8147-103">El nodo TransportType del nodo ReceiveHandler de un archivo de enlace contiene información específica acerca del adaptador asociado a un controlador de recepción que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="c8147-103">The TransportType node of the ReceiveHandler node of a binding file contains specific information about the adapter associated with a receive handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="c8147-104">Nodos del nodo TransportType</span><span class="sxs-lookup"><span data-stu-id="c8147-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="c8147-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="c8147-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c8147-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c8147-106">**Name**</span></span>|<span data-ttu-id="c8147-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="c8147-107">**Node Type**</span></span>|<span data-ttu-id="c8147-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c8147-108">**Data Type**</span></span>|<span data-ttu-id="c8147-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="c8147-109">**Description**</span></span>|<span data-ttu-id="c8147-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="c8147-110">**Restrictions**</span></span>|<span data-ttu-id="c8147-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="c8147-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c8147-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="c8147-112">Name</span></span>|<span data-ttu-id="c8147-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8147-113">Attribute</span></span>|<span data-ttu-id="c8147-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8147-114">xs:string</span></span>|<span data-ttu-id="c8147-115">Especifica el nombre del adaptador asociado al controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="c8147-115">Specifies the name of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="c8147-116">No es obligatorio</span><span class="sxs-lookup"><span data-stu-id="c8147-116">Not Required</span></span>|<span data-ttu-id="c8147-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="c8147-117">Default value: empty</span></span>|  
|<span data-ttu-id="c8147-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="c8147-118">Capabilities</span></span>|<span data-ttu-id="c8147-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8147-119">Attribute</span></span>|<span data-ttu-id="c8147-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="c8147-120">xs:int</span></span>|<span data-ttu-id="c8147-121">Especifica las funciones del adaptador asociado al controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="c8147-121">Specifies the capabilities of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="c8147-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="c8147-122">Required</span></span>|<span data-ttu-id="c8147-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="c8147-123">Default value: none</span></span><br /><br /> <span data-ttu-id="c8147-124">Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c8147-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="c8147-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="c8147-125">ConfigurationClsid</span></span>|<span data-ttu-id="c8147-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="c8147-126">Attribute</span></span>|<span data-ttu-id="c8147-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c8147-127">xs:string</span></span>|<span data-ttu-id="c8147-128">Especifica el GUID de configuración del adaptador asociado al controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="c8147-128">Specifies the configuration GUID of the adapter associated with the receive handler.</span></span>|<span data-ttu-id="c8147-129">No es obligatorio</span><span class="sxs-lookup"><span data-stu-id="c8147-129">Not Required</span></span>|<span data-ttu-id="c8147-130">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="c8147-130">Default value: empty</span></span>|