---
title: Transformaciones (nodo puertoRecepción) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transforms node [binding file]
ms.assetid: cd32f2fe-b70a-4153-86ec-bb1aa9bad0e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7d039d95a1f28afa468078ff7547e9f298633bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transforms-receiveport-node"></a><span data-ttu-id="76bd0-102">Transformaciones (nodo puertoRecepción)</span><span class="sxs-lookup"><span data-stu-id="76bd0-102">Transforms (ReceivePort Node)</span></span>
<span data-ttu-id="76bd0-103">El nodo Transformaciones del nodo puertoRecepción de un archivo de enlace contiene la colección de transformaciones de entrada de un puerto de recepción unidireccional que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="76bd0-103">The Transforms node of the ReceivePort node of a binding file contains the collection of inbound transforms of a one way receive port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="76bd0-104">Nodos del nodo Transformaciones</span><span class="sxs-lookup"><span data-stu-id="76bd0-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="76bd0-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="76bd0-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="76bd0-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="76bd0-106">**Name**</span></span>|<span data-ttu-id="76bd0-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="76bd0-107">**Node Type**</span></span>|<span data-ttu-id="76bd0-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="76bd0-108">**Data Type**</span></span>|<span data-ttu-id="76bd0-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="76bd0-109">**Description**</span></span>|<span data-ttu-id="76bd0-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="76bd0-110">**Restrictions**</span></span>|<span data-ttu-id="76bd0-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="76bd0-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="76bd0-112">Transformación (nodo transformaciones)</span><span class="sxs-lookup"><span data-stu-id="76bd0-112">Transform (Transforms Node)</span></span>](../core/transform-transforms-node.md)|<span data-ttu-id="76bd0-113">Grabar</span><span class="sxs-lookup"><span data-stu-id="76bd0-113">Record</span></span>|<span data-ttu-id="76bd0-114">Transformación (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="76bd0-114">Transform (ComplexType)</span></span>|<span data-ttu-id="76bd0-115">Especifica un asignador de BizTalk Server, o una transformación, es decir, un elemento que representa la asignación entre un esquema de origen y uno de destino.</span><span class="sxs-lookup"><span data-stu-id="76bd0-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="76bd0-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="76bd0-116">Not required</span></span>|<span data-ttu-id="76bd0-117">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="76bd0-117">Default value: none</span></span>|