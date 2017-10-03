---
title: "Enviar un mensaje AS2 a través de un puerto de envío de archivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c5ce9ff-fd73-4d5f-9b16-387c1e520c3a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 555066cb81eabe7328734e73fd9598fbd2cd418a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sending-an-as2-message-over-a-file-send-port"></a>Enviar un mensaje AS2 a través de un puerto de envío de archivo
Los mensajes AS2 suelen enviarse a través de un adaptador de HTTP. No obstante, puede enviar mensajes AS2 a través de un adaptador de archivo si crea componentes personalizados. En este tema se describe cómo funcionaría esta solución y ofrece códigos de ejemplo para ella.  
  
 Cuando los mensajes AS2 se envían a través de HTTP, el codificador AS2 de la canalización de envío rellena la propiedad de contexto `HTTP.UserHttpHeaders` con los encabezados HTTP (y AS2) necesarios para el envío del mensaje. Toma estos encabezados de la propiedad de contexto `HTTP.UserHttpHeaders` existente, de propiedades de contexto independientes o de propiedades de entidad (en ese orden de prioridad). El adaptador HTTP del puerto de envío escribirá los encabezados en el mensaje y enviará el mensaje a través de HTTP.  
  
 Si utiliza un adaptador de archivo en lugar de un adaptador de HTTP en el puerto de envío, los valores de encabezado de la propiedad de contexto `HTTP.UserHttpHeaders` no se escribirán en el mensaje. Debe crear un componente de canalización personalizado para anteponer los encabezados de `HTTP.UserHttpHeaders` al mensaje. A continuación, el adaptador de archivo puede colocar el mensaje en una carpeta y será un mensaje AS2 que incluya los encabezados HTTP necesarios.  
  
 Es posible que necesite también crear un componente personalizado para asegurarse de que todos los encabezados AS2 están incluidos en la propiedad de contexto `HTTP.UserHttpHeaders`. Puede crear una orquestación personalizada o un componente de canalización personalizado antes de AS2Encoder para definir las propiedades de contexto que utiliza el codificador AS2 para generar `HTTP.UserHttpHeaders`.  
  
## <a name="writing-headers-to-an-as2-message"></a>Escribir encabezados en un mensaje AS2  
 Para generar un mensaje AS2 mediante un adaptador de archivo en lugar de un adaptador de HTTP, agregue un componente de canalización personalizado después del codificador AS2 en una canalización de envío AS2 personalizada. Incluya el código en el componente de canalización personalizado que escribe los encabezados desde la propiedad de contexto `HTTP.UserHttpHeaders` en el mensaje. Un ejemplo es el código de ejemplo siguiente:  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
        {  
            IPipelineContext pipelineContext = pContext;  
            IBaseMessage baseMessage = pInMsg;  
  
            //Prepend Headers  
            MemoryStream ms = new MemoryStream();  
            string strName = "UserHttpHeaders";  
            string strValue = (string)baseMessage.Context.Read(strName,  
              "http://schemas.microsoft.com/BizTalk/2003/  
              http-properties");  
  
            //Leave an empty line between the headers and the body  
            strValue += "\r\n";  
            ms.Write(Encoding.ASCII.GetBytes(strValue), 0,   
               Encoding.ASCII.GetByteCount(strValue));  
  
            //Append Body  
            Stream sr = baseMessage.BodyPart.Data;  
  
            //Read the body of the message and append it to the memory   
              stream containing the headers  
            int size = 1024;  
            byte[] buffer = new byte[size];  
            while (0 != (size = sr.Read(buffer, 0, buffer.Length)))  
            {  
                ms.Write(buffer, 0, size);  
            }  
  
            //Set the body of the message to the new memory stream  
            baseMessage.BodyPart.Data = ms;  
  
            //Rewind the stream  
            ms.Seek(0, SeekOrigin.Begin);  
  
            return baseMessage;  
        }  
```  
  
## <a name="promoting-as2-header-context-properties"></a>Promocionar propiedades de contexto de encabezado AS2  
 Puede promocionar propiedades de contexto de encabezado AS2 en el contexto de un mensaje mediante una orquestación personalizada o un componente de canalización personalizado.  
  
 Para promocionar propiedades de encabezado AS2 mediante un componente de canalización personalizado, agregue un componente de canalización personalizado antes del codificador AS2 en una canalización de envío AS2 personalizada. Puede utilizar código del ejemplo expuesto anteriormente para escribir encabezados desde `HTTP.UserHttpHeaders` en el mensaje, con la excepción de que podría reemplazar el método Read con un método Promote ofreciendo el nombre, el valor y el espacio de nombres de la propiedad de contexto que se va a promocionar.  
  
 Para promocionar las propiedades de encabezado AS2 mediante una orquestación personalizada, cree una orquestación con un puerto de recepción de archivos, una forma Construir mensaje y un puerto de envío de archivos. Agregue el código que establece las propiedades promocionadas que contienen los encabezados AS2 a la forma Construir mensaje. Debe agregar una referencia a `Microsoft.BizTalk.HttpTransport.dll` en la orquestación personalizada.  
  
 El espacio de nombres para los encabezados HTTP es `http://schemas.microsoft.com/BizTalk/2003/http-properties` para los encabezados que no son HTTP de AS2 y `http://schemas.microsoft.com/BizTalk/2003/as2-properties` para los encabezados AS2.  
  
 El siguiente código de ejemplo muestra cómo promocionar propiedades de encabezados AS2 en la forma Contruir mensaje de una orquestación. Este código promociona encabezados AS2 para un MDN.  
  
```  
Message_2=new System.Xml.XmlDocument();  
Message_2=Message_1;  
Message_2(EdiIntAS.IsAS2PayloadMessage)=false;  
Message_2(EdiIntAS.IsAS2AsynchronousMdn)=true;  
Message_2(EdiIntAS.IsAS2MdnResponseMessage)=true;  
Message_2(EdiIntAS.SendMDN)=true;  
Message_2(EdiIntAS.IsAS2MessageSigned)=false;  
Message_2(EdiIntAS.AS2To)="Party1";  
Message_2(EdiIntAS.AS2From)="Home";  
Message_2(EdiIntAS.MessageId)="123456";  
Message_2(EdiIntAS.OriginalMessageId)="2123456";  
Message_2(HTTP.UserHttpHeaders)="Message1-Id: xyz\r\nMyHeader: MyValue";  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones AS2 de BizTalk Server](../core/developing-and-configuring-biztalk-server-as2-solutions.md)