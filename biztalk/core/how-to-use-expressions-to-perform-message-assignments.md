---
title: "Cómo usar expresiones para realizar asignaciones de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, distinquished fields
- orchestrations, expressions
- messages, manipulating
- messages, assigning messages
- messages, expressions
- messages, message parts
- orchestrations, messages
- messages, components
ms.assetid: 9989caf5-012c-4fc4-b5d8-981ca9a69f43
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f423e1b797cfff95bae1d9b1dd862d28210cd26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a>Cómo usar expresiones para realizar asignaciones de mensajes
Puede utilizar expresiones para manipular los mensajes de varias formas en una orquestación.  
  
## <a name="referring-to-message-fields"></a>Hacer referencia a los campos de un mensaje  
 Puede hacer referencia a un campo distintivo de un mensaje si anexa el nombre de campo al nombre de mensaje como se muestra a continuación:  
  
```  
MyMsg.Amount  
```  
  
 En este ejemplo, MyMsg es el mensaje y Amount es un campo identificado como campo distintivo para el tipo de mensaje en el que se basa MyMsg.  
  
## <a name="assigning-to-messages-and-message-parts"></a>Asignar a mensajes y partes de mensaje  
 Puede asignar un mensaje directamente a otro mensaje o una parte de mensaje a una parte de mensaje:  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 En este ejemplo, Invoice es una parte de mensaje basada en un esquema.  
  
 Si desea modificar una propiedad de un mensaje que ya se haya construido, como un mensaje que se ha recibido, debe construir un nuevo mensaje asignando el primero al segundo en una forma construir mensaje y modifique la propiedad en el nuevo mensaje dentro de la misma forma construir mensaje.  
  
> [!NOTE]
>  No puede establecer una referencia o asignación a campos de mensaje, como MyMsg.Invoice.MyField, excepto si están promocionados; solamente puede establecer una referencia o asignación a mensajes completos, partes de mensaje, propiedades de mensaje promocionadas o campos distintivos.  
  
## <a name="adding-message-parts"></a>Agregar partes de mensaje  
 Puede agregar partes adicionales a un mensaje de varias partes existente mediante el **XLANGs.BaseTypes.XLANGMessage.AddPart** método. Para ello, haga lo siguiente:  
  
-   Cree un proyecto de C# y agregue una referencia a **Microsoft.XLANGs.BaseTypes**.  
  
-   Implemente una clase pública similar a la siguiente:  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     Hay tres métodos sobrecargados para **Microsoft.XLANGs.BaseTypes.AddPart**:  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   En el proyecto de BizTalk, agregue una referencia a la clase pública y llamar a la **AddPart** método desde el **expresión** forma en la orquestación del siguiente modo:  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  No puede agregar objetos no serializables u objetos con formato personalizado como partes del mensaje. Todas las partes estáticas deben inicializarse antes de agregar más partes mediante el **AddPart** método. Solo puede agregar partes arbitrarias a un mensaje dentro de la instrucción de construcción de mensajes correspondiente. No se admite la agregación de partes adicionales fuera de la instrucción de construcción de mensajes.  
  
## <a name="retrieving-message-parts"></a>Recuperar partes de mensajes  
 Puede recuperar una parte del mensaje de un mensaje de varias partes existente mediante el **RetrieveAs** método de **Microsoft.XLANGs.BaseTypes**. Para ello, haga lo siguiente:  
  
-   Cree un proyecto de C# y agregue una referencia a **Microsoft.XLANGs.BaseTypes**.  
  
-   Implemente una clase pública similar a la siguiente:  
  
    ```  
    Public class MyAddPartHelper  
    {  
         public static Object GetPart(XLANGMessage msg, string sName, Type t)  
         {  
              XLANGPart p =  msg[sName];  
              return p.RetrieveAs(t);  
         }  
         public static Object GetPart(XLANGMessage msg, int partIndex, Type t)  
         {  
               XLANGPart p = msg[partIndex];  
               return p.RetrieveAs(t);  
          }  
    }  
    ```  
  
    > [!NOTE]
    >  El **RetrieveAs** método es compatible con las partes del mensaje al recuperar por nombre y por índice.  
  
-   En el proyecto de BizTalk, agregue una referencia a la clase pública y llamar a la **GetPart** método desde el **expresión** forma en la orquestación del siguiente modo:  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a>Acceso a la propiedad del contexto de una parte de mensaje  
 Una parte de mensaje tiene un contexto independiente del contexto de mensaje. Puede construir propiedades de contexto de parte de mensaje mediante el editor de esquemas cuando se establece la **Property Schema Base** propiedad para el elemento asociado a **PartContextPropertyBase.**  
  
 El acceso es similar a las propiedades de mensaje a través de una expresión como:  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 Por ejemplo:  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a>Acceso a la propiedad del contexto XLANGMessage  
 Si desea tener acceso a propiedades de mensaje de la **XLANGMessage** interfaz desde el código, puede pasar el mensaje como un parámetro de tipo **Microsoft.XLANGs.BaseTypes.XLANGMessage** a un método desde una forma expresión y, a continuación, utilice la **Microsoft.XLANGs.BaseTypes.XLANGMessage** métodos **SetPropertyValue** y **GetPropertyValue** para lograr Este. Para ello, haga lo siguiente:  
  
-   Cree un proyecto de C# y agregue una referencia a **Microsoft.XLANGs.BaseTypes** y **Microsoft.BizTalk.GlobalPropertySchemas**.  
  
-   Obtenga acceso a la propiedad de contexto mediante un código parecido al siguiente:  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  Si desea obtener o establecer sus propias propiedades de contexto personalizadas, es necesario que agregue una referencia al proyecto de esquemas de propiedades o una referencia al ensamblado que contiene los esquemas de propiedades en el proyecto de C#.  
  
## <a name="assigning-to-message-properties"></a>Asignar a propiedades de mensaje  
 Puede asignar un valor a una propiedad de mensaje:  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede hacer referencia a y asignar valores a las propiedades MIME de un mensaje de varias partes:  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  Un mensaje de BizTalk está formado por el contexto del mensaje y las partes del mensaje. Antes de poder obtener o establecer cualquier propiedad de contexto del mensaje, debe inicializar las partes del mensaje; de lo contrario, recibirá un error durante el tiempo de compilación de XLANG.  
  
## <a name="see-also"></a>Vea también  
 [Usar mensajes en orquestaciones](../core/using-messages-in-orchestrations.md)   
 [Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md)   