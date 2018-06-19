---
title: Mapping (nodo Mappings) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c62d46e4d5c2b73eee5094ecda0e20c039798a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262524"
---
# <a name="mapping-mappings-node"></a><span data-ttu-id="bc76a-102">Mapping (nodo Mappings)</span><span class="sxs-lookup"><span data-stu-id="bc76a-102">Mapping (Mappings Node)</span></span>
<span data-ttu-id="bc76a-103">El nodo Mapping de un archivo de enlace describe la asignación entre un puerto de entidad y una operación de tipo de puerto de rol para la entidad dada de alta.</span><span class="sxs-lookup"><span data-stu-id="bc76a-103">The Mapping node of a binding file describes the mapping between a party port and role port type operation for the enlisted party.</span></span>  
  
## <a name="nodes-in-the-mapping-node"></a><span data-ttu-id="bc76a-104">Nodos del nodo Mapping</span><span class="sxs-lookup"><span data-stu-id="bc76a-104">Nodes in the Mapping node</span></span>  
 <span data-ttu-id="bc76a-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="bc76a-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="bc76a-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="bc76a-106">**Name**</span></span>|<span data-ttu-id="bc76a-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="bc76a-107">**Node Type**</span></span>|<span data-ttu-id="bc76a-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="bc76a-108">**Data Type**</span></span>|<span data-ttu-id="bc76a-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="bc76a-109">**Description**</span></span>|<span data-ttu-id="bc76a-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="bc76a-110">**Restrictions**</span></span>|<span data-ttu-id="bc76a-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="bc76a-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="bc76a-112">PortTypeName</span><span class="sxs-lookup"><span data-stu-id="bc76a-112">PortTypeName</span></span>|<span data-ttu-id="bc76a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc76a-113">Attribute</span></span>|<span data-ttu-id="bc76a-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc76a-114">xs:string</span></span>|<span data-ttu-id="bc76a-115">Especifica el nombre del tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="bc76a-115">Specifies the name of the port type.</span></span>|<span data-ttu-id="bc76a-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="bc76a-116">Not required</span></span>|<span data-ttu-id="bc76a-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="bc76a-117">Default value: empty</span></span>|  
|<span data-ttu-id="bc76a-118">OperationName</span><span class="sxs-lookup"><span data-stu-id="bc76a-118">OperationName</span></span>|<span data-ttu-id="bc76a-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc76a-119">Attribute</span></span>|<span data-ttu-id="bc76a-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc76a-120">xs:string</span></span>|<span data-ttu-id="bc76a-121">Especifica la operación que pertenece a este tipo de puerto.</span><span class="sxs-lookup"><span data-stu-id="bc76a-121">Specifies the operation belonging to this port type.</span></span>|<span data-ttu-id="bc76a-122">No requerido</span><span class="sxs-lookup"><span data-stu-id="bc76a-122">Not required</span></span>|<span data-ttu-id="bc76a-123">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="bc76a-123">Default value: empty</span></span>|  
|[<span data-ttu-id="bc76a-124">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="bc76a-124">SendPortRef</span></span>](../core/sendportref-mapping-node.md)|<span data-ttu-id="bc76a-125">Grabar</span><span class="sxs-lookup"><span data-stu-id="bc76a-125">Record</span></span>|<span data-ttu-id="bc76a-126">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="bc76a-126">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="bc76a-127">Nodo contenedor de la lista de puertos de envío asociados a la asignación.</span><span class="sxs-lookup"><span data-stu-id="bc76a-127">Container node for the list of send ports associated with a mapping.</span></span>|<span data-ttu-id="bc76a-128">No requerido</span><span class="sxs-lookup"><span data-stu-id="bc76a-128">Not required</span></span>|<span data-ttu-id="bc76a-129">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="bc76a-129">Default value: none</span></span>|