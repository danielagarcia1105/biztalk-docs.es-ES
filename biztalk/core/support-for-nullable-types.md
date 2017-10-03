---
title: Compatibilidad con tipos que aceptan valores null | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5ea191-09d5-47ab-a197-390fbbcf6306
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abd277db970a00e9d7d8f20de65e85c607c2a861
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-nullable-types"></a>Compatibilidad con tipos que aceptan valores NULL
El motor de reglas admite el uso de los tipos que aceptan valores NULL en una regla de negocios. Puede usar tipos que aceptan valores NULL en enlaces de clase .NET, enlaces XML y enlaces de bases de datos. Actualmente, la herramienta Compositor de reglas de negocio no admite el uso de tipos que aceptan valores NULL en una regla de negocios. Puede usar los tipos que aceptan valores NULL a la hora de crear reglas mediante programación.  
  
## <a name="using-nullable-types-in-net-class-bindings"></a>Usar tipos que aceptan valores NULL en enlaces de clase .NET  
 Puede crear un enlace de miembro de clase a una propiedad o a un campo de un tipo que acepta valores NULL. Asimismo, puede crear un enlace de miembro de clase a un método que adopta un parámetro de tipo que acepta valores NULL o devuelve un valor de tipo que acepta valores NULL. El siguiente código de ejemplo muestra cómo obtener acceso a un campo que acepta valores NULL y cómo obtener acceso a un valor devuelto de tipo que acepta valores NULL desde un método en una regla de negocio. Si ejecuta una aplicación de consola con el código siguiente tal cual, verá que el valor de la **prop** campo se establece en 5. Si no se inicializa el **prop** campo en la clase o inicializar como null y ejecute el código, verá que el valor de la **prop** campo se establece en 1.  
  
```  
using Microsoft.RuleEngine;  
namespace UseNullableAsm  
{  
    class Program  
    {  
        public class Class1  
        {  
            public int? prop = 1;  
            private int? prop2 = 4;  
            public int? GetProp2()  
            {  
                return prop2;  
            }  
        }  
  
        static void Main(string[] args)  
        {  
            //Create the class binding for the Class1 class  
            ClassBinding cbCls1 = new ClassBinding(typeof(Class1));  
  
            //Create the class member binding to the GetProp2 method of Cls1 class  
            ClassMemberBinding cmGetProp2 = new ClassMemberBinding("GetProp2", cbCls1);  
  
            //Create the class member binding to the to GET the value of prop  
            ClassMemberBinding cmGetProp = new ClassMemberBinding("prop", cbCls1);  
  
            //Create arguments for the prop1 field, which is prop1 + GetProp2()  
            UserFunction ufGetProp = new UserFunction(cmGetProp);  
            Add addArg = new Add(ufGetProp, new UserFunction(cmGetProp2));  
            ArgumentCollection al1 = new ArgumentCollection();  
            al1.Add(addArg);  
  
            //Set the value of prop to prop1 + cmGetPro2()  
            ClassMemberBinding cmProp = new ClassMemberBinding("prop", cbCls1, al1);  
  
            //Create a userfunction based on cmProp and add to the action collection  
            UserFunction ufProp = new UserFunction(cmProp);  
            ActionCollection ac = new ActionCollection();  
            ac.Add(ufProp);  
  
            //Create the condition list IF prop == 1  
            Equal eq = new Equal(ufGetProp, new Constant(1));  
  
            //Create the rule   
            // If (prop == 1)  
            // Then prop = prop + GetProp2()  
            Rule rl = new Rule("NullableTestRule", eq, ac);  
  
            //Create the condition list IF prop != 1  
            NotEqual neq = new NotEqual(ufGetProp, new Constant(1));  
  
            //Set the value of prop to prop to 1  
            Constant ct = new Constant(1);  
            ArgumentCollection al2 = new ArgumentCollection();  
            al2.Add(ct);  
  
            //Create class member binding to prop field with argument value 1  
            ClassMemberBinding cmSetProp = new ClassMemberBinding("prop", cbCls1, al2);  
  
            //Create a userfunction based on cmSetProp and add to the action collection  
            UserFunction ufSetProp = new UserFunction(cmSetProp);  
            ActionCollection ac2 = new ActionCollection();  
            ac2.Add(ufSetProp);  
  
            //Create the second rule   
            // If (prop != 1)  
            // Then prop = 1  
            Rule rl2 = new Rule("NullableTestRule2", neq, ac2);  
  
            //Create the policy and add both the rules to the policy  
            RuleSet rs = new RuleSet("NulableTestPolicy");  
            rs.Rules.Add(rl);  
            rs.Rules.Add(rl2);  
  
            //Create the .NET object fact  
            Class1 cls1Obj = new Class1();  
  
            //Print the value of the field prop before executing the policy  
            Console.WriteLine("Value of the prop field is " + cls1Obj.prop);  
  
            //Execute the policy  
            PolicyTester pt = new PolicyTester(rs);  
            pt.Execute(cls1Obj);  
  
            //Print the value of the field prop after executing the policy  
            Console.WriteLine("Value of the prop field is " + cls1Obj.prop);  
        }  
    }  
}  
```  
  
## <a name="using-nullable-types-in-database-bindings"></a>Usar tipos que aceptan valores NULL en enlaces de bases de datos  
 Asimismo, puede usar tipos que aceptan valores NULL en enlaces de bases de datos. El siguiente fragmento de ejemplo de código le muestra cómo usar un tipo que acepta valores NULL en enlaces de bases de datos.  
  
```  
DataColumnBinding dcBinding = new DataColumnBinding(“col”, typeof(int?), dbBinding);  
```  
  
 Suponga que tiene una regla con una condición que comprueba el valor de una columna de base de datos para ver si es igual a 3. Si el valor de la columna es null, la expresión se evalúa como false. Esto no provoca una excepción.  
  
## <a name="using-nullable-types-in-xml-bindings"></a>Usar tipos que aceptan valores NULL en enlaces XML  
 Del mismo modo, puede usar tipos que aceptan valores NULL en enlaces XML. El siguiente fragmento de ejemplo de código muestra cómo usar un tipo que acepta valores NULL en enlaces XML.  
  
```  
XMLDocumentFieldBinding xfb1 = new XMLDocumentFieldBinding(typeof(int?),"ID",xdb);  
```