---
title: PuertosEnvío (nodo DistributionList) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPorts node [binding file]
ms.assetid: 9cb645fa-cb9c-44eb-9f98-2fc507b2be67
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9eaf692bd61913e604731fc2e2cea373fd31f48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269636"
---
# <a name="sendports-distributionlist-node"></a><span data-ttu-id="01623-102">PuertosEnvío (nodo DistributionList)</span><span class="sxs-lookup"><span data-stu-id="01623-102">SendPorts (DistributionList Node)</span></span>
<span data-ttu-id="01623-103">El nodo SendPorts del nodo DistributionList de un archivo de enlace es el nodo contenedor de las referencias del puerto de envío que aparecen en la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="01623-103">The SendPorts node of the DistributionList node of a binding file is the container node for the send port references in the distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01623-104">A una lista de distribución se hace referencia como un grupo de puertos de envío en el administrador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="01623-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendports-node"></a><span data-ttu-id="01623-105">Nodos del nodo SendPorts</span><span class="sxs-lookup"><span data-stu-id="01623-105">Nodes in the SendPorts node</span></span>  
 <span data-ttu-id="01623-106">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="01623-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="01623-107">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="01623-107">**Name**</span></span>|<span data-ttu-id="01623-108">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="01623-108">**Node Type**</span></span>|<span data-ttu-id="01623-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="01623-109">**Data Type**</span></span>|<span data-ttu-id="01623-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="01623-110">**Description**</span></span>|<span data-ttu-id="01623-111">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="01623-111">**Restrictions**</span></span>|<span data-ttu-id="01623-112">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="01623-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[<span data-ttu-id="01623-113">SendPortRef</span><span class="sxs-lookup"><span data-stu-id="01623-113">SendPortRef</span></span>](../core/sendportref-sendports-node.md)|<span data-ttu-id="01623-114">Grabar</span><span class="sxs-lookup"><span data-stu-id="01623-114">Record</span></span>|<span data-ttu-id="01623-115">SendPortRef (ComplexType)</span><span class="sxs-lookup"><span data-stu-id="01623-115">SendPortRef (ComplexType)</span></span>|<span data-ttu-id="01623-116">Nodo contenedor de una referencia a un puerto de envío realizada por la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="01623-116">Container node for a reference to a send port made by the distribution list.</span></span>|<span data-ttu-id="01623-117">No requerido</span><span class="sxs-lookup"><span data-stu-id="01623-117">Not required</span></span>|<span data-ttu-id="01623-118">Valor predeterminado: ninguno</span><span class="sxs-lookup"><span data-stu-id="01623-118">Default value: none</span></span>|