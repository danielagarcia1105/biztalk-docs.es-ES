---
title: SendPortRef (nodo puertosEnvío) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9290a535ebcaf0c23097cacbd3412f64c2808f40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269964"
---
# <a name="sendportref-sendports-node"></a><span data-ttu-id="c45ae-102">SendPortRef (nodo SendPorts)</span><span class="sxs-lookup"><span data-stu-id="c45ae-102">SendPortRef (SendPorts Node)</span></span>
<span data-ttu-id="c45ae-103">El nodo SendPortRef del nodo SendPorts de un archivo de enlace especifica el nombre del puerto de envío al que hace referencia una lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="c45ae-103">The SendPortRef node of the SendPorts node of a binding file specifies the name of a send port referenced by a distribution list.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c45ae-104">A una lista de distribución se hace referencia como un grupo de puertos de envío en el administrador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c45ae-104">A distribution list is referred to as a send port group in the BizTalk Administrator.</span></span>  
  
## <a name="nodes-in-the-sendportref-node"></a><span data-ttu-id="c45ae-105">Nodos del nodo SendPortRef</span><span class="sxs-lookup"><span data-stu-id="c45ae-105">Nodes in the SendPortRef node</span></span>  
 <span data-ttu-id="c45ae-106">En la siguiente tabla se enumeran las propiedades que se pueden definir para este nodo de archivo de enlace:</span><span class="sxs-lookup"><span data-stu-id="c45ae-106">The following table lists the properties that can be set for this node of a binding file:</span></span>  
  
|<span data-ttu-id="c45ae-107">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="c45ae-107">**Name**</span></span>|<span data-ttu-id="c45ae-108">**Tipo de nodo**</span><span class="sxs-lookup"><span data-stu-id="c45ae-108">**Node Type**</span></span>|<span data-ttu-id="c45ae-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c45ae-109">**Data Type**</span></span>|<span data-ttu-id="c45ae-110">**Description**</span><span class="sxs-lookup"><span data-stu-id="c45ae-110">**Description**</span></span>|<span data-ttu-id="c45ae-111">**Restricciones**</span><span class="sxs-lookup"><span data-stu-id="c45ae-111">**Restrictions**</span></span>|<span data-ttu-id="c45ae-112">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="c45ae-112">**Comments**</span></span>|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|<span data-ttu-id="c45ae-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="c45ae-113">Name</span></span>|<span data-ttu-id="c45ae-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="c45ae-114">Attribute</span></span>|<span data-ttu-id="c45ae-115">xs:string</span><span class="sxs-lookup"><span data-stu-id="c45ae-115">xs:string</span></span>|<span data-ttu-id="c45ae-116">Especifica el nombre del puerto de envío al que hace referencia la lista de distribución.</span><span class="sxs-lookup"><span data-stu-id="c45ae-116">Specifies the name of the send port referenced by the distribution list.</span></span>|<span data-ttu-id="c45ae-117">No requerido</span><span class="sxs-lookup"><span data-stu-id="c45ae-117">Not required</span></span>|<span data-ttu-id="c45ae-118">Valor predeterminado: vacío</span><span class="sxs-lookup"><span data-stu-id="c45ae-118">Default value: empty</span></span>|