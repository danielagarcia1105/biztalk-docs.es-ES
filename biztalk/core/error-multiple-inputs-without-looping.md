---
title: Error - varias entradas sin bucle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a8a11b25c3c1df52827bdbf4098f0cd37bdd8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-inputs-without-looping"></a><span data-ttu-id="8597b-102">Error - varias entradas sin bucle</span><span class="sxs-lookup"><span data-stu-id="8597b-102">Error - Multiple Inputs Without Looping</span></span>
<span data-ttu-id="8597b-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="8597b-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8597b-104">btm1004</span><span class="sxs-lookup"><span data-stu-id="8597b-104">btm1004</span></span>  
  
 <span data-ttu-id="8597b-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="8597b-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8597b-106">Varios vínculos conectados al nodo indicado en el esquema de destino, lo cual solo es válido cuando uno de los nodos antecesores del nodo indicado está conectado a un **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="8597b-106">Multiple links are connected to the indicated node in the destination schema, which is only valid when one of the ancestor nodes of the indicated node is connected to a **Looping** functoid.</span></span>  
  
 <span data-ttu-id="8597b-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="8597b-107">**User Action**</span></span>  
  
 <span data-ttu-id="8597b-108">Elimine todos los vínculos del nodo indicado en el esquema de destino menos uno, o bien conecte uno de los nodos primarios del nodo indicado a un functoid de Bucle.</span><span class="sxs-lookup"><span data-stu-id="8597b-108">Either remove all but one of the links to the indicated node in the destination schema, or connect one of the ancestor nodes of the indicated node to a looping functoid.</span></span>