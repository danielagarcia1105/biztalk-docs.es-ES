---
title: ModuleRef (nodo ModuleRefCollection) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRef node [binding file]
ms.assetid: 61787779-33bd-499a-a5c1-c1e0bd306b48
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ed580b022e9896ade824c8cf8eccc2458c7ddce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="moduleref-modulerefcollection-node"></a><span data-ttu-id="30cb1-102">ModuleRef (nodo ModuleRefCollection)</span><span class="sxs-lookup"><span data-stu-id="30cb1-102">ModuleRef (ModuleRefCollection Node)</span></span>
<span data-ttu-id="30cb1-103">El nodo ModuleRef de un archivo de enlace contiene información específica acerca de un ensamblado .NET que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="30cb1-103">The ModuleRef node of a binding file contains specific information about a .NET assembly that was exported with the binding file.</span></span> <span data-ttu-id="30cb1-104">Un nodo ModuleRef puede incluir, entre otros elementos, descripciones de ensamblados que contengan esquemas, orquestaciones y código personalizado.</span><span class="sxs-lookup"><span data-stu-id="30cb1-104">A ModuleRef node can include but is not limited to descriptions of assemblies that contain custom code, schemas, and orchestrations.</span></span>  
  
## <a name="nodes-in-the-moduleref-node"></a><span data-ttu-id="30cb1-105">Nodos del nodo ModuleRef</span><span class="sxs-lookup"><span data-stu-id="30cb1-105">Nodes in the ModuleRef node</span></span>  
 <span data-ttu-id="30cb1-106">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="30cb1-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="30cb1-107">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="30cb1-107">**Name**</span></span>|<span data-ttu-id="30cb1-108">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="30cb1-108">**Node Type**</span></span>|<span data-ttu-id="30cb1-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="30cb1-109">**Data Type**</span></span>|<span data-ttu-id="30cb1-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="30cb1-110">**Description**</span></span>|<span data-ttu-id="30cb1-111">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="30cb1-111">**Restrictions**</span></span>|<span data-ttu-id="30cb1-112">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="30cb1-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="30cb1-113">Servicios de</span><span class="sxs-lookup"><span data-stu-id="30cb1-113">Services</span></span>](../core/services-moduleref-node.md)|<span data-ttu-id="30cb1-114">Grabar</span><span class="sxs-lookup"><span data-stu-id="30cb1-114">Record</span></span>|<span data-ttu-id="30cb1-115">ArrayOfServiceRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="30cb1-115">ArrayOfServiceRef (ComplexType)</span></span>|<span data-ttu-id="30cb1-116">Nodo contenedor para servicios asociados a este ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="30cb1-116">Container node for services associated with this .NET assembly.</span></span>|<span data-ttu-id="30cb1-117">No requerido</span><span class="sxs-lookup"><span data-stu-id="30cb1-117">Not required</span></span>|<span data-ttu-id="30cb1-118">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="30cb1-118">Default value: none</span></span>|  
|[<span data-ttu-id="30cb1-119">TrackedSchemas (nodo ModuleRef)</span><span class="sxs-lookup"><span data-stu-id="30cb1-119">TrackedSchemas (ModuleRef Node)</span></span>](../core/trackedschemas-moduleref-node.md)|<span data-ttu-id="30cb1-120">Grabar</span><span class="sxs-lookup"><span data-stu-id="30cb1-120">Record</span></span>|<span data-ttu-id="30cb1-121">ArrayOfSchema (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="30cb1-121">ArrayOfSchema (ComplexType)</span></span>|<span data-ttu-id="30cb1-122">Nodo contenedor para esquemas asociados a este ensamblado .NET.</span><span class="sxs-lookup"><span data-stu-id="30cb1-122">Container node for schemas associated with this .NET assembly</span></span>|<span data-ttu-id="30cb1-123">No requerido</span><span class="sxs-lookup"><span data-stu-id="30cb1-123">Not required</span></span>|<span data-ttu-id="30cb1-124">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="30cb1-124">Default value: none</span></span>|