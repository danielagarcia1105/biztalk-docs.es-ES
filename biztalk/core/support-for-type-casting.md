---
title: Compatibilidad con conversión de tipos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6af46e34-5e33-4f61-8c19-4348f1bb4d4a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e863221a556343ee7dc39825199dd8236408977
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279508"
---
# <a name="support-for-type-casting"></a><span data-ttu-id="26b64-102">Compatibilidad con conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="26b64-102">Support for Type Casting</span></span>
<span data-ttu-id="26b64-103">Puede usar el **conversión** método de la **ClassMemberBinding** clase para convertir un objeto de un tipo a un objeto de otro tipo compatible.</span><span class="sxs-lookup"><span data-stu-id="26b64-103">You can use the **Cast** method of the **ClassMemberBinding** class to convert an object of one type to an object of another compatible type.</span></span> <span data-ttu-id="26b64-104">Actualmente, la herramienta de Compositor de reglas de negocio no admite crear reglas mediante el **conversión** método.</span><span class="sxs-lookup"><span data-stu-id="26b64-104">Currently, the Business Rule Composer tool does not support creating rules by using the **Cast** method.</span></span> <span data-ttu-id="26b64-105">Las reglas deben crearse mediante programación utilizando el modelo de objetos del motor de reglas para aprovechar esta función.</span><span class="sxs-lookup"><span data-stu-id="26b64-105">You must create the rules programmatically by using the rule engine object model to take advantage of this feature.</span></span>  
  
 <span data-ttu-id="26b64-106">El código de ejemplo siguiente muestra cómo utilizar el **conversión** método para convertir una instancia de la **System.Object** clase a una instancia de la **Cls2** clase.</span><span class="sxs-lookup"><span data-stu-id="26b64-106">The following sample code demonstrates how to use the **Cast** method to convert an instance of the **System.Object** class to an instance of the **Cls2** class.</span></span> <span data-ttu-id="26b64-107">Este ejemplo también muestra cómo obtener acceso a un miembro de una clase anidado, como se describe en [acceso a miembros anidados de una clase](../core/accessing-nested-members-of-a-class.md).</span><span class="sxs-lookup"><span data-stu-id="26b64-107">This sample also demonstrates how to access a nested member of a class as described in [Accessing Nested Members of a Class](../core/accessing-nested-members-of-a-class.md).</span></span>  
  
```  
using Microsoft.RuleEngine;  
  
namespace RuleTypeCasting  
{  
    class Cls1  
    {  
        //Note that return type is 'object', not Cls2  
        public object GetCls2Obj()  
        {  
            return new Cls2();  
        }  
    }  
  
    class Cls2  
    {  
        public void Log()  
        {  
            Console.WriteLine("In Cls2.Log method");  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create the condition list IF 1 == 1  
            Equal eq = new Equal(new Constant(1), new Constant(1));  
  
            //Create the action collection  
            ActionCollection ac = new ActionCollection();  
  
            //Create the class binding for the Cls1 class  
            ClassBinding cbCls1 = new ClassBinding(typeof(Cls1));  
  
            //Create the class member binding for the GetCls2Obj method in the Cls1 class  
            ClassMemberBinding cmGetCls2Obj = new ClassMemberBinding("GetCls2Obj", cbCls1);  
  
            //Type casting the return value of GetCls2Obj method (object) to Cls2 type  
            cmGetCls2Obj.Cast(typeof(Cls2));  
  
            //Create the class member binding to the Log method of Cls2 type   
            ClassMemberBinding cmLog = new ClassMemberBinding("Log", cmGetCls2Obj);  
  
            //Create a user function based on cmLog and add it to the action collection  
            UserFunction ufLog = new UserFunction(cmLog);  
            ac.Add(ufLog);  
  
            // Create the rule  
            Rule rl = new Rule("InvokeLogRule", eq, ac);  
  
            // Create the rule set or policy  
            RuleSet rs = new RuleSet("InvokeLogPolicy");  
            rs.Rules.Add(rl);  
  
            //Create the facts  
            Cls1 Cls1Obj = new Cls1();  
  
            //Execute the policy  
            PolicyTester tester = new PolicyTester(rs);  
            tester.Execute(Cls1Obj);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="26b64-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="26b64-108">See Also</span></span>  
 <span data-ttu-id="26b64-109">[Compatibilidad con herencia de clases en el motor de reglas de negocios](../core/support-for-class-inheritance-in-the-business-rule-engine.md) </span><span class="sxs-lookup"><span data-stu-id="26b64-109">[Support for Class Inheritance in the Business Rule Engine](../core/support-for-class-inheritance-in-the-business-rule-engine.md) </span></span>  
 [<span data-ttu-id="26b64-110">Obtener acceso a miembros anidados de una clase</span><span class="sxs-lookup"><span data-stu-id="26b64-110">Accessing Nested Members of a Class</span></span>](../core/accessing-nested-members-of-a-class.md)