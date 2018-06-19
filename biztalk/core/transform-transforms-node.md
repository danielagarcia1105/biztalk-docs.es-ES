---
title: Transformación (nodo transformaciones) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: 2d1387f1-1668-4982-a717-52478e2a91f9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33e70e5a2bcba2925941e727034b90c9fe4b1418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279172"
---
# <a name="transform-transforms-node"></a><span data-ttu-id="49556-102">Transformación (nodo Transformaciones)</span><span class="sxs-lookup"><span data-stu-id="49556-102">Transform (Transforms Node)</span></span>
<span data-ttu-id="49556-103">El nodo Transformación del nodo Transformaciones de un archivo de enlace contiene información específica acerca de una asignación de BizTalk Server que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="49556-103">The Transform node of the Transforms node of a binding file contains specific information about a BizTalk Server map that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transform-node"></a><span data-ttu-id="49556-104">Nodos del nodo Transformación</span><span class="sxs-lookup"><span data-stu-id="49556-104">Nodes in the Transform node</span></span>  
 <span data-ttu-id="49556-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="49556-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="49556-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="49556-106">**Name**</span></span>|<span data-ttu-id="49556-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="49556-107">**Node Type**</span></span>|<span data-ttu-id="49556-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="49556-108">**Data Type**</span></span>|<span data-ttu-id="49556-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="49556-109">**Description**</span></span>|<span data-ttu-id="49556-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="49556-110">**Restrictions**</span></span>|<span data-ttu-id="49556-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="49556-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="49556-112">FullName</span><span class="sxs-lookup"><span data-stu-id="49556-112">FullName</span></span>|<span data-ttu-id="49556-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="49556-113">Attribute</span></span>|<span data-ttu-id="49556-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="49556-114">xs:string</span></span>|<span data-ttu-id="49556-115">Especifica el nombre completo de la asignación.</span><span class="sxs-lookup"><span data-stu-id="49556-115">Specifies the full name of the map.</span></span>|<span data-ttu-id="49556-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="49556-116">Not required</span></span>|<span data-ttu-id="49556-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="49556-117">Default value: empty</span></span>|  
|<span data-ttu-id="49556-118">AssemblyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="49556-118">AssemblyQualifiedName</span></span>|<span data-ttu-id="49556-119">Attribute</span><span class="sxs-lookup"><span data-stu-id="49556-119">Attribute</span></span>|<span data-ttu-id="49556-120">xs:string</span><span class="sxs-lookup"><span data-stu-id="49556-120">xs:string</span></span>|<span data-ttu-id="49556-121">Especifica el nombre completo del ensamblado de la asignación.</span><span class="sxs-lookup"><span data-stu-id="49556-121">Specifies the assembly qualified name of the map.</span></span>|<span data-ttu-id="49556-122">No requerido</span><span class="sxs-lookup"><span data-stu-id="49556-122">Not required</span></span>|<span data-ttu-id="49556-123">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="49556-123">Default value: empty</span></span>|