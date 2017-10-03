---
title: 'Error: demasiadas entradas de datos en el nodo | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tooManyDataInputsToNode
ms.assetid: 176805f0-2d6d-4072-b866-132b98c7e4b5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9e465f861c4048708f41ea86f04ffd52375dec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-data-inputs-to-node"></a><span data-ttu-id="454c8-102">Error: demasiadas entradas de datos en el nodo</span><span class="sxs-lookup"><span data-stu-id="454c8-102">Error - Too Many Data Inputs to Node</span></span>
<span data-ttu-id="454c8-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="454c8-103">**Error Code**</span></span>  
  
 <span data-ttu-id="454c8-104">btm1005</span><span class="sxs-lookup"><span data-stu-id="454c8-104">btm1005</span></span>  
  
 <span data-ttu-id="454c8-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="454c8-105">**Explanation**</span></span>  
  
 <span data-ttu-id="454c8-106">Hay un mayor número de vínculos conectados al nodo indicado en el esquema de destino que el número de vínculos de entrada a la **bucle** functoid que esté conectado al nodo antecesor del nodo indicado.</span><span class="sxs-lookup"><span data-stu-id="454c8-106">There are a greater number of links connected to the indicated node in the destination schema than the number of input links to the **Looping** functoid that is connected to an ancestor node of the indicated node.</span></span> <span data-ttu-id="454c8-107">El número de vínculos, tanto del primer tipo como del segundo, debe coincidir.</span><span class="sxs-lookup"><span data-stu-id="454c8-107">The number of links of the former and latter types should match.</span></span>  
  
 <span data-ttu-id="454c8-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="454c8-108">**User Action**</span></span>  
  
 <span data-ttu-id="454c8-109">Repetición del trabajo el número de vínculos conectados al nodo indicado y a la **bucle** functoid conectado al nodo antecesor para que coincidan.</span><span class="sxs-lookup"><span data-stu-id="454c8-109">Rework the number of links connected to the indicated node and to the **Looping** functoid connected to the ancestor node so that they match.</span></span>