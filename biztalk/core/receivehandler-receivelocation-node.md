---
title: ReceiveHandler (nodo ReceiveLocation) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceiveHandler node [binding file]
ms.assetid: dd105052-ec71-4762-aa74-e8cdb806a6bf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e865886624731414f979c77f3f2e898e417c8b11
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="receivehandler-receivelocation-node"></a><span data-ttu-id="fb9d8-102">ReceiveHandler (nodo ReceiveLocation)</span><span class="sxs-lookup"><span data-stu-id="fb9d8-102">ReceiveHandler (ReceiveLocation Node)</span></span>
<span data-ttu-id="fb9d8-103">El nodo ReceiveHandler del nodo ReceiveLocation de un archivo de enlace contiene información específica acerca del controlador de recepción asociado a un transporte que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fb9d8-103">The ReceiveHandler node of the ReceiveLocation node of a binding file contains specific information about the receive handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-receivehandler-node"></a><span data-ttu-id="fb9d8-104">Nodos del nodo ReceiveHandler</span><span class="sxs-lookup"><span data-stu-id="fb9d8-104">Nodes in the ReceiveHandler node</span></span>  
 <span data-ttu-id="fb9d8-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="fb9d8-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="fb9d8-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fb9d8-106">**Name**</span></span>|<span data-ttu-id="fb9d8-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="fb9d8-107">**Node Type**</span></span>|<span data-ttu-id="fb9d8-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fb9d8-108">**Data Type**</span></span>|<span data-ttu-id="fb9d8-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="fb9d8-109">**Description**</span></span>|<span data-ttu-id="fb9d8-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="fb9d8-110">**Restrictions**</span></span>|<span data-ttu-id="fb9d8-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="fb9d8-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="fb9d8-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="fb9d8-112">Name</span></span>|<span data-ttu-id="fb9d8-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="fb9d8-113">Attribute</span></span>|<span data-ttu-id="fb9d8-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="fb9d8-114">xs:string</span></span>|<span data-ttu-id="fb9d8-115">Especifica el nombre del controlador de recepción asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="fb9d8-115">Specifies the name of the receive handler associated with the transport.</span></span>|<span data-ttu-id="fb9d8-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="fb9d8-116">Not required</span></span>|<span data-ttu-id="fb9d8-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="fb9d8-117">Default value: empty</span></span>|  
|<span data-ttu-id="fb9d8-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="fb9d8-118">HostTrusted</span></span>|<span data-ttu-id="fb9d8-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="fb9d8-119">Attribute</span></span>|<span data-ttu-id="fb9d8-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="fb9d8-120">xs:boolean</span></span>|<span data-ttu-id="fb9d8-121">Especifica si el host asociado al controlador de recepción asociado es de confianza.</span><span class="sxs-lookup"><span data-stu-id="fb9d8-121">Specifies whether the host associated with the receive handler is trusted.</span></span>|<span data-ttu-id="fb9d8-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="fb9d8-122">Required</span></span>|<span data-ttu-id="fb9d8-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="fb9d8-123">Default value: none</span></span><br /><br /> <span data-ttu-id="fb9d8-124">Establecido en **true** si el host es de confianza, en caso contrario, se establece en **false**.</span><span class="sxs-lookup"><span data-stu-id="fb9d8-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="fb9d8-125">TransportType (nodo ReceiveHandler)</span><span class="sxs-lookup"><span data-stu-id="fb9d8-125">TransportType (ReceiveHandler Node)</span></span>](../core/transporttype-receivehandler-node.md)|<span data-ttu-id="fb9d8-126">Grabar</span><span class="sxs-lookup"><span data-stu-id="fb9d8-126">Record</span></span>|<span data-ttu-id="fb9d8-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="fb9d8-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="fb9d8-128">Especifica el tipo de transporte, que también es el nombre del adaptador usado con este controlador de recepción.</span><span class="sxs-lookup"><span data-stu-id="fb9d8-128">Specifies the transport type, which is also the name of the adapter used with this receive handler.</span></span>|<span data-ttu-id="fb9d8-129">Necesario</span><span class="sxs-lookup"><span data-stu-id="fb9d8-129">Required</span></span>|<span data-ttu-id="fb9d8-130">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="fb9d8-130">Default value: none</span></span>|