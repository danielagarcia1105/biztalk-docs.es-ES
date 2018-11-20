---
title: Mensajes representan como XLANGMessage | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aadca870-2f93-4be3-8733-a0cd3815add7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62c5b4b192602896d0cfe301834844b4b7cab12b
ms.sourcegitcommit: c3070a7a3f332857357f056dc632829b43869c17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2018
ms.locfileid: "51630329"
---
# <a name="messages-represented-as-xlangmessage"></a><span data-ttu-id="093ed-102">Mensajes representados como XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="093ed-102">Messages Represented as XLANGMessage</span></span>
<span data-ttu-id="093ed-103">Un **XLANGMessage** objeto representa una instancia de mensaje declarada con un servicio XLANG.</span><span class="sxs-lookup"><span data-stu-id="093ed-103">An **XLANGMessage** object represents a message instance declared with an XLANG service.</span></span> <span data-ttu-id="093ed-104">Este objeto se obtiene pasando una referencia a un mensaje como un parámetro en una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="093ed-104">This object is obtained by passing a reference to a message as a parameter in a method invocation.</span></span> <span data-ttu-id="093ed-105">Un **XLANGPart** objeto representa una parte de mensaje contenida en una instancia de mensaje dentro de un servicio XLANG.</span><span class="sxs-lookup"><span data-stu-id="093ed-105">An **XLANGPart** object represents a message part contained in a message instance within an XLANG service.</span></span> <span data-ttu-id="093ed-106">Este objeto se obtiene pasando una referencia de los elementos en una invocación del método donde es el tipo de parámetro receptora **XLANGPart** o bien recorriendo una referencia del pasado **XLANGMessage**.</span><span class="sxs-lookup"><span data-stu-id="093ed-106">This object is obtained either by passing a part reference in a method invocation where the receiving parameter type is **XLANGPart** or by enumerating on a passed reference of **XLANGMessage**.</span></span>  
  
 <span data-ttu-id="093ed-107">Una variable de mensaje de orquestación se puede pasar a un componente de usuario y recibió como un **XLANGMessage** objeto.</span><span class="sxs-lookup"><span data-stu-id="093ed-107">An orchestration message variable may be passed to a user component and received as an **XLANGMessage** object.</span></span> <span data-ttu-id="093ed-108">El **XLANGMessage** objeto permite obtener acceso a las partes y acceso a las propiedades de mensaje. El usuario puede "mantener" un **XLANGMessage** y con ello ampliar su duración más allá del ámbito declarado.</span><span class="sxs-lookup"><span data-stu-id="093ed-108">The **XLANGMessage** object allows accessing the parts and accessing message properties.The user may "hold on" to an **XLANGMessage** and thereby extend its lifetime beyond the declared scope.</span></span> <span data-ttu-id="093ed-109">Posteriormente, una **XLANGMessage** puede devuelto desde un método y se asigna a una variable de mensaje en una orquestación.</span><span class="sxs-lookup"><span data-stu-id="093ed-109">Subsequently, an **XLANGMessage** may be returned from a method and assigned to a message variable in an orchestration.</span></span>  
  
## <a name="constructing-an-xlangmessage"></a><span data-ttu-id="093ed-110">Construir un XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="093ed-110">Constructing an XLANGMessage</span></span>  
 <span data-ttu-id="093ed-111">Al construir un **XLANGMessage** con una secuencia, el tipo de secuencia debe implementar **IStreamFactory** o ser un **MemoryStream**.</span><span class="sxs-lookup"><span data-stu-id="093ed-111">When constructing an **XLANGMessage** with a stream, the stream type must either implement **IStreamFactory** or be a **MemoryStream**.</span></span> <span data-ttu-id="093ed-112">Ejemplo de código siguiente muestra cómo construir un **XLANGMessage**:</span><span class="sxs-lookup"><span data-stu-id="093ed-112">The following code sample shows how to construct an **XLANGMessage**:</span></span>  
  
```csharp
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
  
 <span data-ttu-id="093ed-113">Puede que a veces desee crear un nuevo mensaje sin transformar un mensaje de origen.</span><span class="sxs-lookup"><span data-stu-id="093ed-113">There may be times when you want to create a new message without transforming a source message.</span></span> <span data-ttu-id="093ed-114">Puede hacerlo mediante el uso de una variable de tipo **System.Xml.XmlDocument** y cargando o construyendo el contenido adecuado.</span><span class="sxs-lookup"><span data-stu-id="093ed-114">You can do this by using a variable of type **System.Xml.XmlDocument** and loading or otherwise constructing appropriate content.</span></span> <span data-ttu-id="093ed-115">En el ejemplo siguiente, se carga XML desde una cadena mediante el uso de la **LoadXml** método **XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="093ed-115">In the following example, XML is loaded from a string by using the **LoadXml** method of **XmlDocument**:</span></span>  
  
```csharp
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 <span data-ttu-id="093ed-116">En el ejemplo siguiente se carga XML desde un archivo mediante el uso de la **carga** método **XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="093ed-116">The following example loads XML from a file by using the **Load** method of **XmlDocument**:</span></span>  
  
```csharp
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="093ed-117">Si desea construir mensajes más grandes, use uno de los métodos de transmisión por secuencias se muestra en la sección anterior o considere el uso de la **transformar** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="093ed-117">If you want to construct larger messages, use one of the streaming methods demonstrated in the previous section or consider using the **Transform** shape in Orchestration Designer.</span></span>  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a><span data-ttu-id="093ed-118">Consideraciones al usar XLANGMessage y XLANGPart</span><span class="sxs-lookup"><span data-stu-id="093ed-118">Considerations When Using XLANGMessage and XLANGPart</span></span>  
 <span data-ttu-id="093ed-119">Cuando se usa **XLANGMessage** y **XLANGPart** en código de usuario, considere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="093ed-119">When using **XLANGMessage** and **XLANGPart** in user code, consider the following:</span></span>  
  
-   <span data-ttu-id="093ed-120">No pase una parte de mensaje como un **XLANGPart** un valor de tipo de valor devuelto o argumento **XLANGPart**.</span><span class="sxs-lookup"><span data-stu-id="093ed-120">Do not pass a message part as an **XLANGPart** argument or return a value of type **XLANGPart**.</span></span> <span data-ttu-id="093ed-121">Debería pasar **XLANGPart** como el tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="093ed-121">You should pass **XLANGPart** as the type of the part.</span></span> <span data-ttu-id="093ed-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="093ed-122">For example:</span></span>  
  
    ```csharp
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
  
     <span data-ttu-id="093ed-123">También puede pasar el propio mensaje como un **XLANGMessage** y usar el **XLANGMessage** operadores de subíndice para tener acceso a la parte dentro de la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="093ed-123">You can also pass the message itself as an **XLANGMessage** and use the **XLANGMessage** subscript operators to access the part inside the function call.</span></span> <span data-ttu-id="093ed-124">Sin embargo, no debería colocar una **XLANGPart** en una colección cuya duración se extiende más allá de la duración de la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="093ed-124">However, you should not put an **XLANGPart** in a collection whose lifetime extends past the lifetime of the function call.</span></span> <span data-ttu-id="093ed-125">En su lugar, debe colocar el **XLANGMessage** en la colección.</span><span class="sxs-lookup"><span data-stu-id="093ed-125">Instead, you should put the **XLANGMessage** in the collection.</span></span> <span data-ttu-id="093ed-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="093ed-126">For example:</span></span>  
  
    ```csharp
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
  
-   <span data-ttu-id="093ed-127">No defina un parámetro de orquestación como **XLANGMessage** o **XLANGPart**.</span><span class="sxs-lookup"><span data-stu-id="093ed-127">Do not define an orchestration parameter as **XLANGMessage** or **XLANGPart**.</span></span> <span data-ttu-id="093ed-128">Si quiere pasar un mensaje, use un parámetro de tipo mensaje para ello.</span><span class="sxs-lookup"><span data-stu-id="093ed-128">If you want to pass a message, then use a message type parameter to pass the message.</span></span> <span data-ttu-id="093ed-129">Si quiere pasar una parte, pase el mensaje en su lugar y, a continuación, use la parte.</span><span class="sxs-lookup"><span data-stu-id="093ed-129">If you want to pass a part, then pass the message instead and then use the part.</span></span> <span data-ttu-id="093ed-130">Si solo quiere el valor de la parte, use el tipo de parte para pasarla.</span><span class="sxs-lookup"><span data-stu-id="093ed-130">If you only want the part value, then use the part type to pass the part.</span></span>  
  
-   <span data-ttu-id="093ed-131">No devuelven un **XLANGMessage** parámetro para una llamada al método.</span><span class="sxs-lookup"><span data-stu-id="093ed-131">Do not return an **XLANGMessage** parameter for a method call.</span></span> <span data-ttu-id="093ed-132">Si devuelve un **XLANGMessage** parámetro que se pasa en y, a continuación, no puede llamar a la **Dispose** método en el parámetro dentro de la llamada al método, se infringen intuitivamente la duración supuesta y también se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="093ed-132">If you return an **XLANGMessage** parameter that is passed in, and then you cannot call the **Dispose** method on the parameter inside the method call, it intuitively violates lifetime assumptions and it also throws an exception.</span></span> <span data-ttu-id="093ed-133">Al pasar un mensaje a través de un **XLANGMessage** parámetro al código de usuario, hacer referencia al mensaje a un contexto especial que normalmente no tiene mensajes que hagan referencia a él.</span><span class="sxs-lookup"><span data-stu-id="093ed-133">When passing a message through an **XLANGMessage** parameter to user code, you reference the message to a special context that does not normally have messages referenced to it.</span></span> <span data-ttu-id="093ed-134">La duración de este contexto es la duración de la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="093ed-134">The lifetime of this context is the lifetime of the orchestration instance.</span></span> <span data-ttu-id="093ed-135">Esto se debe a que BizTalk Server desconoce si el código de usuario se mantendrá en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="093ed-135">This is because BizTalk Server does not know whether the user code will hold onto the message.</span></span>  
  
     <span data-ttu-id="093ed-136">Cuando se cierra una instancia de orquestación, cualquier mensaje creado en esa instancia ya no es válido; por tanto, la duración de tal colección debe ser menor o igual que la duración de la instancia.</span><span class="sxs-lookup"><span data-stu-id="093ed-136">When an orchestration instance exits, any messages created in that instance are no longer valid, so the lifetime of such a collection should be less than or equal to that of the instance lifetime.</span></span> <span data-ttu-id="093ed-137">Sin embargo, si desea liberar una referencia de mensaje en un bucle cuando se pasa el mensaje a través de un **XLANGMessage** argumento que tiene la misma duración que la instancia de orquestación, puede llamar a  **XLANGMessage.Dispose** para liberar la referencia.</span><span class="sxs-lookup"><span data-stu-id="093ed-137">However, if you want to release a message reference in a loop when the message was passed through an **XLANGMessage** argument that has the same lifetime as the orchestration instance, then you can call **XLANGMessage.Dispose** to free up the reference.</span></span> <span data-ttu-id="093ed-138">Además, si se encuentra dentro del método de código de usuario, el **XLANGMessage** parámetro solo se usa de forma local y la duración del parámetro está contenida en que el de la llamada de función, también se puede llamar **XLANGMessage.Dispose**para liberar la referencia al contexto raíz y devolver el mensaje correspondiente el comportamiento de duración normal.</span><span class="sxs-lookup"><span data-stu-id="093ed-138">Moreover, if inside the user code method, the **XLANGMessage** parameter is only used locally and the lifetime of the parameter is contained in that of the function call, you can also call **XLANGMessage.Dispose** to free up the reference to the root context and give the corresponding message back the normal lifetime behavior.</span></span> <span data-ttu-id="093ed-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="093ed-139">For example:</span></span>  
  
    ```csharp
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
  
     <span data-ttu-id="093ed-140">Si coloca el XML en una colección, la propia clase debe tener un **Dispose** método de limpieza.</span><span class="sxs-lookup"><span data-stu-id="093ed-140">If you place the xlm in a collection, then the class itself must have a **Dispose** method for cleanup.</span></span> <span data-ttu-id="093ed-141">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="093ed-141">For example:</span></span>  
  
    ```csharp
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
  
     <span data-ttu-id="093ed-142">Se llamaría a **A.Dispose** cuando haya terminado con la colección de **XLANGMessages**.</span><span class="sxs-lookup"><span data-stu-id="093ed-142">You would call **A.Dispose** when you are finished with the collection of **XLANGMessages**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="093ed-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="093ed-143">See Also</span></span>  
 <span data-ttu-id="093ed-144">[Mensajes representados como esquemas XSD](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="093ed-144">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="093ed-145">[Mensajes representados como clases .NET](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="093ed-145">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 [<span data-ttu-id="093ed-146">Construcción de mensajes en código de usuario</span><span class="sxs-lookup"><span data-stu-id="093ed-146">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
