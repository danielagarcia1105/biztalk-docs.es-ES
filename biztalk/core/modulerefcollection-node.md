---
title: ModuleRefCollection (nodo) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ModuleRefCollection node [binding file]
ms.assetid: fa8593bf-6548-4615-9f98-1e0eadde9aa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 039cabd380195f840e9ffb99de5071026b3810c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="modulerefcollection-node"></a><span data-ttu-id="2c941-102">ModuleRefCollection (nodo)</span><span class="sxs-lookup"><span data-stu-id="2c941-102">ModuleRefCollection Node</span></span>
<span data-ttu-id="2c941-103">La sección ModuleRefCollection de un archivo de enlace es el nodo primario de todos los nodos ModuleRef que contienen información específica acerca de los ensamblados .NET que se exportan con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2c941-103">The ModuleRefCollection section of a binding file is the parent node for all of the ModuleRef nodes which contain specific information about .NET assemblies exported with the binding file.</span></span>  
  
## <a name="entries-in-the-modulerefcollection-section"></a><span data-ttu-id="2c941-104">Entradas en la sección ModuleRefCollection</span><span class="sxs-lookup"><span data-stu-id="2c941-104">Entries in the ModuleRefCollection section</span></span>  
 <span data-ttu-id="2c941-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para los nodos en esta sección de un archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2c941-105">The following table lists the properties that can be set for the nodes in this section of a binding file:</span></span>  
  
|<span data-ttu-id="2c941-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2c941-106">**Name**</span></span>|<span data-ttu-id="2c941-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="2c941-107">**Node Type**</span></span>|<span data-ttu-id="2c941-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="2c941-108">**Data Type**</span></span>|<span data-ttu-id="2c941-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="2c941-109">**Description**</span></span>|<span data-ttu-id="2c941-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="2c941-110">**Restrictions**</span></span>|<span data-ttu-id="2c941-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="2c941-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="2c941-112">ModuleRef</span><span class="sxs-lookup"><span data-stu-id="2c941-112">ModuleRef</span></span>](../core/moduleref-modulerefcollection-node.md)|<span data-ttu-id="2c941-113">Grabar</span><span class="sxs-lookup"><span data-stu-id="2c941-113">Record</span></span>|<span data-ttu-id="2c941-114">ModuleRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="2c941-114">ModuleRef (ComplexType)</span></span>|<span data-ttu-id="2c941-115">Nodo contenedor para un módulo de ensamblado .NET exportado con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="2c941-115">Container node for a .NET assembly module exported with the binding file.</span></span>|<span data-ttu-id="2c941-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="2c941-116">Not required</span></span>|<span data-ttu-id="2c941-117">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="2c941-117">Default value: None</span></span>|