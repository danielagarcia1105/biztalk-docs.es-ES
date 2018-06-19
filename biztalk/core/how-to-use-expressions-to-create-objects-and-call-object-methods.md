---
title: Cómo usar expresiones para crear objetos y llamar a métodos de objeto | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56cfa46098569863106485fef204f72b23a4ef5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256612"
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a>Cómo usar expresiones para crear objetos y llamar a métodos de objetos [BTS05]
Posiblemente, necesite usar expresiones para crear objetos o invocar métodos.  
  
## <a name="creating-objects"></a>Crear objetos  
 Para crear una variable que tiene un tipo que es una clase. NET, cree un objeto en el **expresión** forma. Las propiedades de la variable de la clase .NET incluyen un constructor. Si utiliza el constructor predeterminado, bastará con que declare directamente la variable de forma similar a como lo haría con otra variable (como una variable de tipo bool o int).  
  
 Si utiliza un constructor que toma parámetros, use la palabra clave **nueva**, seguido de la clase de objeto y los parámetros entre paréntesis:  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  El **utilizar Constructor predeterminado** propiedad podría no mostrarse para algunos objetos que, de hecho, tienen constructores. En ese caso, se utilizará automáticamente el constructor predeterminado y se generará un error si se intenta usar otro constructor.  
  
## <a name="invoking-methods"></a>Invocar métodos  
 Para invocar un método en un objeto de clase .NET, anexe un punto y el nombre del método a la referencia de objeto y, a continuación, especifique los parámetros entre paréntesis:  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a>Pasar y usar mensajes como parámetros  
 Para pasar un mensaje como un parámetro a una llamada de método en una clase .NET, agregue primero una referencia a Microsoft.XLANGs.BaseTypes.dll en el proyecto que define la clase y, a continuación, use el tipo XLANGMessage en la firma de método.  
  
 Si hace referencia al tipo de mensaje de varias partes, podrá tener acceso a las distintas partes del mensaje mediante el tipo XLANGPart:  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 En la propia llamada, sólo tiene que proporcionar el nombre del mensaje, de forma similar a como lo haría con otro parámetro:  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 También puede pasar una parte de mensaje como tipo XLANGPart.  
  
## <a name="net-member-invocation"></a>Llamada a miembros .NET  
 Puede obtener acceso a miembros públicos, excepto en el caso de acceso directo a miembros de una parte de mensaje. Para tener acceso directo a un miembro de una parte de mensaje, es necesario que se promocione como un campo distintivo.  
  
## <a name="comcom-component-invocation"></a>Invocación del componente COM/COM+  
 XLANGs genera código C#. Todas las variables de XLANGs declaradas por el usuario se generan como variables C#. No hay un comportamiento especial excepto en el caso de las transacciones atómicas. Cuando un componente con servicio (es decir, una instancia de una clase que implementa **System.EnterpriseServices.ServicedComponent**) está declarado en un ámbito atómico, a continuación y sólo entonces XLANGs generar y utilizar una transacción COM + de DTC real.  
  
 Cuando se hace referencia a una variable como valor L (es decir, escrito en) en el ámbito atómico, pero se declara en un ámbito externo, la variable se clona para ser compatible con reversión. Sin embargo, un objeto (como un **XmlDocument**) se pueden modificar dentro de una llamada de función .NET cuando se pasa como un parámetro y, por tanto, XLANGs omitirá que se escribe el objeto y no se revertirá correctamente. La solución en este caso es transferir tales objetos como parámetros ref.  
  
 El resultado es que los componentes deben comportarse como lo hacen en otros programas C#.  
  
## <a name="see-also"></a>Vea también  
 [Acerca de las propiedades de contexto de mensaje de BizTalk](../core/about-biztalk-message-context-properties.md)