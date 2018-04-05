---
title: TransportType (nodo PrimaryTransport) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: 9eb377ec-35d8-4b72-85f9-f264f6553c5a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40e0f005e7279541a2cdcb5c2bf205b7731e5263
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-primarytransport-node"></a><span data-ttu-id="cea8c-102">TransportType (nodo PrimaryTransport)</span><span class="sxs-lookup"><span data-stu-id="cea8c-102">TransportType (PrimaryTransport Node)</span></span>
<span data-ttu-id="cea8c-103">El nodo TransportType del nodo PrimaryTransport de un archivo de enlace contiene información específica acerca del adaptador asociado a un transporte que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="cea8c-103">The TransportType node of the PrimaryTransport node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transporttype-node"></a><span data-ttu-id="cea8c-104">Nodos del nodo TransportType</span><span class="sxs-lookup"><span data-stu-id="cea8c-104">Nodes in the TransportType node</span></span>  
 <span data-ttu-id="cea8c-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="cea8c-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="cea8c-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="cea8c-106">**Name**</span></span>|<span data-ttu-id="cea8c-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="cea8c-107">**Node Type**</span></span>|<span data-ttu-id="cea8c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="cea8c-108">**Data Type**</span></span>|<span data-ttu-id="cea8c-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="cea8c-109">**Description**</span></span>|<span data-ttu-id="cea8c-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="cea8c-110">**Restrictions**</span></span>|<span data-ttu-id="cea8c-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="cea8c-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="cea8c-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="cea8c-112">Name</span></span>|<span data-ttu-id="cea8c-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="cea8c-113">Attribute</span></span>|<span data-ttu-id="cea8c-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="cea8c-114">xs:string</span></span>|<span data-ttu-id="cea8c-115">Especifica el nombre del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="cea8c-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="cea8c-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="cea8c-116">Not required</span></span>|<span data-ttu-id="cea8c-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="cea8c-117">Default value: empty</span></span>|  
|<span data-ttu-id="cea8c-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="cea8c-118">Capabilities</span></span>|<span data-ttu-id="cea8c-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="cea8c-119">Attribute</span></span>|<span data-ttu-id="cea8c-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="cea8c-120">xs:int</span></span>|<span data-ttu-id="cea8c-121">Especifica las funciones del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="cea8c-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="cea8c-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="cea8c-122">Required</span></span>|<span data-ttu-id="cea8c-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="cea8c-123">Default value: none</span></span><br /><br /> <span data-ttu-id="cea8c-124">Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .</span><span class="sxs-lookup"><span data-stu-id="cea8c-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="cea8c-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="cea8c-125">ConfigurationClsid</span></span>|<span data-ttu-id="cea8c-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="cea8c-126">Attribute</span></span>|<span data-ttu-id="cea8c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="cea8c-127">xs:string</span></span>|<span data-ttu-id="cea8c-128">Especifica el GUID de configuración del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="cea8c-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="cea8c-129">No requerido</span><span class="sxs-lookup"><span data-stu-id="cea8c-129">Not required</span></span>|<span data-ttu-id="cea8c-130">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="cea8c-130">Default value: empty</span></span>|