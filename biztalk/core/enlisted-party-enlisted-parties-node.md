---
title: Da de alta entidades (nodo entidades dadas de alta) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624f74d3b49b80e8000723c3f7451c52b37c8d3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239956"
---
# <a name="enlisted-party-enlisted-parties-node"></a><span data-ttu-id="aa441-102">Entidad dada de alta (nodo de Entidades dadas de alta)</span><span class="sxs-lookup"><span data-stu-id="aa441-102">Enlisted Party (Enlisted Parties Node)</span></span>
<span data-ttu-id="aa441-103">El nodo Entidad dada de alta de un archivo de enlace contiene información específica acerca de una entidad dada de alta asociada a un rol que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="aa441-103">The Enlisted Party node of a binding file contains specific information about an enlisted party associated with a role that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-enlisted-party-node"></a><span data-ttu-id="aa441-104">Nodos del nodo Entidad dada de alta</span><span class="sxs-lookup"><span data-stu-id="aa441-104">Nodes in the Enlisted Party node</span></span>  
 <span data-ttu-id="aa441-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="aa441-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="aa441-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="aa441-106">**Name**</span></span>|<span data-ttu-id="aa441-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="aa441-107">**Node Type**</span></span>|<span data-ttu-id="aa441-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="aa441-108">**Data Type**</span></span>|<span data-ttu-id="aa441-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="aa441-109">**Description**</span></span>|<span data-ttu-id="aa441-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="aa441-110">**Restrictions**</span></span>|<span data-ttu-id="aa441-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="aa441-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="aa441-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="aa441-112">Name</span></span>|<span data-ttu-id="aa441-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="aa441-113">Attribute</span></span>|<span data-ttu-id="aa441-114">xs:string</span><span class="sxs-lookup"><span data-stu-id="aa441-114">xs:string</span></span>|<span data-ttu-id="aa441-115">Especifica el nombre de la entidad dada de alta.</span><span class="sxs-lookup"><span data-stu-id="aa441-115">Specifies the name of the enlisted party</span></span>|<span data-ttu-id="aa441-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="aa441-116">Not required</span></span>|<span data-ttu-id="aa441-117">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="aa441-117">Default value: empty</span></span>|  
|[<span data-ttu-id="aa441-118">Asignaciones</span><span class="sxs-lookup"><span data-stu-id="aa441-118">Mappings</span></span>](../core/mappings-enlisted-party-node.md)|<span data-ttu-id="aa441-119">Grabar</span><span class="sxs-lookup"><span data-stu-id="aa441-119">Record</span></span>|<span data-ttu-id="aa441-120">ArrayOfEnlistedPartyMapping (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="aa441-120">ArrayOfEnlistedPartyMapping (ComplexType)</span></span>|<span data-ttu-id="aa441-121">Nodo contenedor de las asignaciones entre puertos de entidad y operaciones de tipo de puerto de rol.</span><span class="sxs-lookup"><span data-stu-id="aa441-121">Container node for the mappings between party ports and role port type operations.</span></span>|<span data-ttu-id="aa441-122">No requerido</span><span class="sxs-lookup"><span data-stu-id="aa441-122">Not required</span></span>|<span data-ttu-id="aa441-123">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="aa441-123">Default value: none</span></span>|