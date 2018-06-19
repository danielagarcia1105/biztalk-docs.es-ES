---
title: TransportType (nodo SendHandler) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ee87a409-33dd-4111-ba6a-ead3bacc80aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3525b78fa9812c1e4fa8690a622f9b8cccce8d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278988"
---
# <a name="transporttype-sendhandler-node"></a><span data-ttu-id="bd032-102">TransportType (nodo SendHandler)</span><span class="sxs-lookup"><span data-stu-id="bd032-102">TransportType (SendHandler Node)</span></span>
<span data-ttu-id="bd032-103">El nodo TransportType del nodo SendHandler de un archivo de enlace contiene información específica acerca del adaptador asociado a un controlador de envío que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="bd032-103">The TransportType node of the SendHandler node of a binding file contains specific information about the adapter associated with a send handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="bd032-104">Nodos del nodo TransportType</span><span class="sxs-lookup"><span data-stu-id="bd032-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="bd032-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="bd032-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="bd032-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bd032-106">**Name**</span></span>|<span data-ttu-id="bd032-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="bd032-107">**Node Type**</span></span>|<span data-ttu-id="bd032-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="bd032-108">**Data Type**</span></span>|<span data-ttu-id="bd032-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="bd032-109">**Description**</span></span>|<span data-ttu-id="bd032-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="bd032-110">**Restrictions**</span></span>|<span data-ttu-id="bd032-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="bd032-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="bd032-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="bd032-112">Name</span></span>|<span data-ttu-id="bd032-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="bd032-113">Attribute</span></span>|<span data-ttu-id="bd032-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd032-114">xs:string</span></span>|<span data-ttu-id="bd032-115">Especifica el nombre del adaptador asociado al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="bd032-115">Specifies the name of the adapter associated with the send handler.</span></span>|<span data-ttu-id="bd032-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="bd032-116">Not required</span></span>|<span data-ttu-id="bd032-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="bd032-117">Default value: empty</span></span>|  
|<span data-ttu-id="bd032-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="bd032-118">Capabilities</span></span>|<span data-ttu-id="bd032-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="bd032-119">Attribute</span></span>|<span data-ttu-id="bd032-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="bd032-120">xs:int</span></span>|<span data-ttu-id="bd032-121">Especifica las capacidades del adaptador asociado al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="bd032-121">Specifies the capabilities of the adapter associated with the send handler.</span></span>|<span data-ttu-id="bd032-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="bd032-122">Required</span></span>|<span data-ttu-id="bd032-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="bd032-123">Default value: none</span></span><br /><br /> <span data-ttu-id="bd032-124">Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .</span><span class="sxs-lookup"><span data-stu-id="bd032-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="bd032-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="bd032-125">ConfigurationClsid</span></span>|<span data-ttu-id="bd032-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="bd032-126">Attribute</span></span>|<span data-ttu-id="bd032-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="bd032-127">xs:string</span></span>|<span data-ttu-id="bd032-128">Especifica el GUID de configuración del adaptador asociado al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="bd032-128">Specifies the configuration GUID of the adapter associated with the send handler.</span></span>|<span data-ttu-id="bd032-129">No requerido</span><span class="sxs-lookup"><span data-stu-id="bd032-129">Not required</span></span>|<span data-ttu-id="bd032-130">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="bd032-130">Default value: empty</span></span>|