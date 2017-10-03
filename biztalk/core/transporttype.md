---
title: TransportType | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransportType node [binding file]
ms.assetid: 64eb00be-47c9-473f-aec6-03cb7f948e3b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d9636e7aa6dd8b09bb73678072242ed8b8725a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype"></a><span data-ttu-id="0fbcf-102">TransportType</span><span class="sxs-lookup"><span data-stu-id="0fbcf-102">TransportType</span></span>
<span data-ttu-id="0fbcf-103">El nodo TransportType del nodo SendHandler de un archivo de enlace contiene información específica acerca del adaptador asociado a un controlador de envío que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="0fbcf-103">The TransportType node of the SendHandler node of a binding file contains specific information about the adapter associated with a send handler that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="0fbcf-104">Nodos del nodo TransportType</span><span class="sxs-lookup"><span data-stu-id="0fbcf-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="0fbcf-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="0fbcf-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="0fbcf-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="0fbcf-106">**Name**</span></span>|<span data-ttu-id="0fbcf-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="0fbcf-107">**Node Type**</span></span>|<span data-ttu-id="0fbcf-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="0fbcf-108">**Data Type**</span></span>|<span data-ttu-id="0fbcf-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="0fbcf-109">**Description**</span></span>|<span data-ttu-id="0fbcf-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="0fbcf-110">**Restrictions**</span></span>|<span data-ttu-id="0fbcf-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="0fbcf-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="0fbcf-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="0fbcf-112">Name</span></span>|<span data-ttu-id="0fbcf-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="0fbcf-113">Attribute</span></span>|<span data-ttu-id="0fbcf-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="0fbcf-114">xs:string</span></span>|<span data-ttu-id="0fbcf-115">Especifica el nombre del adaptador asociado al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="0fbcf-115">Specifies the name of the adapter associated with the send handler.</span></span>|<span data-ttu-id="0fbcf-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="0fbcf-116">Not required</span></span>|<span data-ttu-id="0fbcf-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="0fbcf-117">Default value: empty</span></span>|  
|<span data-ttu-id="0fbcf-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="0fbcf-118">Capabilities</span></span>|<span data-ttu-id="0fbcf-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="0fbcf-119">Attribute</span></span>|<span data-ttu-id="0fbcf-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="0fbcf-120">xs:int</span></span>|<span data-ttu-id="0fbcf-121">Especifica las capacidades del adaptador asociado al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="0fbcf-121">Specifies the capabilities of the adapter associated with the send handler.</span></span>|<span data-ttu-id="0fbcf-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="0fbcf-122">Required</span></span>|<span data-ttu-id="0fbcf-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="0fbcf-123">Default value: none</span></span><br /><br /> <span data-ttu-id="0fbcf-124">Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .</span><span class="sxs-lookup"><span data-stu-id="0fbcf-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="0fbcf-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="0fbcf-125">ConfigurationClsid</span></span>|<span data-ttu-id="0fbcf-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="0fbcf-126">Attribute</span></span>|<span data-ttu-id="0fbcf-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0fbcf-127">xs:string</span></span>|<span data-ttu-id="0fbcf-128">Especifica el GUID de configuración del adaptador asociado al controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="0fbcf-128">Specifies the configuration GUID of the adapter associated with the send handler.</span></span>|<span data-ttu-id="0fbcf-129">No requerido</span><span class="sxs-lookup"><span data-stu-id="0fbcf-129">Not required</span></span>|<span data-ttu-id="0fbcf-130">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="0fbcf-130">Default value: empty</span></span>|