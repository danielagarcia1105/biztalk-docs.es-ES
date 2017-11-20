---
title: "Cómo usar expresiones para crear objetos y llamar a métodos de objeto | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, parameters
- Expression shape [Orchestration Designer], calling objects
- Expression shape [Orchestration Designer], parameters
- Expression shape [Orchestration Designer], passing messages
- orchestrations, methods
- Expression shape [Orchestration Designer], calling methods
- orchestrations, objects
- Expression shape [Orchestration Designer], warning
- Use Default Constructor property
- .NET member invocation
ms.assetid: b6af67eb-8ba5-4c95-9b63-26ebb6617af0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56cfa46098569863106485fef204f72b23a4ef5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a><span data-ttu-id="2c078-102">Cómo usar expresiones para crear objetos y llamar a métodos de objetos [BTS05]</span><span class="sxs-lookup"><span data-stu-id="2c078-102">How to Use Expressions to Create Objects and Call Object Methods</span></span>
<span data-ttu-id="2c078-103">Posiblemente, necesite usar expresiones para crear objetos o invocar métodos.</span><span class="sxs-lookup"><span data-stu-id="2c078-103">You might need to use expressions to create objects or invoke methods.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="2c078-104">Crear objetos</span><span class="sxs-lookup"><span data-stu-id="2c078-104">Creating objects</span></span>  
 <span data-ttu-id="2c078-105">Para crear una variable que tiene un tipo que es una clase. NET, cree un objeto en el **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="2c078-105">To create a variable that has a type which is a .NET class, you construct an object in the **Expression** shape.</span></span> <span data-ttu-id="2c078-106">Las propiedades de la variable de la clase .NET incluyen un constructor.</span><span class="sxs-lookup"><span data-stu-id="2c078-106">The properties of your .NET class variable include a constructor.</span></span> <span data-ttu-id="2c078-107">Si utiliza el constructor predeterminado, bastará con que declare directamente la variable de forma similar a como lo haría con otra variable (como una variable de tipo bool o int).</span><span class="sxs-lookup"><span data-stu-id="2c078-107">If you use the default constructor, you simply declare the variable directly as you would any other variable, like one of type bool or int.</span></span>  
  
 <span data-ttu-id="2c078-108">Si utiliza un constructor que toma parámetros, use la palabra clave **nueva**, seguido de la clase de objeto y los parámetros entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="2c078-108">If you use a constructor that takes parameters, you use the keyword **new**, followed by the object class and any parameters in parentheses:</span></span>  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  <span data-ttu-id="2c078-109">El **utilizar Constructor predeterminado** propiedad podría no mostrarse para algunos objetos que, de hecho, tienen constructores.</span><span class="sxs-lookup"><span data-stu-id="2c078-109">The **Use Default Constructor** property might not be displayed for some objects that do, in fact, have constructors.</span></span> <span data-ttu-id="2c078-110">En ese caso, se utilizará automáticamente el constructor predeterminado y se generará un error si se intenta usar otro constructor.</span><span class="sxs-lookup"><span data-stu-id="2c078-110">In this case, the default constructor will be used automatically, and an error will be raised if you attempt to use a different constructor.</span></span>  
  
## <a name="invoking-methods"></a><span data-ttu-id="2c078-111">Invocar métodos</span><span class="sxs-lookup"><span data-stu-id="2c078-111">Invoking methods</span></span>  
 <span data-ttu-id="2c078-112">Para invocar un método en un objeto de clase .NET, anexe un punto y el nombre del método a la referencia de objeto y, a continuación, especifique los parámetros entre paréntesis:</span><span class="sxs-lookup"><span data-stu-id="2c078-112">To invoke a method on a .NET class object, you append a period and the name of the method to the object reference, followed by any parameters in parentheses:</span></span>  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a><span data-ttu-id="2c078-113">Pasar y usar mensajes como parámetros</span><span class="sxs-lookup"><span data-stu-id="2c078-113">Passing and using messages as parameters</span></span>  
 <span data-ttu-id="2c078-114">Para pasar un mensaje como un parámetro a una llamada de método en una clase .NET, agregue primero una referencia a Microsoft.XLANGs.BaseTypes.dll en el proyecto que define la clase y, a continuación, use el tipo XLANGMessage en la firma de método.</span><span class="sxs-lookup"><span data-stu-id="2c078-114">To pass a message as a parameter to a method call on a .NET class, you first add a reference to Microsoft.XLANGs.BaseTypes.dll in the project that defines the class, and then use the type XLANGMessage in the method signature.</span></span>  
  
 <span data-ttu-id="2c078-115">Si hace referencia al tipo de mensaje de varias partes, podrá tener acceso a las distintas partes del mensaje mediante el tipo XLANGPart:</span><span class="sxs-lookup"><span data-stu-id="2c078-115">Referencing the multi-part message type enables you to access the various parts of the message by using the type XLANGPart:</span></span>  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 <span data-ttu-id="2c078-116">En la propia llamada, sólo tiene que proporcionar el nombre del mensaje, de forma similar a como lo haría con otro parámetro:</span><span class="sxs-lookup"><span data-stu-id="2c078-116">In the call itself, you simply supply the name of the message as you would any other parameter:</span></span>  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 <span data-ttu-id="2c078-117">También puede pasar una parte de mensaje como tipo XLANGPart.</span><span class="sxs-lookup"><span data-stu-id="2c078-117">You can also pass a message part as type XLANGPart.</span></span>  
  
## <a name="net-member-invocation"></a><span data-ttu-id="2c078-118">Llamada a miembros .NET</span><span class="sxs-lookup"><span data-stu-id="2c078-118">.NET member invocation</span></span>  
 <span data-ttu-id="2c078-119">Puede obtener acceso a miembros públicos, excepto en el caso de acceso directo a miembros de una parte de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2c078-119">You can access public members except in the case of direct access to members of a message part.</span></span> <span data-ttu-id="2c078-120">Para tener acceso directo a un miembro de una parte de mensaje, es necesario que se promocione como un campo distintivo.</span><span class="sxs-lookup"><span data-stu-id="2c078-120">To directly access a member of a message part it must be promoted as a distinguished field.</span></span>  
  
## <a name="comcom-component-invocation"></a><span data-ttu-id="2c078-121">Invocación del componente COM/COM+</span><span class="sxs-lookup"><span data-stu-id="2c078-121">COM/COM+ component invocation</span></span>  
 <span data-ttu-id="2c078-122">XLANGs genera código C#.</span><span class="sxs-lookup"><span data-stu-id="2c078-122">XLANGs generates C# code.</span></span> <span data-ttu-id="2c078-123">Todas las variables de XLANGs declaradas por el usuario se generan como variables C#.</span><span class="sxs-lookup"><span data-stu-id="2c078-123">All user-declared XLANGs variables are generated as C# variables.</span></span> <span data-ttu-id="2c078-124">No hay un comportamiento especial excepto en el caso de las transacciones atómicas.</span><span class="sxs-lookup"><span data-stu-id="2c078-124">There is no special behavior except in the case of atomic transactions.</span></span> <span data-ttu-id="2c078-125">Cuando un componente con servicio (es decir, una instancia de una clase que implementa **System.EnterpriseServices.ServicedComponent**) está declarado en un ámbito atómico, a continuación y sólo entonces XLANGs generar y utilizar una transacción COM + de DTC real.</span><span class="sxs-lookup"><span data-stu-id="2c078-125">When a serviced component (that is, an instance of a class that implements **System.EnterpriseServices.ServicedComponent**) is declared in an atomic scope, then and only then does XLANGs generate and use a real DTC COM+ transaction.</span></span>  
  
 <span data-ttu-id="2c078-126">Cuando se hace referencia a una variable como valor L (es decir, escrito en) en el ámbito atómico, pero se declara en un ámbito externo, la variable se clona para ser compatible con reversión.</span><span class="sxs-lookup"><span data-stu-id="2c078-126">If a variable is referenced as an L-value (that is, it is written to) in the atomic scope, but is declared in an outer scope, the variable is cloned to support rollback.</span></span> <span data-ttu-id="2c078-127">Sin embargo, un objeto (como un **XmlDocument**) se pueden modificar dentro de una llamada de función .NET cuando se pasa como un parámetro y, por tanto, XLANGs omitirá que se escribe el objeto y no se revertirá correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c078-127">However, an object (such as an **XmlDocument**) can be modified inside a .NET function call when passed as an in-parameter, and thus XLANGs will miss that the object is being written to and it will not roll back correctly.</span></span> <span data-ttu-id="2c078-128">La solución en este caso es transferir tales objetos como parámetros ref.</span><span class="sxs-lookup"><span data-stu-id="2c078-128">The workaround in this case is to pass such objects as ref parameters.</span></span>  
  
 <span data-ttu-id="2c078-129">El resultado es que los componentes deben comportarse como lo hacen en otros programas C#.</span><span class="sxs-lookup"><span data-stu-id="2c078-129">The bottom line is that components should behave as they do in other C# programs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c078-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c078-130">See Also</span></span>  
 [<span data-ttu-id="2c078-131">Acerca de las propiedades de contexto de mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2c078-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)