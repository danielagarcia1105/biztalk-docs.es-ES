---
title: "Error - el vínculo de salida XSLT no es válido el Functoid de secuencias de comandos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.outputLinkForXsltNotValid
ms.assetid: cdf8e779-6cf6-4d9c-8655-f8b406498fb7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd597a3953db76087086c7ea9038e9fa1fd87eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---output-link-for-xslt-scripting-functoid-not-valid"></a><span data-ttu-id="31390-102">Error - el vínculo de salida XSLT no es válido el Functoid de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="31390-102">Error - Output Link For XSLT Scripting Functoid Not Valid</span></span>
<span data-ttu-id="31390-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="31390-103">**Error Code**</span></span>  
  
 <span data-ttu-id="31390-104">btm1075</span><span class="sxs-lookup"><span data-stu-id="31390-104">btm1075</span></span>  
  
 <span data-ttu-id="31390-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="31390-105">**Explanation**</span></span>  
  
 <span data-ttu-id="31390-106">El vínculo de salida de la correspondiente **secuencias de comandos** functoid configurado para utilizar XSLT en línea o una plantilla de llamada XSLT no es válido.</span><span class="sxs-lookup"><span data-stu-id="31390-106">The output link of the relevant **Scripting** functoid configured to use inline XSLT or an XSLT Call Template is not valid.</span></span> <span data-ttu-id="31390-107">El resultado de estos **secuencias de comandos** functoids debe estar conectados directamente a un nodo del esquema de destino (y no a otro functoid, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="31390-107">The output of such **Scripting** functoids must be connected directly to a node in the destination schema (and not to another functoid, for example).</span></span>  
  
 <span data-ttu-id="31390-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="31390-108">**User Action**</span></span>  
  
 <span data-ttu-id="31390-109">Asegúrese de que conecta el vínculo de salida de la correspondiente **secuencias de comandos** functoid directamente a un nodo del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="31390-109">Ensure that you connect the output link from the relevant **Scripting** functoid directly to a node in the destination schema.</span></span>