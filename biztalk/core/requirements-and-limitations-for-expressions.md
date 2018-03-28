---
title: Requisitos y limitaciones para las expresiones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Expression Editor, about Expression Editor
- Expression Editor, requirements
- Orchestration Designer, Expression Editor
- Expression Editor, limitations
- Expression Editor
- Expression Editor, Orchestration Designer
ms.assetid: 1e0353d3-c2f3-4c10-86e3-8620e62dd0d5
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd819850f62d47c640753e843325c9851da177b5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="requirements-and-limitations-for-expressions"></a><span data-ttu-id="08581-102">Requisitos y limitaciones para expresiones</span><span class="sxs-lookup"><span data-stu-id="08581-102">Requirements and Limitations for Expressions</span></span>
<span data-ttu-id="08581-103">El Editor de expresiones de BizTalk del Diseñador de orquestaciones es un editor de texto estándar de Visual Studio, lo que significa que ofrece IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="08581-103">BizTalk Expression Editor in Orchestration Designer is a standard Visual Studio text editor, which means it offers IntelliSense.</span></span> <span data-ttu-id="08581-104">El Editor de expresiones de BizTalk se usa para escribir expresiones en formato de texto.</span><span class="sxs-lookup"><span data-stu-id="08581-104">You use BizTalk Expression Editor to enter an expression in textual form.</span></span>  
  
 <span data-ttu-id="08581-105">Use el cuadro de texto para escribir una sola expresión en formato de texto.</span><span class="sxs-lookup"><span data-stu-id="08581-105">Use the text box to enter a single expression in textual form.</span></span> <span data-ttu-id="08581-106">La expresión puede contener varias líneas, pero debe finalizar por un solo punto y coma (;).</span><span class="sxs-lookup"><span data-stu-id="08581-106">The expression can span multiple lines, but must end with single semicolon.</span></span>  
  
 <span data-ttu-id="08581-107">A continuación se muestra una lista de limitaciones para el uso de expresiones en el Editor de expresiones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="08581-107">The following is a list of limitations when using expressions in the BizTalk Expression Editor:</span></span>  
  
-   <span data-ttu-id="08581-108">No se permite la asignación compuesta, como "+=", "-=" o "\*=".</span><span class="sxs-lookup"><span data-stu-id="08581-108">Compound assignment such as "+=", "-=", or "\*=" is not supported.</span></span>  
  
-   <span data-ttu-id="08581-109">No se admite el uso de más de un operador de asignación en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="08581-109">More than one assignment operator in a statement is not supported.</span></span>  
  
-   <span data-ttu-id="08581-110">No se admite la asignación dentro de un predicado “if” o “while”.</span><span class="sxs-lookup"><span data-stu-id="08581-110">Assignment within an “if” or “while” predicate is not supported.</span></span>  
  
-   <span data-ttu-id="08581-111">No se admiten los incrementos ni las reducciones.</span><span class="sxs-lookup"><span data-stu-id="08581-111">Increment and decrement are not supported.</span></span> <span data-ttu-id="08581-112">Por ejemplo, "++" ni "--".</span><span class="sxs-lookup"><span data-stu-id="08581-112">For example, "++" and "--".</span></span>  
  
-   <span data-ttu-id="08581-113">Para las partes de mensajes, se permite el acceso de miembros en los métodos públicos, los tipos anidados, los campos de datos estáticos, las propiedades de .NET de solo lectura cuando se anotan con Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, todos los campos de datos públicos y las propiedades de .NET que no son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="08581-113">For message parts, member access is allowed on public methods, nested types, static data fields, read-only .NET properties when annotated with Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, all public data fields, and non-read-only .NET properties.</span></span>  
  
-   <span data-ttu-id="08581-114">No se admiten los indizadores ni las propiedades de .NET con parámetros.</span><span class="sxs-lookup"><span data-stu-id="08581-114">Indexers or parameterized .NET properties are not supported.</span></span>  
  
-   <span data-ttu-id="08581-115">No se admiten los delegados ni los eventos.</span><span class="sxs-lookup"><span data-stu-id="08581-115">Delegates and events are not supported.</span></span>  
  
-   <span data-ttu-id="08581-116">No se admiten los elementos genéricos.</span><span class="sxs-lookup"><span data-stu-id="08581-116">Generics are not supported.</span></span>  
  
-   <span data-ttu-id="08581-117">No se admite la sintaxis de control de flujo, tal como "foreach", "for", "do-while", "break" y "continue".</span><span class="sxs-lookup"><span data-stu-id="08581-117">Flow control syntax such as "foreach", "for", "do-while", "break", and "continue" are not supported.</span></span>  
  
-   <span data-ttu-id="08581-118">No se admiten las operaciones ternarias.</span><span class="sxs-lookup"><span data-stu-id="08581-118">Ternary operations are not supported.</span></span> <span data-ttu-id="08581-119">Por ejemplo, "?:".</span><span class="sxs-lookup"><span data-stu-id="08581-119">For example, "?:".</span></span>  
  
-   <span data-ttu-id="08581-120">Puede agregar comentarios en la forma Expresión, pero ésta debe contener al menos una instrucción.</span><span class="sxs-lookup"><span data-stu-id="08581-120">You can add comments in the Expression shape, but the Expression shape must contain at least one statement.</span></span>  
  
-   <span data-ttu-id="08581-121">No se admiten las matrices.</span><span class="sxs-lookup"><span data-stu-id="08581-121">Arrays are not supported.</span></span>  
  
-   <span data-ttu-id="08581-122">Cuando la forma Expresión se coloca en una forma Construir mensaje, no se puede realizar ningún flujo de control.</span><span class="sxs-lookup"><span data-stu-id="08581-122">When the Expression shape is placed in a Construct Message shape, you cannot do any control flow.</span></span> <span data-ttu-id="08581-123">Por ejemplo, "if-then-else" ni "while".</span><span class="sxs-lookup"><span data-stu-id="08581-123">For example, "if-then-else" or "while".</span></span>  
  
-   <span data-ttu-id="08581-124">Todas las instrucciones de expresiones válidas deben tener el formato:</span><span class="sxs-lookup"><span data-stu-id="08581-124">All valid expression statements are of the form:</span></span>  
  
    -   <span data-ttu-id="08581-125">Dotted-name = expression;</span><span class="sxs-lookup"><span data-stu-id="08581-125">Dotted-name = expression;</span></span>  
  
    -   <span data-ttu-id="08581-126">Dotted-name = expression;</span><span class="sxs-lookup"><span data-stu-id="08581-126">Dotted-name = expression;</span></span>  
  
 <span data-ttu-id="08581-127">Aunque puede usar el Editor de expresiones de BizTalk para escribir expresiones complejas con facilidad y rapidez, no se puede usar para escribir una cantidad de código arbitraria.</span><span class="sxs-lookup"><span data-stu-id="08581-127">Though you can use BizTalk Expression Editor to enter complex expressions easily and quickly, you cannot use it to enter an arbitrary amount of code.</span></span> <span data-ttu-id="08581-128">El motivo es asegurar que el código de los procesos empresariales se mantenga independiente de su código de implementación.</span><span class="sxs-lookup"><span data-stu-id="08581-128">The reason for this is to keep code for the business process separate from its implementation code.</span></span>