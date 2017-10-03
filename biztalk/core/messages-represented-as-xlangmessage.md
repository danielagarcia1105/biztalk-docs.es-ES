---
title: Mensajes representan como XLANGMessage | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aadca870-2f93-4be3-8733-a0cd3815add7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 996c88ca73fcc8abc450159e1cf26cd24b7aa241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-represented-as-xlangmessage"></a><span data-ttu-id="a8a56-102">Mensajes representados como XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="a8a56-102">Messages Represented as XLANGMessage</span></span>
<span data-ttu-id="a8a56-103">Un **XLANGMessage** objeto representa una instancia de mensaje declarada con un servicio XLANG.</span><span class="sxs-lookup"><span data-stu-id="a8a56-103">An **XLANGMessage** object represents a message instance declared with an XLANG service.</span></span> <span data-ttu-id="a8a56-104">Este objeto se obtiene pasando una referencia a un mensaje como un parámetro en una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="a8a56-104">This object is obtained by passing a reference to a message as a parameter in a method invocation.</span></span> <span data-ttu-id="a8a56-105">Un **XLANGPart** objeto representa una parte de mensaje contenida en una instancia de mensaje dentro de un servicio XLANG.</span><span class="sxs-lookup"><span data-stu-id="a8a56-105">An **XLANGPart** object represents a message part contained in a message instance within an XLANG service.</span></span> <span data-ttu-id="a8a56-106">Este objeto se obtiene bien pasando una referencia de parte de una invocación de método donde es el tipo de parámetro receptora **XLANGPart** o bien recorriendo una referencia pasada de **XLANGMessage**.</span><span class="sxs-lookup"><span data-stu-id="a8a56-106">This object is obtained either by passing a part reference in a method invocation where the receiving parameter type is **XLANGPart** or by enumerating on a passed reference of **XLANGMessage**.</span></span>  
  
 <span data-ttu-id="a8a56-107">Una variable de mensaje de orquestación se puede pasar a un componente de usuario y recibió como un **XLANGMessage** objeto.</span><span class="sxs-lookup"><span data-stu-id="a8a56-107">An orchestration message variable may be passed to a user component and received as an **XLANGMessage** object.</span></span> <span data-ttu-id="a8a56-108">El **XLANGMessage** objeto permite obtener acceso a los elementos y tener acceso a propiedades de mensaje. El usuario puede "mantener" un **XLANGMessage** y, por tanto, extender su duración más allá del ámbito declarado.</span><span class="sxs-lookup"><span data-stu-id="a8a56-108">The **XLANGMessage** object allows accessing the parts and accessing message properties.The user may "hold on" to an **XLANGMessage** and thereby extend its lifetime beyond the declared scope.</span></span> <span data-ttu-id="a8a56-109">Como consecuencia, un **XLANGMessage** posible desde un método y se asigna a una variable de mensaje en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="a8a56-109">Subsequently, an **XLANGMessage** may be retuned from a method and assigned to a message variable in an orchestration.</span></span>  
  
## <a name="constructing-an-xlangmessage"></a><span data-ttu-id="a8a56-110">Construir un XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="a8a56-110">Constructing an XLANGMessage</span></span>  
 <span data-ttu-id="a8a56-111">Al construir un **XLANGMessage** con una secuencia, el tipo de secuencia debe bien implemente **IStreamFactory** o ser un **MemoryStream**.</span><span class="sxs-lookup"><span data-stu-id="a8a56-111">When constructing an **XLANGMessage** with a stream, the stream type must either implement **IStreamFactory** or be a **MemoryStream**.</span></span> <span data-ttu-id="a8a56-112">El ejemplo de código siguiente muestra cómo construir un **XLANGMessage**:</span><span class="sxs-lookup"><span data-stu-id="a8a56-112">The following code sample shows how to construct an **XLANGMessage**:</span></span>  
  
```  
public class FileStreamFactory : IStreamFactory  
{  
    string _fname;  
  
    public FileStreamFactory(string fname)  
    {  
        _fname = fname;  
    }  
  
    public Stream CreateStream()  
    {  
        return new FileStream  
        (  
            _fname,  
            FileMode.Open,  
            FileAccess.Read,  
            FileShare.Read  
        );  
    }  
}  
  
public static void AssignStreamFactoryToPart(XLANGMessage msg)  
{  
    IStreamFactory sf = new FileStreamFactory( @”c:\data.xml” );  
    msg[0].LoadFrom( sf );  
}  
```  
  
 <span data-ttu-id="a8a56-113">Puede que a veces desee crear un nuevo mensaje sin transformar un mensaje de origen.</span><span class="sxs-lookup"><span data-stu-id="a8a56-113">There may be times when you want to create a new message without transforming a source message.</span></span> <span data-ttu-id="a8a56-114">Puede hacerlo mediante el uso de una variable de tipo **System.Xml.XmlDocument** y cargando o construyendo el contenido adecuado.</span><span class="sxs-lookup"><span data-stu-id="a8a56-114">You can do this by using a variable of type **System.Xml.XmlDocument** and loading or otherwise constructing appropriate content.</span></span> <span data-ttu-id="a8a56-115">En el ejemplo siguiente, se carga XML desde una cadena mediante el uso de la **LoadXml** método **XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="a8a56-115">In the following example, XML is loaded from a string by using the **LoadXml** method of **XmlDocument**:</span></span>  
  
```  
XmlVariable.LoadXml("\<ns0:Root PONumber=\"047745351122111\" xmlns:ns0=\"http://BTSHTTPSend.SimpleSchema\">\<MyChildRecord SubAttr1=\"Simple Attribute \" />\</ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 <span data-ttu-id="a8a56-116">En el ejemplo siguiente se carga XML desde un archivo mediante la **carga** método **XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="a8a56-116">The following example loads XML from a file by using the **Load** method of **XmlDocument**:</span></span>  
  
```  
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="a8a56-117">Si desea construir mensajes más grandes, utilice uno de los métodos de transmisión por secuencias que se muestra en la sección anterior o considere el uso de la **transformar** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="a8a56-117">If you want to construct larger messages, use one of the streaming methods demonstrated in the previous section or consider using the **Transform** shape in Orchestration Designer.</span></span>  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a><span data-ttu-id="a8a56-118">Consideraciones al usar XLANGMessage y XLANGPart</span><span class="sxs-lookup"><span data-stu-id="a8a56-118">Considerations When Using XLANGMessage and XLANGPart</span></span>  
 <span data-ttu-id="a8a56-119">Cuando se usa **XLANGMessage** y **XLANGPart** en el código de usuario, considere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8a56-119">When using **XLANGMessage** and **XLANGPart** in user code, consider the following:</span></span>  
  
-   <span data-ttu-id="a8a56-120">No pase una parte del mensaje como una **XLANGPart** un valor de tipo de valor devuelto o argumento **XLANGPart**.</span><span class="sxs-lookup"><span data-stu-id="a8a56-120">Do not pass a message part as an **XLANGPart** argument or return a value of type **XLANGPart**.</span></span> <span data-ttu-id="a8a56-121">Debería pasar **XLANGPart** como el tipo del elemento.</span><span class="sxs-lookup"><span data-stu-id="a8a56-121">You should pass **XLANGPart** as the type of the part.</span></span> <span data-ttu-id="a8a56-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a56-122">For example:</span></span>  
  
    ```  
    Message String msg;  
    Class.Test(msg);  
    // or you can do the following  
    Messagetype mt  
    {  
         String part;  
    };  
    Message mt msg;  
    Class.Test(msg,part);  
  
    ```  
  
     <span data-ttu-id="a8a56-123">También puede pasar el propio mensaje como una **XLANGMessage** y use la **XLANGMessage** operadores de subíndice para tener acceso a la parte dentro de la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="a8a56-123">You can also pass the message itself as an **XLANGMessage** and use the **XLANGMessage** subscript operators to access the part inside the function call.</span></span> <span data-ttu-id="a8a56-124">Sin embargo, no debería colocar un **XLANGPart** en una colección cuya duración se extiende más allá de la duración de la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="a8a56-124">However, you should not put an **XLANGPart** in a collection whose lifetime extends past the lifetime of the function call.</span></span> <span data-ttu-id="a8a56-125">En su lugar, debe colocar la **XLANGMessage** en la colección.</span><span class="sxs-lookup"><span data-stu-id="a8a56-125">Instead, you should put the **XLANGMessage** in the collection.</span></span> <span data-ttu-id="a8a56-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a56-126">For example:</span></span>  
  
    ```  
    Void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          XLANGPart xlp = xlm[0];  
          String sval = (String) xlp.RetrieveAs(typeof(string));  
         }  
         finally  
         {  
          Xlm.Dispose();  
         }  
    }  
    ```  
  
-   <span data-ttu-id="a8a56-127">No se define un parámetro de orquestación como **XLANGMessage** o **XLANGPart**.</span><span class="sxs-lookup"><span data-stu-id="a8a56-127">Do not define an orchestration parameter as **XLANGMessage** or **XLANGPart**.</span></span> <span data-ttu-id="a8a56-128">Si quiere pasar un mensaje, use un parámetro de tipo mensaje para ello.</span><span class="sxs-lookup"><span data-stu-id="a8a56-128">If you want to pass a message, then use a message type parameter to pass the message.</span></span> <span data-ttu-id="a8a56-129">Si quiere pasar una parte, pase el mensaje en su lugar y, a continuación, use la parte.</span><span class="sxs-lookup"><span data-stu-id="a8a56-129">If you want to pass a part, then pass the message instead and then use the part.</span></span> <span data-ttu-id="a8a56-130">Si solo quiere el valor de la parte, use el tipo de parte para pasarla.</span><span class="sxs-lookup"><span data-stu-id="a8a56-130">If you only want the part value, then use the part type to pass the part.</span></span>  
  
-   <span data-ttu-id="a8a56-131">No devuelven un **XLANGMessage** parámetro para una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="a8a56-131">Do not return an **XLANGMessage** parameter for a method call.</span></span> <span data-ttu-id="a8a56-132">Si devuelve un **XLANGMessage** parámetro que se pasa en y, a continuación, no puede llamar a la **Dispose** método en el parámetro dentro de la llamada al método, se infringen intuitivamente la duración supuesta y también produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="a8a56-132">If you return an **XLANGMessage** parameter that is passed in, and then you cannot call the **Dispose** method on the parameter inside the method call, it intuitively violates lifetime assumptions and it also throws an exception.</span></span> <span data-ttu-id="a8a56-133">Al pasar un mensaje a través de un **XLANGMessage** parámetro al código de usuario, hace que el mensaje a un contexto especial que normalmente no tienen mensajes que hagan referencia a él.</span><span class="sxs-lookup"><span data-stu-id="a8a56-133">When passing a message through an **XLANGMessage** parameter to user code, you reference the message to a special context that does not normally have messages referenced to it.</span></span> <span data-ttu-id="a8a56-134">La duración de este contexto es la duración de la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="a8a56-134">The lifetime of this context is the lifetime of the orchestration instance.</span></span> <span data-ttu-id="a8a56-135">Esto se debe a que BizTalk Server desconoce si el código de usuario se mantendrá en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a8a56-135">This is because BizTalk Server does not know whether the user code will hold onto the message.</span></span>  
  
     <span data-ttu-id="a8a56-136">Cuando se cierra una instancia de orquestación, cualquier mensaje creado en esa instancia ya no es válido; por tanto, la duración de tal colección debe ser menor o igual que la duración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="a8a56-136">When an orchestration instance exits, any messages created in that instance are no longer valid, so the lifetime of such a collection should be less than or equal to that of the instance lifetime.</span></span> <span data-ttu-id="a8a56-137">Sin embargo, si desea liberar una referencia de mensaje en un bucle cuando se pasa el mensaje a través de un **XLANGMessage** argumento que tiene la misma duración que la instancia de orquestación, a continuación, puede llamar a  **XLANGMessage.Dispose** para liberar la referencia.</span><span class="sxs-lookup"><span data-stu-id="a8a56-137">However, if you want to release a message reference in a loop when the message was passed through an **XLANGMessage** argument that has the same lifetime as the orchestration instance, then you can call **XLANGMessage.Dispose** to free up the reference.</span></span> <span data-ttu-id="a8a56-138">Además, si se encuentra dentro del método de código de usuario, el **XLANGMessage** parámetro solo se utiliza localmente y la duración del parámetro está contenida en la de la llamada de función, también puede llamar a **XLANGMessage.Dispose**para liberar la referencia al contexto raíz y devolver el mensaje correspondiente el comportamiento de duración normal.</span><span class="sxs-lookup"><span data-stu-id="a8a56-138">Moreover, if inside the user code method, the **XLANGMessage** parameter is only used locally and the lifetime of the parameter is contained in that of the function call, you can also call **XLANGMessage.Dispose** to free up the reference to the root context and give the corresponding message back the normal lifetime behavior.</span></span> <span data-ttu-id="a8a56-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a56-139">For example:</span></span>  
  
    ```  
    void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          //XLANGMessage is only used locally  
         }  
         finally  
         {  
          xlm.Dispose();  
         }  
    }  
    ```  
  
     <span data-ttu-id="a8a56-140">Si coloca el XML en una colección, la propia clase debe tener un **Dispose** método de limpieza.</span><span class="sxs-lookup"><span data-stu-id="a8a56-140">If you place the xlm in a collection, then the class itself must have a **Dispose** method for cleanup.</span></span> <span data-ttu-id="a8a56-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a8a56-141">For example:</span></span>  
  
    ```  
    Public class A  
    {  
         Hashtable h = new Hashtable();  
         Public Test(XLANGMessage xlm)  
         {  
          h[xlm] = 1;  
         }  
         //You can have more methods here  
         Public Dispose()  
         {  
          foreach (XLANGMessage xlm in h.Keys)  
           Xlm.Dispose();  
         }  
    }  
    ```  
  
     <span data-ttu-id="a8a56-142">Debería llamar a **A.Dispose** cuando haya terminado con la colección de **XLANGMessages**.</span><span class="sxs-lookup"><span data-stu-id="a8a56-142">You would call **A.Dispose** when you are finished with the collection of **XLANGMessages**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a56-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8a56-143">See Also</span></span>  
 <span data-ttu-id="a8a56-144">[Mensajes representados como esquemas XSD](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a8a56-144">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="a8a56-145">[Mensajes representados como clases .NET](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="a8a56-145">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 [<span data-ttu-id="a8a56-146">Construir mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="a8a56-146">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)