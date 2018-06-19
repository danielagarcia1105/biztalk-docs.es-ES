---
title: Cómo usar expresiones para realizar asignaciones de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f423e1b797cfff95bae1d9b1dd862d28210cd26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256748"
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a><span data-ttu-id="126fb-102">Cómo usar expresiones para realizar asignaciones de mensajes</span><span class="sxs-lookup"><span data-stu-id="126fb-102">How to Use Expressions to Perform Message Assignments</span></span>
<span data-ttu-id="126fb-103">Puede utilizar expresiones para manipular los mensajes de varias formas en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="126fb-103">You can use expressions to manipulate messages in various ways in your orchestration.</span></span>  
  
## <a name="referring-to-message-fields"></a><span data-ttu-id="126fb-104">Hacer referencia a los campos de un mensaje</span><span class="sxs-lookup"><span data-stu-id="126fb-104">Referring to message fields</span></span>  
 <span data-ttu-id="126fb-105">Puede hacer referencia a un campo distintivo de un mensaje si anexa el nombre de campo al nombre de mensaje como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="126fb-105">You can refer to a distinguished field in a message by appending the field name to the message name as follows:</span></span>  
  
```  
MyMsg.Amount  
```  
  
 <span data-ttu-id="126fb-106">En este ejemplo, MyMsg es el mensaje y Amount es un campo identificado como campo distintivo para el tipo de mensaje en el que se basa MyMsg.</span><span class="sxs-lookup"><span data-stu-id="126fb-106">In this example, MyMsg is the message, and Amount is a field that has been identified as a distinguished field for the message type that MyMsg is based on.</span></span>  
  
## <a name="assigning-to-messages-and-message-parts"></a><span data-ttu-id="126fb-107">Asignar a mensajes y partes de mensaje</span><span class="sxs-lookup"><span data-stu-id="126fb-107">Assigning to messages and message parts</span></span>  
 <span data-ttu-id="126fb-108">Puede asignar un mensaje directamente a otro mensaje o una parte de mensaje a una parte de mensaje:</span><span class="sxs-lookup"><span data-stu-id="126fb-108">You can assign a message directly to another message, or a message part to a message part:</span></span>  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 <span data-ttu-id="126fb-109">En este ejemplo, Invoice es una parte de mensaje basada en un esquema.</span><span class="sxs-lookup"><span data-stu-id="126fb-109">In this example, Invoice is a message part based on a schema.</span></span>  
  
 <span data-ttu-id="126fb-110">Si desea modificar una propiedad de un mensaje que ya se haya construido, como un mensaje que se ha recibido, debe construir un nuevo mensaje asignando el primero al segundo en una forma construir mensaje y modifique la propiedad en el nuevo mensaje dentro de la misma forma construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="126fb-110">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message by assigning the first to the second in a Construct Message shape, and modify the property on the new message within the same Construct Message shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="126fb-111">No puede establecer una referencia o asignación a campos de mensaje, como MyMsg.Invoice.MyField, excepto si están promocionados; solamente puede establecer una referencia o asignación a mensajes completos, partes de mensaje, propiedades de mensaje promocionadas o campos distintivos.</span><span class="sxs-lookup"><span data-stu-id="126fb-111">You cannot refer or assign to message fields, such as MyMsg.Invoice.MyField, unless they have been promoted; you can only refer or assign to entire messages, message parts, promoted message properties, or distinguished fields.</span></span>  
  
## <a name="adding-message-parts"></a><span data-ttu-id="126fb-112">Agregar partes de mensaje</span><span class="sxs-lookup"><span data-stu-id="126fb-112">Adding message parts</span></span>  
 <span data-ttu-id="126fb-113">Puede agregar partes adicionales a un mensaje de varias partes existente mediante el **XLANGs.BaseTypes.XLANGMessage.AddPart** método.</span><span class="sxs-lookup"><span data-stu-id="126fb-113">You can add additional parts to an existing multipart message by using the **XLANGs.BaseTypes.XLANGMessage.AddPart** method.</span></span> <span data-ttu-id="126fb-114">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="126fb-114">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="126fb-115">Cree un proyecto de C# y agregue una referencia a **Microsoft.XLANGs.BaseTypes**.</span><span class="sxs-lookup"><span data-stu-id="126fb-115">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="126fb-116">Implemente una clase pública similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="126fb-116">Implement a public class similar to the following:</span></span>  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     <span data-ttu-id="126fb-117">Hay tres métodos sobrecargados para **Microsoft.XLANGs.BaseTypes.AddPart**:</span><span class="sxs-lookup"><span data-stu-id="126fb-117">There are three overloaded methods for **Microsoft.XLANGs.BaseTypes.AddPart**:</span></span>  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   <span data-ttu-id="126fb-118">En el proyecto de BizTalk, agregue una referencia a la clase pública y llamar a la **AddPart** método desde el **expresión** forma en la orquestación del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="126fb-118">In your BizTalk project, add a reference to the public class and call the **AddPart** method from the **Expression** shape in your orchestration as follows:</span></span>  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="126fb-119">No puede agregar objetos no serializables u objetos con formato personalizado como partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="126fb-119">You cannot add non-serializable objects or custom formatted objects as message parts.</span></span> <span data-ttu-id="126fb-120">Todas las partes estáticas deben inicializarse antes de agregar más partes mediante el **AddPart** método.</span><span class="sxs-lookup"><span data-stu-id="126fb-120">All static parts must be initialized before adding additional parts using the **AddPart** method.</span></span> <span data-ttu-id="126fb-121">Solo puede agregar partes arbitrarias a un mensaje dentro de la instrucción de construcción de mensajes correspondiente.</span><span class="sxs-lookup"><span data-stu-id="126fb-121">You can add arbitrary parts to a message only inside its message construct statement.</span></span> <span data-ttu-id="126fb-122">No se admite la agregación de partes adicionales fuera de la instrucción de construcción de mensajes.</span><span class="sxs-lookup"><span data-stu-id="126fb-122">Adding additional parts outside of the message construct statement is not supported.</span></span>  
  
## <a name="retrieving-message-parts"></a><span data-ttu-id="126fb-123">Recuperar partes de mensajes</span><span class="sxs-lookup"><span data-stu-id="126fb-123">Retrieving message parts</span></span>  
 <span data-ttu-id="126fb-124">Puede recuperar una parte del mensaje de un mensaje de varias partes existente mediante el **RetrieveAs** método de **Microsoft.XLANGs.BaseTypes**.</span><span class="sxs-lookup"><span data-stu-id="126fb-124">You can retrieve a message part from an existing multipart message by using the **RetrieveAs** method from **Microsoft.XLANGs.BaseTypes**.</span></span> <span data-ttu-id="126fb-125">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="126fb-125">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="126fb-126">Cree un proyecto de C# y agregue una referencia a **Microsoft.XLANGs.BaseTypes**.</span><span class="sxs-lookup"><span data-stu-id="126fb-126">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="126fb-127">Implemente una clase pública similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="126fb-127">Implement a public class similar to the following:</span></span>  
  
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
    >  <span data-ttu-id="126fb-128">El **RetrieveAs** método es compatible con las partes del mensaje al recuperar por nombre y por índice.</span><span class="sxs-lookup"><span data-stu-id="126fb-128">The **RetrieveAs** method supports retrieving message parts by name and by index.</span></span>  
  
-   <span data-ttu-id="126fb-129">En el proyecto de BizTalk, agregue una referencia a la clase pública y llamar a la **GetPart** método desde el **expresión** forma en la orquestación del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="126fb-129">In your BizTalk project, add a reference to the public class and call the **GetPart** method from the **Expression** shape in your orchestration as follows:</span></span>  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a><span data-ttu-id="126fb-130">Acceso a la propiedad del contexto de una parte de mensaje</span><span class="sxs-lookup"><span data-stu-id="126fb-130">Message part context property access</span></span>  
 <span data-ttu-id="126fb-131">Una parte de mensaje tiene un contexto independiente del contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="126fb-131">A message part has context separate from the message context.</span></span> <span data-ttu-id="126fb-132">Puede construir propiedades de contexto de parte de mensaje mediante el editor de esquemas cuando se establece la **Property Schema Base** propiedad para el elemento asociado a **PartContextPropertyBase.**</span><span class="sxs-lookup"><span data-stu-id="126fb-132">You can construct message part context properties through the schema editor when you set the **Property Schema Base** property for the associated element to **PartContextPropertyBase.**</span></span>  
  
 <span data-ttu-id="126fb-133">El acceso es similar a las propiedades de mensaje a través de una expresión como:</span><span class="sxs-lookup"><span data-stu-id="126fb-133">The access is similar to message properties, through an expression like:</span></span>  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 <span data-ttu-id="126fb-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="126fb-134">For example:</span></span>  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a><span data-ttu-id="126fb-135">Acceso a la propiedad del contexto XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="126fb-135">XLANGMessage context property access</span></span>  
 <span data-ttu-id="126fb-136">Si desea tener acceso a propiedades de mensaje de la **XLANGMessage** interfaz desde el código, puede pasar el mensaje como un parámetro de tipo **Microsoft.XLANGs.BaseTypes.XLANGMessage** a un método desde una forma expresión y, a continuación, utilice la **Microsoft.XLANGs.BaseTypes.XLANGMessage** métodos **SetPropertyValue** y **GetPropertyValue** para lograr Este.</span><span class="sxs-lookup"><span data-stu-id="126fb-136">If you would like to access message properties from the **XLANGMessage** interface from your code, you can pass the message as a parameter of type **Microsoft.XLANGs.BaseTypes.XLANGMessage** to a method from an Expression shape, and then use the **Microsoft.XLANGs.BaseTypes.XLANGMessage** methods **SetPropertyValue** and **GetPropertyValue** to achieve this.</span></span> <span data-ttu-id="126fb-137">Para ello, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="126fb-137">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="126fb-138">Cree un proyecto de C# y agregue una referencia a **Microsoft.XLANGs.BaseTypes** y **Microsoft.BizTalk.GlobalPropertySchemas**.</span><span class="sxs-lookup"><span data-stu-id="126fb-138">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes** and **Microsoft.BizTalk.GlobalPropertySchemas**.</span></span>  
  
-   <span data-ttu-id="126fb-139">Obtenga acceso a la propiedad de contexto mediante un código parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="126fb-139">Access the context property using the code similar to the below:</span></span>  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="126fb-140">Si desea obtener o establecer sus propias propiedades de contexto personalizadas, es necesario que agregue una referencia al proyecto de esquemas de propiedades o una referencia al ensamblado que contiene los esquemas de propiedades en el proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="126fb-140">If you would like to get or set your own custom context properties, you need to add a reference to your property schema project or add a reference to the assembly contains the property schemas in your C# project.</span></span>  
  
## <a name="assigning-to-message-properties"></a><span data-ttu-id="126fb-141">Asignar a propiedades de mensaje</span><span class="sxs-lookup"><span data-stu-id="126fb-141">Assigning to message properties</span></span>  
 <span data-ttu-id="126fb-142">Puede asignar un valor a una propiedad de mensaje:</span><span class="sxs-lookup"><span data-stu-id="126fb-142">You can assign a value to a message property:</span></span>  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 <span data-ttu-id="126fb-143">En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede hacer referencia a y asignar valores a las propiedades MIME de un mensaje de varias partes:</span><span class="sxs-lookup"><span data-stu-id="126fb-143">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you can refer to and assign values to the MIME properties of a multi-part message:</span></span>  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  <span data-ttu-id="126fb-144">Un mensaje de BizTalk está formado por el contexto del mensaje y las partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="126fb-144">A BizTalk message consists of message context and message parts.</span></span> <span data-ttu-id="126fb-145">Antes de poder obtener o establecer cualquier propiedad de contexto del mensaje, debe inicializar las partes del mensaje; de lo contrario, recibirá un error durante el tiempo de compilación de XLANG.</span><span class="sxs-lookup"><span data-stu-id="126fb-145">You must first initialize the message parts before you can get or set any message context property; otherwise, you will receive error during the XLANG compile time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="126fb-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="126fb-146">See Also</span></span>  
 <span data-ttu-id="126fb-147">[Usar mensajes en orquestaciones](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="126fb-147">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="126fb-148">Construir mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="126fb-148">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)   