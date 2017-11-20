---
title: "Cómo usar la forma expresión | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Expression shapes
- Expression shape [Orchestration Designer]
- Expression shape [Orchestration Designer], configuring
- Expression shape [Orchestration Designer], about Expression shape
ms.assetid: 2d702aa9-b824-4f47-a416-70707ce8ef29
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e263454db9674d5bc86b6b7dae1649003f3d129c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expression-shape"></a><span data-ttu-id="2727f-102">Cómo usar la forma Expresión</span><span class="sxs-lookup"><span data-stu-id="2727f-102">How to Use Expression Shape</span></span>
<span data-ttu-id="2727f-103">El **expresión** forma le permite escribir las expresiones de XLANG/s que desee utilizar en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2727f-103">The **Expression** shape enables you to enter any XLANG/s expression you choose in your orchestration.</span></span> <span data-ttu-id="2727f-104">Por ejemplo, puede hacer una llamada a .NET para ejecutar un programa externo o, sencillamente, cambiar los valores de las variables de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2727f-104">For example, you can make a .NET call to run an external program, or simply manipulate the values of your orchestration variables.</span></span>  
  
 <span data-ttu-id="2727f-105">Mientras el **expresión** forma es bastante flexible, no es recomendable utilizar lógica de orquestación de alto nivel, que preferentemente sería visible en el propio diseño de orquestación.</span><span class="sxs-lookup"><span data-stu-id="2727f-105">While the **Expression** shape is quite flexible, it is not good practice to use it to perform high-level orchestration logic, which preferably would be visible in the orchestration drawing itself.</span></span> <span data-ttu-id="2727f-106">En general, resulta más fácil de entender y mantener las orquestaciones si su **expresión** formas contienen expresiones simples y modulares.</span><span class="sxs-lookup"><span data-stu-id="2727f-106">In general, it is easier to understand and maintain your orchestrations if your **Expression** shapes contain simple and modular expressions.</span></span>  
  
### <a name="to-configure-an-expression-shape"></a><span data-ttu-id="2727f-107">Para configurar una forma Expresión</span><span class="sxs-lookup"><span data-stu-id="2727f-107">To configure an Expression shape</span></span>  
  
1.  <span data-ttu-id="2727f-108">Si el Editor de expresiones de BizTalk no está visible, haga clic en el **expresión** forma y haga clic en **Editar expresión** o, en la ventana Propiedades, haga clic en el botón de puntos suspensivos (**...** ) botón la **expresión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="2727f-108">If BizTalk Expression Editor is not visible, right-click the **Expression** shape and click **Edit Expression** or, in the Properties window, click the Ellipsis (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="2727f-109">En el Editor de expresiones de BizTalk, cree una expresión para asignar valores.</span><span class="sxs-lookup"><span data-stu-id="2727f-109">In BizTalk Expression Editor, create an expression to assign values.</span></span> <span data-ttu-id="2727f-110">Para obtener más información, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="2727f-110">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2727f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2727f-111">See Also</span></span>  
 [<span data-ttu-id="2727f-112">Lenguaje XLANG-s.</span><span class="sxs-lookup"><span data-stu-id="2727f-112">XLANG-s Language</span></span>](../core/xlang-s-language.md)