---
title: DistributionListRef (nodo puerto) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionListRef node [binding file]
ms.assetid: 5d0d0121-1bcc-4c26-a1a3-8937ac7c282a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 665b8c2115c5c4681f7cff057481b6ce7da320ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239756"
---
# <a name="distributionlistref-port-node"></a><span data-ttu-id="6988c-102">DistributionListRef (nodo Puerto)</span><span class="sxs-lookup"><span data-stu-id="6988c-102">DistributionListRef (Port Node)</span></span>
<span data-ttu-id="6988c-103">El nodo DistributionListRef del nodo Puerto de un archivo de enlace contiene información acerca de una lista de distribución a la que hace referencia un servicio.</span><span class="sxs-lookup"><span data-stu-id="6988c-103">The DistributionListRef node of the Port node of a binding file contains information about a distribution list that is referenced by a service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6988c-104">A las listas de distribución se hace referencia como grupos de puertos de envío en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="6988c-104">Distribution lists are referred to as send port groups in the BizTalk Server Administration Console.</span></span>  
  
## <a name="nodes-in-the-distributionlistref-node"></a><span data-ttu-id="6988c-105">Nodos del nodo DistributionListRef</span><span class="sxs-lookup"><span data-stu-id="6988c-105">Nodes in the DistributionListRef node</span></span>  
 <span data-ttu-id="6988c-106">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="6988c-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="6988c-107">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="6988c-107">**Name**</span></span>|<span data-ttu-id="6988c-108">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="6988c-108">**Node Type**</span></span>|<span data-ttu-id="6988c-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6988c-109">**Data Type**</span></span>|<span data-ttu-id="6988c-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="6988c-110">**Description**</span></span>|<span data-ttu-id="6988c-111">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="6988c-111">**Restrictions**</span></span>|<span data-ttu-id="6988c-112">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="6988c-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="6988c-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="6988c-113">Name</span></span>|<span data-ttu-id="6988c-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="6988c-114">Attribute</span></span>|<span data-ttu-id="6988c-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="6988c-115">xs:string</span></span>|<span data-ttu-id="6988c-116">Especifica el nombre de una lista de distribución a la que hace referencia un servicio.</span><span class="sxs-lookup"><span data-stu-id="6988c-116">Specifies the name of a distribution list that is referenced by a service.</span></span>|<span data-ttu-id="6988c-117">No requerido</span><span class="sxs-lookup"><span data-stu-id="6988c-117">Not required</span></span>|<span data-ttu-id="6988c-118">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="6988c-118">Default value: empty</span></span>|