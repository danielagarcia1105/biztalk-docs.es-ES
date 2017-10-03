---
title: "Transformación (nodo puertoEnvío transformaciones) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: db9a82b2-9bc1-4bd8-8d98-a708a8d25b35
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a54ed1f25b762d12f598bca84da9b9c3ddd26a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transform-sendport-transforms-node"></a><span data-ttu-id="79da3-102">Transformación (nodo puertoEnvío transformaciones)</span><span class="sxs-lookup"><span data-stu-id="79da3-102">Transform (SendPort-Transforms Node)</span></span>
<span data-ttu-id="79da3-103">El nodo Transformación del nodo Transformaciones de un archivo de enlace contiene información específica acerca de una asignación de BizTalk Server que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="79da3-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="79da3-104">Nodos del nodo Transformación</span><span class="sxs-lookup"><span data-stu-id="79da3-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="79da3-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="79da3-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="79da3-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="79da3-106">**Name**</span></span>|<span data-ttu-id="79da3-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="79da3-107">**Node Type**</span></span>|<span data-ttu-id="79da3-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="79da3-108">**Data Type**</span></span>|<span data-ttu-id="79da3-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="79da3-109">**Description**</span></span>|<span data-ttu-id="79da3-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="79da3-110">**Restrictions**</span></span>|<span data-ttu-id="79da3-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="79da3-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="79da3-112">FullName</span><span class="sxs-lookup"><span data-stu-id="79da3-112">FullName</span></span>|<span data-ttu-id="79da3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="79da3-113">Attribute</span></span>|<span data-ttu-id="79da3-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="79da3-114">xs:string</span></span>|<span data-ttu-id="79da3-115">Especifica el nombre completo de la asignación.</span><span class="sxs-lookup"><span data-stu-id="79da3-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="79da3-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="79da3-116">Not required</span></span>|<span data-ttu-id="79da3-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="79da3-117">Default value: empty</span></span>|  
|<span data-ttu-id="79da3-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="79da3-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="79da3-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="79da3-119">Attribute</span></span>|<span data-ttu-id="79da3-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="79da3-120">xs:string</span></span>|<span data-ttu-id="79da3-121">Especifica el nombre completo del ensamblado de la asignación.</span><span class="sxs-lookup"><span data-stu-id="79da3-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="79da3-122">No requerido</span><span class="sxs-lookup"><span data-stu-id="79da3-122">Not required</span></span>|<span data-ttu-id="79da3-123">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="79da3-123">Default value: empty</span></span>|