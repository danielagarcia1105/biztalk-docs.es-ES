---
title: Especificar el cuerpo del mensaje para los adaptadores de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, SOAP messages
- messages, WCF adapters
- WCF adapters, message bodies
- SOAP messages, WCF adapters
ms.assetid: b20364b7-0365-4636-b4d6-bde9c69b8dcb
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109ad486baa542aff3cd1c4a44804ff2fd79aac5
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="specifying-the-message-body-for-the-wcf-adapters"></a>Especificar el cuerpo del mensaje para los adaptadores de WCF
Puede usar el **mensajes** ficha en los adaptadores de WCF para especificar cómo se extrae el cuerpo del mensaje de BizTalk de un mensaje SOAP entrante y el cuerpo del mensaje de BizTalk se coloca en un mensaje SOAP saliente.  
  
## <a name="specifying-how-the-biztalk-message-body-is-extracted-from-an-incoming-soap-message"></a>Especificar cómo se extrae el cuerpo del mensaje de BizTalk de un mensaje SOAP entrante  
 Puede controlar cómo crear el cuerpo del mensaje de BizTalk entrante a partir de mensajes SOAP que llegan a través de los adaptadores de WCF. Las ilustraciones siguientes muestran el **mensajes** adaptadores de envío y la recepción de las pestañas de WCF-NetNamedPipe como ejemplos.  
  
 ![Adaptadores de recepción de la pestaña mensajes en WCF](../core/media/abbaccfc-092c-42c6-9207-fa1af28912ac.gif "abbaccfc-092c-42c6-9207-fa1af28912ac")  
  
 ![Adaptadores de envío de la pestaña mensajes en WCF](../core/media/58e1d490-5bd9-4571-87b1-4dea6dbfe2de.gif "58e1d490-5bd9-4571-87b1-4dea6dbfe2de")  
  
 Para especificar cómo se crea el cuerpo del mensaje de BizTalk, seleccione una de las siguientes opciones en el **cuerpo del mensaje entrante de BizTalk** sección en las ilustraciones anteriores:  
  
-   **Sobre--entero \<soap: Envelope\>**. Utiliza SOAP **sobres** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. El mensaje entrante completo se convierte en el cuerpo del mensaje de BizTalk. Use esta opción para crear el cuerpo del mensaje de BizTalk incorporando todos los encabezados.  
  
    > [!NOTE]
    >  Los encabezados SOAP se colocan en el contexto del mensaje, pero no se promocionan automáticamente. La promoción se puede realizar en un componente de canalización personalizada.  
  
-   **Cuerpo--contenido \<soap: Body\> elemento**. Utiliza el contenido del mensaje SOAP **cuerpo** elemento de un mensaje entrante para crear la parte del cuerpo de mensaje de BizTalk. Si el elemento **Body** tiene varios elementos secundarios, sólo el primero de ellos será la parte del cuerpo del mensaje de BizTalk.  
  
-   **Ruta--contenido ubicado por la ruta de cuerpo**. Usa la expresión de ruta de cuerpo en el **expresión de ruta de acceso del cuerpo** cuadro de texto para crear la parte del cuerpo de mensaje de BizTalk. Esta expresión se evalúa con respecto al elemento secundario inmediato del elemento **Cuerpo** de SOAP de un mensaje entrante. Cuando los mensajes entrantes incluyen datos binarios, se puede usar esta opción para que el cuerpo del mensaje de BizTalk incluya únicamente los datos binarios sin etiquetas.  
  
 Cuando el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada, el **codificación de nodo** propiedad se puede configurar para especificar el tipo de codificación esperado para el nodo especificado por la expresión de ruta de cuerpo el **expresión de ruta de acceso del cuerpo** cuadro de texto. Si la expresión de ruta de cuerpo coincide con más de un elemento, sólo se usa el primer elemento coincidente.  
  
> [!NOTE]
>  Para el **expresión de ruta de acceso del cuerpo** sólo el XPath que se admiten expresiones adecuadas para el procesamiento progresivo de XML de la propiedad. Para obtener más información sobre las expresiones XPath disponibles para esta propiedad, vea "El mejor de ambos mundos: combinación de XPath con el XmlReader" en [ http://go.microsoft.com/fwlink/?LinkID=75701 ](http://go.microsoft.com/fwlink/?LinkID=75701).  
  
 Si el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada y el **codificación de nodo** propiedad está establecida en **cadena**, los adaptadores de WCF esperan que el nodo coincidente tiene UTF-8 datos de caracteres codificados. Si los mensajes entrantes incluyen caracteres de escape datos de caracteres para los caracteres especiales XML como \< y \>, los adaptadores de WCF restauran los datos de carácter de escape al crear la parte del cuerpo de mensaje de BizTalk. Por ejemplo, si el nodo coincidente escape como datos de caracteres **&lt;FirstName&gt;CONTOSO&lt;/FirstName&gt;** los adaptadores WCF crean **\< FirstName\>CONTOSO\</FirstName\>** cuerpo del mensaje en la entrada de BizTalk.  
  
 Si el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada y el **codificación de nodo** propiedad está establecida en **hexadecimal** o **Base64**, el nodo coincidente puede tener válido **BinHex** o **Base64** secuencia. Si el nodo coincidente tiene una secuencia no válida, el cliente WCF recibe **FaultException**, un mensaje de error se registra en el registro de eventos en el equipo de BizTalk Server y se suspende ningún mensaje.  
  
 Si el **ruta--contenido ubicado por la ruta de cuerpo** opción está seleccionada y el **codificación de nodo** propiedad está establecida en **XML**, los adaptadores WCF crean el cuerpo del mensaje de BizTalk con el XML externo del nodo seleccionado por la expresión de ruta de acceso de cuerpo en el **expresión de ruta de acceso del cuerpo** cuadro de texto.  
  
 Si el nodo coincidente no tiene datos codificados como se especifica en el **codificación de nodo** propiedad, se crea un cuerpo de mensaje de BizTalk entrante vacío.  
  
 Por ejemplo, suponga que los adaptadores de envío WCF reciben el mensaje de SOAP siguiente procedente de clientes de WCF:  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/OrderRefresh</a:Action>   
    <a:MessageID>urn:uuid:59e74507-66d0-4d50-be70-c3ec248b6f78</a:MessageID>   
    <a:ReplyTo>  
       <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>   
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>   
  </s:Header>  
  <s:Body>  
    <Order xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
     <OrderDetail>  
       <CustomerID>CONTOSO</CustomerID>   
       <OrderID>00000000</OrderID>   
     </OrderDetail>  
    </Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 Si configura el **cuerpo del mensaje entrante de BizTalk** sección tal y como se muestra en la siguiente tabla, el mensaje SOAP entrante anterior se convierte en la parte del cuerpo de mensaje de BizTalk entrante.  
  
|Cuerpo de mensaje entrante de BizTalk|Expresión de ruta de cuerpo|Codificación de nodo|  
|----------------------------------|--------------------------|-------------------|  
|**Sobre--entero \<soap: Envelope\>**|N/D|N/D|  
  
 Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean la parte de cuerpo de mensaje de BizTalk entrante para que contenga únicamente la **orden** elemento en la versión anterior mensaje SOAP entrante.  
  
|Cuerpo de mensaje entrante de BizTalk|Expresión de ruta de cuerpo|Codificación de nodo|  
|----------------------------------|--------------------------|-------------------|  
|**Cuerpo--contenido \<soap: Body\> elemento**|N/D|N/D|  
  
 Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la tabla siguiente, los adaptadores de WCF esperan que el nodo de entrada que coincide con la expresión de ruta de cuerpo tendrá datos de caracteres con codificación UTF-8.  
  
|Cuerpo de mensaje entrante de BizTalk|Expresión de ruta de cuerpo|Codificación de nodo|  
|----------------------------------|--------------------------|-------------------|  
|**Ruta--contenido ubicado por la ruta de cuerpo**|/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']|**String**|  
  
 Para el mensaje SOAP entrante anterior, los adaptadores de WCF usan los datos de caracteres, **CONTOSO**, de la **CustomerID** elemento que se va a crear la parte del cuerpo de mensaje de BizTalk entrante.  
  
> [!NOTE]
>  No se puede utilizar la sintaxis abreviada de XPath, **/Order/OrderDetail/CustomerID**, para el mensaje SOAP entrante anterior. Esto es porque la sintaxis abreviada de XPath devuelve el nodo no declarado en un espacio de nombres y el **CustomerID** elemento del mensaje SOAP anterior se declara en el **http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess** espacio de nombres con espacios de nombres predeterminados.  
  
 Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la siguiente tabla, el **CustomID** elemento en el mensaje SOAP entrante anterior debe tener válido **BinHex**o **Base64** secuencia.  
  
|Cuerpo de mensaje entrante de BizTalk|Expresión de ruta de cuerpo|Codificación de nodo|  
|----------------------------------|--------------------------|-------------------|  
|**Ruta--contenido ubicado por la ruta de cuerpo**|/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']|**Hex** o **Base64**|  
  
 Si configura el **cuerpo del mensaje de BizTalk** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean el cuerpo del mensaje de BizTalk entrante para el mensaje SOAP entrante anterior tal como se muestra en el código después de la tabla.  
  
|Cuerpo de mensaje entrante de BizTalk|Expresión de ruta de cuerpo|Codificación de nodo|  
|----------------------------------|--------------------------|-------------------|  
|**Ruta--contenido ubicado por la ruta de cuerpo**|/*[local-name()='Order']/\*[local-name()='OrderDetail']/\*[local-name()='CustomerID']|**XML**|  
  
```  
<CustomerID xmlns="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">CONTOSO</CustomerID>   
```  
  
## <a name="specifying-the-source-of-the-outbound-wcf-message-body"></a>Especificar el origen del cuerpo del mensaje WCF saliente  
 Puede controlar cómo crear el cuerpo del mensaje de BizTalk saliente a partir de mensajes WCF que llegan a través de los adaptadores de WCF. Para especificar cómo se coloca el cuerpo del mensaje de BizTalk en el cuerpo del mensaje WCF saliente, puede usar una de las siguientes opciones en el **cuerpo del mensaje saliente de WCF** sección en la **mensajes** pestaña tal y como se muestra en el figuras en la sección anterior:  
  
-   **Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**. La parte del cuerpo de mensaje de BizTalk se utiliza para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente. El cuerpo del mensaje de BizTalk saliente se convierte en el cuerpo del mensaje SOAP saliente.  
  
-   **Plantilla--contenido especificado por plantilla**. Utiliza la plantilla proporcionada en el **XML** cuadro de texto para crear el contenido del mensaje SOAP **cuerpo** (elemento) para un mensaje saliente. Los adaptadores de WCF con **cuerpo--cuerpo de mensaje de respuesta de BizTalk** (el valor predeterminado) opción no permite el envío de mensajes no XML, como imágenes de mapa de bits y datos de caracteres. Puede usar el **plantilla--contenido especificado por plantilla** opción para los adaptadores de WCF enviar mensajes no XML codificados en **base64**, **hexadecimal**, o **cadena** .  
  
 Cuando el **plantilla--contenido especificado por plantilla** opción está seleccionada, debe proporcionar un elemento XML de plantilla arbitrario en el **cuerpo del mensaje saliente de WCF - XML** cuadro de texto. El elemento XML de plantilla debe contener lo siguiente **bts-msg-body** elemento solamente una vez a menos que el elemento XML de plantilla se deja en blanco:  
  
```  
<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2010" encoding="[base64|hex|string|xml]"/>  
```  
  
 Los adaptadores de WCF codifican el cuerpo del mensaje de BizTalk según el **codificación** de atributo en la plantilla XML y, a continuación, reemplace el **bts-msg-body** elemento con el cuerpo de mensaje de BizTalk codificado al crear mensajes WCF salientes. Si el **cuerpo del mensaje saliente de WCF - XML** cuadro de texto se deja vacío, los adaptadores de WCF codifican el cuerpo del mensaje de BizTalk en **Base64**y, a continuación, coloque el **Base64** de secuencia en el cuerpo del mensaje SOAP saliente.  
  
 Si el **codificación** atributo en la plantilla XML se establece en **cadena**, los adaptadores de WCF codifican la parte del cuerpo de mensaje de BizTalk como datos de caracteres con codificación UTF-8, en el que los caracteres especiales de XML como \< y \> son caracteres de escape.  
  
 Si el **codificación** atributo en la plantilla XML se establece en **base64** o **hexadecimal**, los adaptadores de WCF codifican la parte del cuerpo de mensaje de BizTalk como un **BinHex** o **Base64** secuencia.  
  
 Si el **codificación** atributo en la plantilla XML se establece en **xml**, los adaptadores de WCF sustituyen el **bts-msg-body** elemento con el cuerpo del mensaje de BizTalk saliente para crear el mensaje saliente de WCF.  
  
 Por ejemplo, suponga que los adaptadores de WCF tienen que enviar la parte del cuerpo del mensaje de BizTalk siguiente a clientes de WCF:  
  
```  
<ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
```  
  
 Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.  
  
|Cuerpo de mensaje saliente de WCF|XML|  
|-------------------------------|---------|  
|**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**|N/D|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:6a706a54-c4f5-4767-909d-a992c7c26dba</a:MessageID>  
    <a:ReplyTo>  
<a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CONTOSO</ns0:CustomerID>  
    <ns0:OrderID>01A2c</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
  </s:Body>  
</s:Envelope>  
```  
  
 Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.  
  
|Cuerpo de mensaje saliente de WCF|XML|  
|-------------------------------|---------|  
|**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**|\<Book\><br /><br /> \<**BTS-msg-body** xmlns = "http://www.microsoft.com/schemas/bts2010" codificación = "**cadena**" /\><br /><br /> \</Book\>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:05dde292-eedd-467e-b0d2-f1b8f0757410</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessService</a:To>  
  </s:Header>  
  <s:Body>  
    <Book><ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  <ns0:OrderDetail>    <ns0:CustomerID>CONTOSO</ns0:CustomerID>    <ns0:OrderID> 01A2c</ns0:OrderID>  </ns0:OrderDetail></ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```  
  
 Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.  
  
|Cuerpo de mensaje saliente de WCF|XML|  
|-------------------------------|---------|  
|**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**|\<Book\><br /><br /> \<**BTS-msg-body** xmlns = "http://www.microsoft.com/schemas/bts2010" codificación = "**base64**" /\><br /><br /> \</Book\>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://ww  
w.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe  
/OrderProcess/IOrderProcess/Request</a:Action>  
    <a:MessageID>urn:uuid:cb3cac6d-a542-4a90-bad8-cdbfa8251112</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessSer  
vice</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>77u/PG5zMDpPcmRlciB4bWxuczpuczA9Imh0dHA6Ly9NaWNyb3NvZnQuU2FtcGxlcy5CaX  
pUYWxrLk5ldE5hbWVkUGlwZS9PcmRlclByb2Nlc3MiPg0KICA8bnMwOk9yZGVyRGV0YWlsPg0KICAgID  
xuczA6Q3VzdG9tZXJJRD5DT05UT1NPPC9uczA6Q3VzdG9tZXJJRD4NCiAgICA8bnMwOk9yZGVySUQ+MD  
FBMmM8L25zMDpPcmRlcklEPg0KICA8L25zMDpPcmRlckRldGFpbD4NCjwvbnMwOk9yZGVyPg==</Book  
>  
  </s:Body>  
</s:Envelope>  
```  
  
 Si configura el **cuerpo del mensaje saliente de WCF** sección tal y como se muestra en la tabla siguiente, los adaptadores WCF crean los mensajes WCF salientes como se muestra en el código después de la tabla.  
  
|Cuerpo de mensaje saliente de WCF|XML|  
|-------------------------------|---------|  
|**Cuerpo--Cuerpo de mensaje de respuesta de BizTalk**|\<Book\><br /><br /> \<**BTS-msg-body** xmlns = "http://www.microsoft.com/schemas/bts2010" codificación = "**xml**" /\><br /><br /> \</Book\>|  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess/IOrderProcess/Request</a:A  
ction>  
    <a:MessageID>{513C123C-0600-4A1C-BEE2-EF83E0EFEB15}</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address>  
    </a:ReplyTo>  
    <a:To s:mustUnderstand="1">net.pipe://mycomputer/NetNamedPipeOrderProcessServiceBizTalk</a:To>  
  </s:Header>  
  <s:Body>  
    <Book>  
      <ns0:Order xmlns:ns0="http://Microsoft.Samples.BizTalk.NetNamedPipe/OrderProcess">  
  <ns0:OrderDetail>  
    <ns0:CustomerID>CustomerID_0</ns0:CustomerID>  
    <ns0:OrderID>OrderID_0</ns0:OrderID>  
  </ns0:OrderDetail>  
</ns0:Order>  
    </Book>  
  </s:Body>  
</s:Envelope>  
```