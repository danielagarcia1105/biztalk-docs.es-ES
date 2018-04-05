---
title: ReceiveLocationTransportType (nodo ReceiveLocation) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveLocationTransportType node [binding file]
ms.assetid: 375076c3-d5e6-4c25-b054-b452e29717e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0eae3e2c4fd9f5f668cb12ffd630640b1b63c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receivelocationtransporttype-receivelocation-node"></a><span data-ttu-id="4ca15-102">ReceiveLocationTransportType (nodo ReceiveLocation)</span><span class="sxs-lookup"><span data-stu-id="4ca15-102">ReceiveLocationTransportType (ReceiveLocation Node)</span></span>
<span data-ttu-id="4ca15-103">El nodo ReceiveLocationTransportType del nodo ReceiveLocation de un archivo de enlace contiene información específica acerca del adaptador asociado a un transporte que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ca15-103">The ReceiveLocationTransportType node of the ReceiveLocation node of a binding file contains specific information about the adapter associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a><span data-ttu-id="4ca15-104">Nodos del nodo ReceiveLocationTransportType</span><span class="sxs-lookup"><span data-stu-id="4ca15-104">Nodes in the ReceiveLocationTransportType node</span></span>  
 <span data-ttu-id="4ca15-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="4ca15-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="4ca15-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="4ca15-106">**Name**</span></span>|<span data-ttu-id="4ca15-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="4ca15-107">**Node Type**</span></span>|<span data-ttu-id="4ca15-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="4ca15-108">**Data Type**</span></span>|<span data-ttu-id="4ca15-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="4ca15-109">**Description**</span></span>|<span data-ttu-id="4ca15-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="4ca15-110">**Restrictions**</span></span>|<span data-ttu-id="4ca15-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="4ca15-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="4ca15-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="4ca15-112">Name</span></span>|<span data-ttu-id="4ca15-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ca15-113">Attribute</span></span>|<span data-ttu-id="4ca15-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ca15-114">xs:string</span></span>|<span data-ttu-id="4ca15-115">Especifica el nombre del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="4ca15-115">Specifies the name of the adapter associated with the transport.</span></span>|<span data-ttu-id="4ca15-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="4ca15-116">Not required</span></span>|<span data-ttu-id="4ca15-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="4ca15-117">Default value: empty</span></span>|  
|<span data-ttu-id="4ca15-118">Capabilities</span><span class="sxs-lookup"><span data-stu-id="4ca15-118">Capabilities</span></span>|<span data-ttu-id="4ca15-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ca15-119">Attribute</span></span>|<span data-ttu-id="4ca15-120">xs:int</span><span class="sxs-lookup"><span data-stu-id="4ca15-120">xs:int</span></span>|<span data-ttu-id="4ca15-121">Especifica las funciones del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="4ca15-121">Specifies the capabilities of the adapter associated with the transport.</span></span>|<span data-ttu-id="4ca15-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="4ca15-122">Required</span></span>|<span data-ttu-id="4ca15-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="4ca15-123">Default value: none</span></span><br /><br /> <span data-ttu-id="4ca15-124">Los valores posibles incluyen los que están disponibles en la enumeración [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4ca15-124">Possible values include those available in the [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) enumeration.</span></span>|  
|<span data-ttu-id="4ca15-125">ConfigurationClsid</span><span class="sxs-lookup"><span data-stu-id="4ca15-125">ConfigurationClsid</span></span>|<span data-ttu-id="4ca15-126">Atributo</span><span class="sxs-lookup"><span data-stu-id="4ca15-126">Attribute</span></span>|<span data-ttu-id="4ca15-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ca15-127">xs:string</span></span>|<span data-ttu-id="4ca15-128">Especifica el GUID de configuración del adaptador asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="4ca15-128">Specifies the configuration GUID of the adapter associated with the transport.</span></span>|<span data-ttu-id="4ca15-129">No requerido</span><span class="sxs-lookup"><span data-stu-id="4ca15-129">Not required</span></span>|<span data-ttu-id="4ca15-130">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="4ca15-130">Default value: empty</span></span>|