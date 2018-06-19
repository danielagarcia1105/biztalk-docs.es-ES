---
title: Transformaciones (nodo puertoEnvío) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transforms node [binding file]
ms.assetid: b405397b-e394-44fa-b507-93896f800f66
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1571a38841f6567279a27c58770f4198ba3eb56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278228"
---
# <a name="transforms-sendport-node"></a><span data-ttu-id="573aa-102">Transformaciones (nodo puertoEnvío)</span><span class="sxs-lookup"><span data-stu-id="573aa-102">Transforms (SendPort Node)</span></span>
<span data-ttu-id="573aa-103">El nodo Transformaciones del nodo puertoEnvío de un archivo de enlace contiene la colección de transformaciones salientes de un puerto de envío unidireccional que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="573aa-103">The Transforms node of the SendPort node of a binding file contains the collection of outbound transforms of a one way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-transforms-node"></a><span data-ttu-id="573aa-104">Nodos del nodo Transformaciones</span><span class="sxs-lookup"><span data-stu-id="573aa-104">Nodes in the Transforms node</span></span>  
 <span data-ttu-id="573aa-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="573aa-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="573aa-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="573aa-106">**Name**</span></span>|<span data-ttu-id="573aa-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="573aa-107">**Node Type**</span></span>|<span data-ttu-id="573aa-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="573aa-108">**Data Type**</span></span>|<span data-ttu-id="573aa-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="573aa-109">**Description**</span></span>|<span data-ttu-id="573aa-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="573aa-110">**Restrictions**</span></span>|<span data-ttu-id="573aa-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="573aa-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="573aa-112">Transformación (nodo puertoEnvío transformaciones)</span><span class="sxs-lookup"><span data-stu-id="573aa-112">Transform (SendPort-Transforms Node)</span></span>](../core/transform-sendport-transforms-node.md)|<span data-ttu-id="573aa-113">Grabar</span><span class="sxs-lookup"><span data-stu-id="573aa-113">Record</span></span>|<span data-ttu-id="573aa-114">Transformación (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="573aa-114">Transform (ComplexType)</span></span>|<span data-ttu-id="573aa-115">Especifica un asignador de BizTalk Server, o una transformación, es decir, un elemento que representa la asignación entre un esquema de origen y uno de destino.</span><span class="sxs-lookup"><span data-stu-id="573aa-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="573aa-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="573aa-116">Not required</span></span>|<span data-ttu-id="573aa-117">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="573aa-117">Default value: none</span></span>|