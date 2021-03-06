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
# <a name="messages-represented-as-xlangmessage"></a>Mensajes representados como XLANGMessage
Un **XLANGMessage** objeto representa una instancia de mensaje declarada con un servicio XLANG. Este objeto se obtiene pasando una referencia a un mensaje como un parámetro en una llamada de método. Un **XLANGPart** objeto representa una parte de mensaje contenida en una instancia de mensaje dentro de un servicio XLANG. Este objeto se obtiene pasando una referencia de los elementos en una invocación del método donde es el tipo de parámetro receptora **XLANGPart** o bien recorriendo una referencia del pasado **XLANGMessage**.  
  
 Una variable de mensaje de orquestación se puede pasar a un componente de usuario y recibió como un **XLANGMessage** objeto. El **XLANGMessage** objeto permite obtener acceso a las partes y acceso a las propiedades de mensaje. El usuario puede "mantener" un **XLANGMessage** y con ello ampliar su duración más allá del ámbito declarado. Posteriormente, una **XLANGMessage** puede devuelto desde un método y se asigna a una variable de mensaje en una orquestación.  
  
## <a name="constructing-an-xlangmessage"></a>Construir un XLANGMessage  
 Al construir un **XLANGMessage** con una secuencia, el tipo de secuencia debe implementar **IStreamFactory** o ser un **MemoryStream**. Ejemplo de código siguiente muestra cómo construir un **XLANGMessage**:  
  
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
  
 Puede que a veces desee crear un nuevo mensaje sin transformar un mensaje de origen. Puede hacerlo mediante el uso de una variable de tipo **System.Xml.XmlDocument** y cargando o construyendo el contenido adecuado. En el ejemplo siguiente, se carga XML desde una cadena mediante el uso de la **LoadXml** método **XmlDocument**:  
  
```csharp
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 En el ejemplo siguiente se carga XML desde un archivo mediante el uso de la **carga** método **XmlDocument**:  
  
```csharp
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  Si desea construir mensajes más grandes, use uno de los métodos de transmisión por secuencias se muestra en la sección anterior o considere el uso de la **transformar** forma en el Diseñador de orquestaciones.  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a>Consideraciones al usar XLANGMessage y XLANGPart  
 Cuando se usa **XLANGMessage** y **XLANGPart** en código de usuario, considere lo siguiente:  
  
-   No pase una parte de mensaje como un **XLANGPart** un valor de tipo de valor devuelto o argumento **XLANGPart**. Debería pasar **XLANGPart** como el tipo de elemento. Por ejemplo:  
  
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
  
     También puede pasar el propio mensaje como un **XLANGMessage** y usar el **XLANGMessage** operadores de subíndice para tener acceso a la parte dentro de la llamada de función. Sin embargo, no debería colocar una **XLANGPart** en una colección cuya duración se extiende más allá de la duración de la llamada de función. En su lugar, debe colocar el **XLANGMessage** en la colección. Por ejemplo:  
  
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
  
-   No defina un parámetro de orquestación como **XLANGMessage** o **XLANGPart**. Si quiere pasar un mensaje, use un parámetro de tipo mensaje para ello. Si quiere pasar una parte, pase el mensaje en su lugar y, a continuación, use la parte. Si solo quiere el valor de la parte, use el tipo de parte para pasarla.  
  
-   No devuelven un **XLANGMessage** parámetro para una llamada al método. Si devuelve un **XLANGMessage** parámetro que se pasa en y, a continuación, no puede llamar a la **Dispose** método en el parámetro dentro de la llamada al método, se infringen intuitivamente la duración supuesta y también se produce una excepción. Al pasar un mensaje a través de un **XLANGMessage** parámetro al código de usuario, hacer referencia al mensaje a un contexto especial que normalmente no tiene mensajes que hagan referencia a él. La duración de este contexto es la duración de la instancia de orquestación. Esto se debe a que BizTalk Server desconoce si el código de usuario se mantendrá en el mensaje.  
  
     Cuando se cierra una instancia de orquestación, cualquier mensaje creado en esa instancia ya no es válido; por tanto, la duración de tal colección debe ser menor o igual que la duración de la instancia. Sin embargo, si desea liberar una referencia de mensaje en un bucle cuando se pasa el mensaje a través de un **XLANGMessage** argumento que tiene la misma duración que la instancia de orquestación, puede llamar a  **XLANGMessage.Dispose** para liberar la referencia. Además, si se encuentra dentro del método de código de usuario, el **XLANGMessage** parámetro solo se usa de forma local y la duración del parámetro está contenida en que el de la llamada de función, también se puede llamar **XLANGMessage.Dispose**para liberar la referencia al contexto raíz y devolver el mensaje correspondiente el comportamiento de duración normal. Por ejemplo:  
  
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
  
     Si coloca el XML en una colección, la propia clase debe tener un **Dispose** método de limpieza. Por ejemplo:  
  
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
  
     Se llamaría a **A.Dispose** cuando haya terminado con la colección de **XLANGMessages**.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes representados como esquemas XSD](../core/messages-represented-as-xsd-schemas.md)   
 [Mensajes representados como clases .NET](../core/messages-represented-as-net-classes.md)   
 [Construcción de mensajes en código de usuario](../core/constructing-messages-in-user-code.md)
