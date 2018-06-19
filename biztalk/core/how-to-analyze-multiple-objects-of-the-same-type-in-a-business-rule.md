---
title: Cómo analizar varios objetos del mismo tipo en una regla de negocios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1e4d2fb01513b1d4d314264ab74b84d3a0223a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248436"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a><span data-ttu-id="66b79-102">Cómo analizar varios objetos del mismo tipo en una regla de negocios</span><span class="sxs-lookup"><span data-stu-id="66b79-102">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>
<span data-ttu-id="66b79-103">En muchos escenarios, la regla empresarial se escribe con respecto a un tipo y se espera que cada instancia del tipo que se impone en el motor se analice independientemente y la regla actúe sobre ella.</span><span class="sxs-lookup"><span data-stu-id="66b79-103">In many scenarios, you will write a business rule against a type and expect each instance of the type that is asserted into the engine to be separately analyzed and acted upon by the rule.</span></span> <span data-ttu-id="66b79-104">Sin embargo, en algunos escenarios, será conveniente analizar varias instancias de un tipo determinado de forma simultánea en una regla.</span><span class="sxs-lookup"><span data-stu-id="66b79-104">In some scenarios, however, you will want to analyze multiple instances of a given type simultaneously in a rule.</span></span>  
  
 <span data-ttu-id="66b79-105">Tomemos, por ejemplo, una regla que use instancias de la **FamilyMember** clase.</span><span class="sxs-lookup"><span data-stu-id="66b79-105">Take for example a rule that uses instances of the **FamilyMember** class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 <span data-ttu-id="66b79-106">La regla identifica una **FamilyMember** instancia que es un **padre** y otra instancia que es un **hijo**.</span><span class="sxs-lookup"><span data-stu-id="66b79-106">The rule identifies a **FamilyMember** instance that is a **Father** and another instance that is a **Son**.</span></span> <span data-ttu-id="66b79-107">Si las instancias están relacionadas por el apellido, el **hijo** instancia se agrega a una colección de elementos secundarios en la instancia del padre.</span><span class="sxs-lookup"><span data-stu-id="66b79-107">If the instances are related by surname, the **Son** instance is added to a collection of children on the Father instance.</span></span> <span data-ttu-id="66b79-108">Si cada **FamilyMember** instancia se analizara independientemente de la regla, la regla nunca se activaría porque en este escenario, el **FamilyMember** sólo tiene una función:**padre** o **hijo**.</span><span class="sxs-lookup"><span data-stu-id="66b79-108">If each **FamilyMember** instance were analyzed separately in the rule, the rule would never fire, because in this scenario, the **FamilyMember** only has one role—**Father** or **Son**.</span></span>  
  
 <span data-ttu-id="66b79-109">Por lo tanto, debe indicar al motor que se deben analizar varias instancias juntas en la regla y necesita una manera de diferenciar la identidad de cada instancia en la regla.</span><span class="sxs-lookup"><span data-stu-id="66b79-109">Therefore, you must indicate to the engine that multiple instances should be analyzed together in the rule, and you need a way to differentiate the identity of each instance in the rule.</span></span> <span data-ttu-id="66b79-110">El **Id. de instancia** propiedad se utiliza para proporcionar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="66b79-110">The **Instance ID** property is used to provide this functionality.</span></span> <span data-ttu-id="66b79-111">Este campo está disponible en la ventana de propiedades cuando se selecciona un hecho en el Explorador de hechos.</span><span class="sxs-lookup"><span data-stu-id="66b79-111">This field is available in the Properties window when a fact is selected in Facts Explorer.</span></span> <span data-ttu-id="66b79-112">Debe cambiar el valor del campo antes de arrastrar un hecho o un miembro a la regla.</span><span class="sxs-lookup"><span data-stu-id="66b79-112">You should change the value of the field prior to dragging a fact or member into a rule.</span></span>  
  
 <span data-ttu-id="66b79-113">Mediante el **Id. de instancia** propiedad, se regenerará la regla.</span><span class="sxs-lookup"><span data-stu-id="66b79-113">Using the **Instance ID** property, the rule would be rebuilt.</span></span> <span data-ttu-id="66b79-114">Para los argumentos de regla que utilicen el **hijo** instancia de **FamilyMember**, **Id. de instancia** campo se cambia el valor predeterminado de 0 a 1.</span><span class="sxs-lookup"><span data-stu-id="66b79-114">For those rule arguments that use the **Son** instance of **FamilyMember**, the **Instance ID** field is changed from the default of 0 to 1.</span></span> <span data-ttu-id="66b79-115">Cuando se cambia el identificador de instancia entre 0 y el hecho o miembro se arrastra en el editor de reglas, el valor de Id. de instancia se mostrará en la regla después de la clase.</span><span class="sxs-lookup"><span data-stu-id="66b79-115">When the Instance ID is changed from 0 and the fact or member is dragged into the rule editor, the value of Instance ID will show up in the rule after the class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 <span data-ttu-id="66b79-116">Ahora, suponga que un **padre** instancia y un **hijo** instancia se imponen en el motor.</span><span class="sxs-lookup"><span data-stu-id="66b79-116">Now, assume that a **Father** instance and a **Son** instance are asserted into the engine.</span></span> <span data-ttu-id="66b79-117">El motor evaluará la regla con respecto a las distintas combinaciones de las instancias.</span><span class="sxs-lookup"><span data-stu-id="66b79-117">The engine will evaluate the rule against the various combinations of the instances.</span></span> <span data-ttu-id="66b79-118">Suponiendo que la **padre** y **hijo** instancia tengan el mismo apellido, el **hijo** instancia se agregarán a la **padre** instancia como diseñado.</span><span class="sxs-lookup"><span data-stu-id="66b79-118">Assuming that the **Father** and **Son** instance have the same surname, the **Son** instance will be added to the **Father** instance as intended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66b79-119">El **Id. de instancia** solo se usa en el contexto de una evaluación determinado de reglas.</span><span class="sxs-lookup"><span data-stu-id="66b79-119">The **Instance ID** is only used within the context of a given rule evaluation.</span></span> <span data-ttu-id="66b79-120">No está fijada a la instancia de un objeto en toda la ejecución de la directiva y no está relacionada con el orden en que se imponen los objetos.</span><span class="sxs-lookup"><span data-stu-id="66b79-120">It is not affixed to an object instance across the policy execution and is not related to the order in which objects are asserted.</span></span> <span data-ttu-id="66b79-121">Cada instancia del objeto se evaluará en todos los argumentos de la regla para ese tipo.</span><span class="sxs-lookup"><span data-stu-id="66b79-121">Each object instance will be evaluated in all rule arguments for that type.</span></span>