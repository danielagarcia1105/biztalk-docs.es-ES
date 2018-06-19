---
title: Invocar reglas de negocios en orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], business rules
- business rules, orchestrations
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
- orchestrations, business rules
ms.assetid: ac3a3277-e9ea-4f40-9326-c63076c6b90e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ecbb9738089dfa2d885f9aa45ac12e92ed27aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261828"
---
# <a name="invoking-business-rules-in-orchestrations"></a><span data-ttu-id="b2b91-102">Invocar reglas de negocios en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="b2b91-102">Invoking Business Rules in Orchestrations</span></span>
<span data-ttu-id="b2b91-103">Puede invocar una directiva (o conjunto de reglas) desde una orquestación mediante el uso de la **reglas de llamada** forma.</span><span class="sxs-lookup"><span data-stu-id="b2b91-103">You can invoke a policy (or rule set) from an orchestration by using the **Call Rules** shape.</span></span> <span data-ttu-id="b2b91-104">La directiva invoca el motor de reglas, que opera en las reglas de la directiva.</span><span class="sxs-lookup"><span data-stu-id="b2b91-104">The policy invokes the rule engine, which operates on the rules in the policy.</span></span>  
  
 <span data-ttu-id="b2b91-105">Además de utilizar reglas de llamada, las reglas de motor puede llamarse mediante programación de la expresión de código, por ejemplo, en un **expresión** o **asignación de mensajes** forma.</span><span class="sxs-lookup"><span data-stu-id="b2b91-105">In addition to using Call Rules, the rules engine can be programmatically called from expression code, for example, in an **Expression** or **Message Assignment** shape.</span></span> <span data-ttu-id="b2b91-106">Para obtener información acerca de la ejecución de directivas mediante programación, vea [cómo ejecutar directivas](../core/how-to-execute-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b2b91-106">For information about programmatically executing policies, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  
  
 <span data-ttu-id="b2b91-107">En esta sección se detalla información de configuración y los procedimientos requeridos para llamar y ejecutar una directiva empresarial desde una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b2b91-107">This section describes configuration information and the procedures required to call and execute a business policy from a BizTalk orchestration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2b91-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b2b91-108">In This Section</span></span>  
  
-   [<span data-ttu-id="b2b91-109">Información de configuración</span><span class="sxs-lookup"><span data-stu-id="b2b91-109">Configuration Information</span></span>](../core/configuration-information.md)  
  
-   [<span data-ttu-id="b2b91-110">Cómo usar la forma reglas de llamada</span><span class="sxs-lookup"><span data-stu-id="b2b91-110">How to Use the Call Rules Shape</span></span>](../core/how-to-use-the-call-rules-shape.md)