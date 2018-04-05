---
title: TrackedSchemas (nodo ModuleRef) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TrackedSchemas node [binding file]
ms.assetid: a2b99fbf-df6b-4a94-97b8-ac5eb819604f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303aeb1ed17b001583a596d5b550faf63ea1200b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="trackedschemas-moduleref-node"></a><span data-ttu-id="fe150-102">TrackedSchemas (nodo ModuleRef)</span><span class="sxs-lookup"><span data-stu-id="fe150-102">TrackedSchemas (ModuleRef Node)</span></span>
<span data-ttu-id="fe150-103">El nodo TrackedSchemas de un archivo de enlace es el nodo primario de todos los nodos Esquema que describen los esquemas enlazados con el servicio que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fe150-103">The TrackedSchemas node of a binding file is the parent node for all of the Schema nodes which describe the schemas bound to the service that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-trackedschemas-node"></a><span data-ttu-id="fe150-104">Nodos del nodo TrackedSchemas</span><span class="sxs-lookup"><span data-stu-id="fe150-104">Nodes in the TrackedSchemas node</span></span>  
 <span data-ttu-id="fe150-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="fe150-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="fe150-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fe150-106">**Name**</span></span>|<span data-ttu-id="fe150-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="fe150-107">**Node Type**</span></span>|<span data-ttu-id="fe150-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fe150-108">**Data Type**</span></span>|<span data-ttu-id="fe150-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="fe150-109">**Description**</span></span>|<span data-ttu-id="fe150-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="fe150-110">**Restrictions**</span></span>|<span data-ttu-id="fe150-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="fe150-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="fe150-112">Esquema</span><span class="sxs-lookup"><span data-stu-id="fe150-112">Schema</span></span>](../core/schema-trackedschemas-node.md)|<span data-ttu-id="fe150-113">Grabar</span><span class="sxs-lookup"><span data-stu-id="fe150-113">Record</span></span>|<span data-ttu-id="fe150-114">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="fe150-114">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="fe150-115">Nodo contenedor de los esquemas que están enlazados con el servicio que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fe150-115">Container node for the schemas that are bound to the service that is exported with the binding file.</span></span>|<span data-ttu-id="fe150-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="fe150-116">Not required</span></span>|<span data-ttu-id="fe150-117">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="fe150-117">Default value: none</span></span>|