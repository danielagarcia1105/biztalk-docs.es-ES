---
title: Requisitos y limitaciones para expresiones | Microsoft Docs
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9b3cbbd426227e21f16d5bde4186823164f1fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999693"
---
# <a name="requirements-and-limitations-for-expressions"></a><span data-ttu-id="06301-102">Requisitos y limitaciones para expresiones</span><span class="sxs-lookup"><span data-stu-id="06301-102">Requirements and Limitations for Expressions</span></span>
<span data-ttu-id="06301-103">El Editor de expresiones de BizTalk del Diseñador de orquestaciones es un editor de texto estándar de Visual Studio, lo que significa que ofrece IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="06301-103">BizTalk Expression Editor in Orchestration Designer is a standard Visual Studio text editor, which means it offers IntelliSense.</span></span> <span data-ttu-id="06301-104">El Editor de expresiones de BizTalk se usa para escribir expresiones en formato de texto.</span><span class="sxs-lookup"><span data-stu-id="06301-104">You use BizTalk Expression Editor to enter an expression in textual form.</span></span>  
  
 <span data-ttu-id="06301-105">Use el cuadro de texto para escribir una sola expresión en formato de texto.</span><span class="sxs-lookup"><span data-stu-id="06301-105">Use the text box to enter a single expression in textual form.</span></span> <span data-ttu-id="06301-106">La expresión puede contener varias líneas, pero debe finalizar por un solo punto y coma (;).</span><span class="sxs-lookup"><span data-stu-id="06301-106">The expression can span multiple lines, but must end with single semicolon.</span></span>  
  
 <span data-ttu-id="06301-107">A continuación se muestra una lista de limitaciones para el uso de expresiones en el Editor de expresiones de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="06301-107">The following is a list of limitations when using expressions in the BizTalk Expression Editor:</span></span>  
  
- <span data-ttu-id="06301-108">No se permite la asignación compuesta, como "+=", "-=" o "\*=".</span><span class="sxs-lookup"><span data-stu-id="06301-108">Compound assignment such as "+=", "-=", or "\*=" is not supported.</span></span>  
  
- <span data-ttu-id="06301-109">No se admite el uso de más de un operador de asignación en una instrucción.</span><span class="sxs-lookup"><span data-stu-id="06301-109">More than one assignment operator in a statement is not supported.</span></span>  
  
- <span data-ttu-id="06301-110">No se admite la asignación dentro de un predicado “if” o “while”.</span><span class="sxs-lookup"><span data-stu-id="06301-110">Assignment within an “if” or “while” predicate is not supported.</span></span>  
  
- <span data-ttu-id="06301-111">No se admiten los incrementos ni las reducciones.</span><span class="sxs-lookup"><span data-stu-id="06301-111">Increment and decrement are not supported.</span></span> <span data-ttu-id="06301-112">Por ejemplo, "++" ni "--".</span><span class="sxs-lookup"><span data-stu-id="06301-112">For example, "++" and "--".</span></span>  
  
- <span data-ttu-id="06301-113">Para las partes de mensajes, se permite el acceso de miembros en los métodos públicos, los tipos anidados, los campos de datos estáticos, las propiedades de .NET de solo lectura cuando se anotan con Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, todos los campos de datos públicos y las propiedades de .NET que no son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="06301-113">For message parts, member access is allowed on public methods, nested types, static data fields, read-only .NET properties when annotated with Microsoft.XLANGs.BaseTypes.DistinguishedFieldAttribute, all public data fields, and non-read-only .NET properties.</span></span>  
  
- <span data-ttu-id="06301-114">No se admiten los indizadores ni las propiedades de .NET con parámetros.</span><span class="sxs-lookup"><span data-stu-id="06301-114">Indexers or parameterized .NET properties are not supported.</span></span>  
  
- <span data-ttu-id="06301-115">No se admiten los delegados ni los eventos.</span><span class="sxs-lookup"><span data-stu-id="06301-115">Delegates and events are not supported.</span></span>  
  
- <span data-ttu-id="06301-116">No se admiten los elementos genéricos.</span><span class="sxs-lookup"><span data-stu-id="06301-116">Generics are not supported.</span></span>  
  
- <span data-ttu-id="06301-117">No se admite la sintaxis de control de flujo, tal como "foreach", "for", "do-while", "break" y "continue".</span><span class="sxs-lookup"><span data-stu-id="06301-117">Flow control syntax such as "foreach", "for", "do-while", "break", and "continue" are not supported.</span></span>  
  
- <span data-ttu-id="06301-118">No se admiten las operaciones ternarias.</span><span class="sxs-lookup"><span data-stu-id="06301-118">Ternary operations are not supported.</span></span> <span data-ttu-id="06301-119">Por ejemplo, "?:".</span><span class="sxs-lookup"><span data-stu-id="06301-119">For example, "?:".</span></span>  
  
- <span data-ttu-id="06301-120">Puede agregar comentarios en la forma Expresión, pero ésta debe contener al menos una instrucción.</span><span class="sxs-lookup"><span data-stu-id="06301-120">You can add comments in the Expression shape, but the Expression shape must contain at least one statement.</span></span>  
  
- <span data-ttu-id="06301-121">No se admiten las matrices.</span><span class="sxs-lookup"><span data-stu-id="06301-121">Arrays are not supported.</span></span>  
  
- <span data-ttu-id="06301-122">Cuando la forma Expresión se coloca en una forma Construir mensaje, no se puede realizar ningún flujo de control.</span><span class="sxs-lookup"><span data-stu-id="06301-122">When the Expression shape is placed in a Construct Message shape, you cannot do any control flow.</span></span> <span data-ttu-id="06301-123">Por ejemplo, "if-then-else" ni "while".</span><span class="sxs-lookup"><span data-stu-id="06301-123">For example, "if-then-else" or "while".</span></span>  
  
- <span data-ttu-id="06301-124">Todas las instrucciones de expresiones válidas deben tener el formato:</span><span class="sxs-lookup"><span data-stu-id="06301-124">All valid expression statements are of the form:</span></span>  
  
  -   <span data-ttu-id="06301-125">Dotted-name = expression;</span><span class="sxs-lookup"><span data-stu-id="06301-125">Dotted-name = expression;</span></span>  
  
  -   <span data-ttu-id="06301-126">Dotted-name = expression;</span><span class="sxs-lookup"><span data-stu-id="06301-126">Dotted-name = expression;</span></span>  
  
  <span data-ttu-id="06301-127">Aunque puede usar el Editor de expresiones de BizTalk para escribir expresiones complejas con facilidad y rapidez, no se puede usar para escribir una cantidad de código arbitraria.</span><span class="sxs-lookup"><span data-stu-id="06301-127">Though you can use BizTalk Expression Editor to enter complex expressions easily and quickly, you cannot use it to enter an arbitrary amount of code.</span></span> <span data-ttu-id="06301-128">El motivo es asegurar que el código de los procesos empresariales se mantenga independiente de su código de implementación.</span><span class="sxs-lookup"><span data-stu-id="06301-128">The reason for this is to keep code for the business process separate from its implementation code.</span></span>