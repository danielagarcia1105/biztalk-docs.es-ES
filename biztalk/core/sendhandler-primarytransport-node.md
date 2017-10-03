---
title: SendHandler (nodo PrimaryTransport) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SendHandler node [binding file]
ms.assetid: c0b200ee-ecbc-4708-a2c8-c37cd6cd0060
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 029285e9b56aeb91bbca7a7c9eacf6abedc7ebbc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sendhandler-primarytransport-node"></a><span data-ttu-id="68b78-102">SendHandler (nodo PrimaryTransport)</span><span class="sxs-lookup"><span data-stu-id="68b78-102">SendHandler (PrimaryTransport Node)</span></span>
<span data-ttu-id="68b78-103">El nodo SendHandler del nodo PrimaryTransport de un archivo de enlace contiene información específica acerca del controlador de envío asociado a un transporte que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="68b78-103">The SendHandler node of the PrimaryTransport node of a binding file contains specific information about the send handler associated with a transport that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-sendhandler-node"></a><span data-ttu-id="68b78-104">Nodos del nodo SendHandler</span><span class="sxs-lookup"><span data-stu-id="68b78-104">Nodes in the SendHandler node</span></span>  
 <span data-ttu-id="68b78-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="68b78-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="68b78-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="68b78-106">**Name**</span></span>|<span data-ttu-id="68b78-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="68b78-107">**Node Type**</span></span>|<span data-ttu-id="68b78-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="68b78-108">**Data Type**</span></span>|<span data-ttu-id="68b78-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="68b78-109">**Description**</span></span>|<span data-ttu-id="68b78-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="68b78-110">**Restrictions**</span></span>|<span data-ttu-id="68b78-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="68b78-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="68b78-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="68b78-112">Name</span></span>|<span data-ttu-id="68b78-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="68b78-113">Attribute</span></span>|<span data-ttu-id="68b78-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="68b78-114">xs:string</span></span>|<span data-ttu-id="68b78-115">Especifica el nombre del controlador de envío asociado al transporte.</span><span class="sxs-lookup"><span data-stu-id="68b78-115">Specifies the name of the send handler associated with the transport.</span></span>|<span data-ttu-id="68b78-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="68b78-116">Not required</span></span>|<span data-ttu-id="68b78-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="68b78-117">Default value: empty</span></span>|  
|<span data-ttu-id="68b78-118">HostTrusted</span><span class="sxs-lookup"><span data-stu-id="68b78-118">HostTrusted</span></span>|<span data-ttu-id="68b78-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="68b78-119">Attribute</span></span>|<span data-ttu-id="68b78-120">xs:boolean</span><span class="sxs-lookup"><span data-stu-id="68b78-120">xs:boolean</span></span>|<span data-ttu-id="68b78-121">Especifica si el host asociado al controlador de envío es de confianza.</span><span class="sxs-lookup"><span data-stu-id="68b78-121">Specifies whether the host associated with the send handler is trusted.</span></span>|<span data-ttu-id="68b78-122">Necesario</span><span class="sxs-lookup"><span data-stu-id="68b78-122">Required</span></span>|<span data-ttu-id="68b78-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="68b78-123">Default value: none</span></span><br /><br /> <span data-ttu-id="68b78-124">Establecido en **true** si el host es de confianza, en caso contrario, se establece en **false**.</span><span class="sxs-lookup"><span data-stu-id="68b78-124">Set to **true** if host is trusted, otherwise set to **false**.</span></span>|  
|[<span data-ttu-id="68b78-125">Tipo de transporte</span><span class="sxs-lookup"><span data-stu-id="68b78-125">TransportType</span></span>](../core/transporttype.md)|<span data-ttu-id="68b78-126">Grabar</span><span class="sxs-lookup"><span data-stu-id="68b78-126">Record</span></span>|<span data-ttu-id="68b78-127">ProtocolType (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="68b78-127">ProtocolType (ComplexType)</span></span>|<span data-ttu-id="68b78-128">Especifica el tipo de transporte, que también es el nombre del adaptador usado con este controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="68b78-128">Specifies the transport type, which is also the name of the adapter used with this send handler.</span></span>|<span data-ttu-id="68b78-129">Necesario</span><span class="sxs-lookup"><span data-stu-id="68b78-129">Required</span></span>|<span data-ttu-id="68b78-130">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="68b78-130">Default value: none</span></span>|