---
title: InboundTransforms (nodo puertoEnvío) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- InboundTransforms node [binding file]
ms.assetid: 5ed239b9-13d8-4099-b779-08f589a722e9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03567b5ea6095e38370260e1f17055ab40da4d6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257316"
---
# <a name="inboundtransforms-sendport-node"></a><span data-ttu-id="6a9cd-102">InboundTransforms (nodo puertoEnvío)</span><span class="sxs-lookup"><span data-stu-id="6a9cd-102">InboundTransforms (SendPort Node)</span></span>
<span data-ttu-id="6a9cd-103">El nodo InboundTransforms del nodo puertoEnvío de un archivo de enlace contiene la colección de transformaciones de entrada de un puerto de envío bidireccional que se exporta con el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="6a9cd-103">The InboundTransforms node of the SendPort node of a binding file contains the collection of inbound transforms of a two-way send port that is exported with the binding file.</span></span>  
  
## <a name="nodes-in-the-inboundtransforms-node"></a><span data-ttu-id="6a9cd-104">Nodos del nodo InboundTransforms</span><span class="sxs-lookup"><span data-stu-id="6a9cd-104">Nodes in the InboundTransforms node</span></span>  
 <span data-ttu-id="6a9cd-105">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="6a9cd-105">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="6a9cd-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6a9cd-106">**Name**</span></span>|<span data-ttu-id="6a9cd-107">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="6a9cd-107">**Node Type**</span></span>|<span data-ttu-id="6a9cd-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6a9cd-108">**Data Type**</span></span>|<span data-ttu-id="6a9cd-109">**Description**</span><span class="sxs-lookup"><span data-stu-id="6a9cd-109">**Description**</span></span>|<span data-ttu-id="6a9cd-110">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="6a9cd-110">**Restrictions**</span></span>|<span data-ttu-id="6a9cd-111">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="6a9cd-111">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="6a9cd-112">Transformación (nodo InboundTransforms)</span><span class="sxs-lookup"><span data-stu-id="6a9cd-112">Transform (InboundTransforms Node)</span></span>](../core/transform-inboundtransforms-node.md)|<span data-ttu-id="6a9cd-113">Grabar</span><span class="sxs-lookup"><span data-stu-id="6a9cd-113">Record</span></span>|<span data-ttu-id="6a9cd-114">Transformación (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="6a9cd-114">Transform (ComplexType)</span></span>|<span data-ttu-id="6a9cd-115">Especifica un asignador de BizTalk Server, o una transformación, es decir, un elemento que representa la asignación entre un esquema de origen y uno de destino.</span><span class="sxs-lookup"><span data-stu-id="6a9cd-115">Specifies a BizTalk Server map, or transform, which is an item that represents the mapping between a source schema and destination schema.</span></span>|<span data-ttu-id="6a9cd-116">No requerido</span><span class="sxs-lookup"><span data-stu-id="6a9cd-116">Not required</span></span>|<span data-ttu-id="6a9cd-117">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="6a9cd-117">Default value: none</span></span>|