---
title: TransportType (nodo SecondaryTransport) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ed66c7ef-32b6-4110-b932-f96a45a29618
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bb0b9460e6c4689dab169a37a9d6b6c51753598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-secondarytransport-node"></a><span data-ttu-id="3db81-102">TransportType (nodo SecondaryTransport)</span><span class="sxs-lookup"><span data-stu-id="3db81-102">TransportType (SecondaryTransport Node)</span></span>
<span data-ttu-id="3db81-103">El nodo TransportType del nodo SecondaryTransport de un archivo de enlace contiene información específica acerca del adaptador asociado a un transporte que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="3db81-103">The TransportType node of the SecondaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="3db81-104">Nodos del nodo TransportType</span><span class="sxs-lookup"><span data-stu-id="3db81-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="3db81-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="3db81-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="3db81-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="3db81-106">**Name**</span></span>|<span data-ttu-id="3db81-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="3db81-107">**Node Type**</span></span>|<span data-ttu-id="3db81-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3db81-108">**Data Type**</span></span>|<span data-ttu-id="3db81-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="3db81-109">**Description**</span></span>|<span data-ttu-id="3db81-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="3db81-110">**Restrictions**</span></span>|<span data-ttu-id="3db81-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="3db81-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="3db81-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="3db81-112">Name</span></span>|<span data-ttu-id="3db81-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3db81-113">Attribute</span></span>|<span data-ttu-id="3db81-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db81-114">xs:string</span></span>|<span data-ttu-id="3db81-115">Especifica el nombre del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="3db81-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="3db81-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="3db81-116">Not required</span></span>|<span data-ttu-id="3db81-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="3db81-117">Default value: empty</span></span>|  
|<span data-ttu-id="3db81-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="3db81-118">Capabilities</span></span>|<span data-ttu-id="3db81-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="3db81-119">Attribute</span></span>|<span data-ttu-id="3db81-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="3db81-120">xs:int</span></span>|<span data-ttu-id="3db81-121">Especifica las funciones del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="3db81-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="3db81-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="3db81-122">Required</span></span>|<span data-ttu-id="3db81-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="3db81-123">Default value: none</span></span><br /><br /> <span data-ttu-id="3db81-124">Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .</span><span class="sxs-lookup"><span data-stu-id="3db81-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="3db81-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="3db81-125">ConfigurationClsid</span></span>|<span data-ttu-id="3db81-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="3db81-126">Attribute</span></span>|<span data-ttu-id="3db81-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3db81-127">xs:string</span></span>|<span data-ttu-id="3db81-128">Especifica el GUID de configuración del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="3db81-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="3db81-129">No requerido</span><span class="sxs-lookup"><span data-stu-id="3db81-129">Not required</span></span>|<span data-ttu-id="3db81-130">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="3db81-130">Default value: empty</span></span>|