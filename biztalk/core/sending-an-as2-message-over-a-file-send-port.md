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
# <a name="sending-an-as2-message-over-a-file-send-port"></a><span data-ttu-id="a46a6-102">Enviar un mensaje AS2 a través de un puerto de envío de archivo</span><span class="sxs-lookup"><span data-stu-id="a46a6-102">Sending an AS2 Message over a FILE Send Port</span></span>
<span data-ttu-id="a46a6-103">Los mensajes AS2 suelen enviarse a través de un adaptador de HTTP.</span><span class="sxs-lookup"><span data-stu-id="a46a6-103">AS2 messages are normally sent over an HTTP adapter.</span></span> <span data-ttu-id="a46a6-104">No obstante, puede enviar mensajes AS2 a través de un adaptador de archivo si crea componentes personalizados.</span><span class="sxs-lookup"><span data-stu-id="a46a6-104">You can, however, send AS2 messages over a FILE adapter if you create custom components.</span></span> <span data-ttu-id="a46a6-105">En este tema se describe cómo funcionaría esta solución y ofrece códigos de ejemplo para ella.</span><span class="sxs-lookup"><span data-stu-id="a46a6-105">This topic describes how such a solution would work and provides sample code for the solution.</span></span>  
  
 <span data-ttu-id="a46a6-106">Cuando los mensajes AS2 se envían a través de HTTP, el codificador AS2 de la canalización de envío rellena la propiedad de contexto `HTTP.UserHttpHeaders` con los encabezados HTTP (y AS2) necesarios para el envío del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46a6-106">When AS2 messages are sent over HTTP, the AS2 Encoder in the send pipeline populates the `HTTP.UserHttpHeaders` context property with the HTTP (and AS2) headers required for sending the message.</span></span> <span data-ttu-id="a46a6-107">Toma estos encabezados de la propiedad de contexto `HTTP.UserHttpHeaders` existente, de propiedades de contexto independientes o de propiedades de entidad (en ese orden de prioridad).</span><span class="sxs-lookup"><span data-stu-id="a46a6-107">It takes these headers either from the existing `HTTP.UserHttpHeaders` context property, from separate context properties, or from agreement properties (in that order of precedence).</span></span> <span data-ttu-id="a46a6-108">El adaptador HTTP del puerto de envío escribirá los encabezados en el mensaje y enviará el mensaje a través de HTTP.</span><span class="sxs-lookup"><span data-stu-id="a46a6-108">The HTTP adapter in the send port will write the headers to the message, and send the message over HTTP.</span></span>  
  
 <span data-ttu-id="a46a6-109">Si utiliza un adaptador de archivo en lugar de un adaptador de HTTP en el puerto de envío, los valores de encabezado de la propiedad de contexto `HTTP.UserHttpHeaders` no se escribirán en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46a6-109">If you use a FILE adapter instead of an HTTP adapter in the send port, the header values in the `HTTP.UserHttpHeaders` context property will not be written to the message.</span></span> <span data-ttu-id="a46a6-110">Debe crear un componente de canalización personalizado para anteponer los encabezados de `HTTP.UserHttpHeaders` al mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46a6-110">You have to create a custom pipeline component to prepend the headers in `HTTP.UserHttpHeaders` to the message.</span></span> <span data-ttu-id="a46a6-111">A continuación, el adaptador de archivo puede colocar el mensaje en una carpeta y será un mensaje AS2 que incluya los encabezados HTTP necesarios.</span><span class="sxs-lookup"><span data-stu-id="a46a6-111">The message can then be dropped into a folder by the FILE adapter, and will be an AS2 message that includes the required HTTP headers.</span></span>  
  
 <span data-ttu-id="a46a6-112">Es posible que necesite también crear un componente personalizado para asegurarse de que todos los encabezados AS2 están incluidos en la propiedad de contexto `HTTP.UserHttpHeaders`.</span><span class="sxs-lookup"><span data-stu-id="a46a6-112">You may also need to create a custom component to ensure that all the AS2 headers are included in the `HTTP.UserHttpHeaders` context property.</span></span> <span data-ttu-id="a46a6-113">Puede crear una orquestación personalizada o un componente de canalización personalizado antes de AS2Encoder para definir las propiedades de contexto que utiliza el codificador AS2 para generar `HTTP.UserHttpHeaders`.</span><span class="sxs-lookup"><span data-stu-id="a46a6-113">You can create either a custom orchestration, or a custom pipeline component before the AS2Encoder, to set the context properties that the AS2 Encoder uses to build `HTTP.UserHttpHeaders`.</span></span>  
  
## <a name="writing-headers-to-an-as2-message"></a><span data-ttu-id="a46a6-114">Escribir encabezados en un mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="a46a6-114">Writing Headers to an AS2 Message</span></span>  
 <span data-ttu-id="a46a6-115">Para generar un mensaje AS2 mediante un adaptador de archivo en lugar de un adaptador de HTTP, agregue un componente de canalización personalizado después del codificador AS2 en una canalización de envío AS2 personalizada.</span><span class="sxs-lookup"><span data-stu-id="a46a6-115">To generate an AS2 message using a FILE adapter, rather than an HTTP adapter, add a custom pipeline component after the AS2 Encoder in a custom AS2 send pipeline.</span></span> <span data-ttu-id="a46a6-116">Incluya el código en el componente de canalización personalizado que escribe los encabezados desde la propiedad de contexto `HTTP.UserHttpHeaders` en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46a6-116">Include code in the custom pipeline component that writes the headers from the `HTTP.UserHttpHeaders` context property into the message.</span></span> <span data-ttu-id="a46a6-117">Un ejemplo es el código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a46a6-117">An example is the following sample code:</span></span>  
  
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
  
## <a name="promoting-as2-header-context-properties"></a><span data-ttu-id="a46a6-118">Promocionar propiedades de contexto de encabezado AS2</span><span class="sxs-lookup"><span data-stu-id="a46a6-118">Promoting AS2 Header Context Properties</span></span>  
 <span data-ttu-id="a46a6-119">Puede promocionar propiedades de contexto de encabezado AS2 en el contexto de un mensaje mediante una orquestación personalizada o un componente de canalización personalizado.</span><span class="sxs-lookup"><span data-stu-id="a46a6-119">You can promote AS2 header properties into the context of a message using either a custom orchestration or a custom pipeline component.</span></span>  
  
 <span data-ttu-id="a46a6-120">Para promocionar propiedades de encabezado AS2 mediante un componente de canalización personalizado, agregue un componente de canalización personalizado antes del codificador AS2 en una canalización de envío AS2 personalizada.</span><span class="sxs-lookup"><span data-stu-id="a46a6-120">To promote AS2 header properties using a custom pipeline component, add a custom pipeline component before the AS2 Encoder in a custom AS2 send pipeline.</span></span> <span data-ttu-id="a46a6-121">Puede utilizar código del ejemplo expuesto anteriormente para escribir encabezados desde `HTTP.UserHttpHeaders` en el mensaje, con la excepción de que podría reemplazar el método Read con un método Promote ofreciendo el nombre, el valor y el espacio de nombres de la propiedad de contexto que se va a promocionar.</span><span class="sxs-lookup"><span data-stu-id="a46a6-121">You can use code from the sample code shown above for writing headers from `HTTP.UserHttpHeaders` into the message, with the exception that you would replace the Read method with a Promote method, providing the name, value, and namespace of the context property to be promoted.</span></span>  
  
 <span data-ttu-id="a46a6-122">Para promocionar las propiedades de encabezado AS2 mediante una orquestación personalizada, cree una orquestación con un puerto de recepción de archivos, una forma Construir mensaje y un puerto de envío de archivos.</span><span class="sxs-lookup"><span data-stu-id="a46a6-122">To promote AS2 header properties using a custom orchestration, create an orchestration with a FILE receive port, a Construct Message shape, and a FILE send port.</span></span> <span data-ttu-id="a46a6-123">Agregue el código que establece las propiedades promocionadas que contienen los encabezados AS2 a la forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="a46a6-123">To the Construct Message shape, add code setting the promoted properties that contain the AS2 headers.</span></span> <span data-ttu-id="a46a6-124">Debe agregar una referencia a `Microsoft.BizTalk.HttpTransport.dll` en la orquestación personalizada.</span><span class="sxs-lookup"><span data-stu-id="a46a6-124">You must add a reference to `Microsoft.BizTalk.HttpTransport.dll` in the custom orchestration.</span></span>  
  
 <span data-ttu-id="a46a6-125">El espacio de nombres para los encabezados HTTP es `http://schemas.microsoft.com/BizTalk/2003/http-properties` para los encabezados que no son HTTP de AS2 y `http://schemas.microsoft.com/BizTalk/2003/as2-properties` para los encabezados AS2.</span><span class="sxs-lookup"><span data-stu-id="a46a6-125">The namespaces for HTTP headers is `http://schemas.microsoft.com/BizTalk/2003/http-properties` for non-AS2 HTTP headers and `http://schemas.microsoft.com/BizTalk/2003/as2-properties` for AS2 headers.</span></span>  
  
 <span data-ttu-id="a46a6-126">El siguiente código de ejemplo muestra cómo promocionar propiedades de encabezados AS2 en la forma Contruir mensaje de una orquestación.</span><span class="sxs-lookup"><span data-stu-id="a46a6-126">The following sample code shows how to promote AS2 header properties in the Construct Message shape of an orchestration.</span></span> <span data-ttu-id="a46a6-127">Este código promociona encabezados AS2 para un MDN.</span><span class="sxs-lookup"><span data-stu-id="a46a6-127">This code promotes AS2 headers for an MDN.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a46a6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a46a6-128">See Also</span></span>  
 [<span data-ttu-id="a46a6-129">Desarrollar y configurar soluciones AS2 de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a46a6-129">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)