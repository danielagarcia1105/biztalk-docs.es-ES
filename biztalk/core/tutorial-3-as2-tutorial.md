---
title: 'Tutorial 3: Tutorial de AS2 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 018829a9-e670-4b87-bac5-7f7b1332d90e
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629d1390b6471fb85a0b9e6fb6b605bedb043a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013469"
---
# <a name="tutorial-3-as2-tutorial"></a><span data-ttu-id="fc2e0-102">Tutorial 3: Tutorial de AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-102">Tutorial 3: AS2 Tutorial</span></span>
<span data-ttu-id="fc2e0-103">En este tutorial, establezca una solución que reciba y envíe mensajes de cifrado EDIINT/AS2 a través de un transporte HTTP.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-103">In this tutorial, you set up a solution that receives and sends EDIINT/AS2-encoded messages over an HTTP transport.</span></span>  
  
 <span data-ttu-id="fc2e0-104">**Cómo funciona la solución del Tutorial**</span><span class="sxs-lookup"><span data-stu-id="fc2e0-104">**How the Tutorial Solution Works**</span></span>  
  
 <span data-ttu-id="fc2e0-105">La solución hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc2e0-105">The solution will do the following:</span></span>  
  
- <span data-ttu-id="fc2e0-106">Recibir un mensaje AS2 de un socio comercial (Fabrikam)</span><span class="sxs-lookup"><span data-stu-id="fc2e0-106">Receive an AS2 message from a partner (Fabrikam)</span></span>  
  
- <span data-ttu-id="fc2e0-107">Devolver una respuesta MDN de forma asíncrona al socio comercial</span><span class="sxs-lookup"><span data-stu-id="fc2e0-107">Return an MDN response asynchronously to the partner</span></span>  
  
- <span data-ttu-id="fc2e0-108">Procesar la carga EDI del mensaje AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-108">Process the EDI payload of the AS2 message</span></span>  
  
- <span data-ttu-id="fc2e0-109">Devolver una confirmación 997 al socio comercial (Fabrikam) a través de AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-109">Return a 997 acknowledgment to the partner (Fabrikam) over AS2</span></span>  
  
- <span data-ttu-id="fc2e0-110">Enrutar un archivo XML que contenga la carga del mensaje EDI a una aplicación de servidor de la organización propia (Contoso).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-110">Route an XML file containing the payload of the EDI message to a backend application of the home organization (Contoso).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fc2e0-111">Esta solución no utiliza la firma o cifrado para ayudar a garantizar la seguridad de los mensajes AS2.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-111">This solution does not use signing or encryption to help ensure the security of AS2 messages.</span></span>  
  
  <span data-ttu-id="fc2e0-112">**Componentes de tutorial**</span><span class="sxs-lookup"><span data-stu-id="fc2e0-112">**Tutorial Components**</span></span>  
  
  <span data-ttu-id="fc2e0-113">Esta solución utilizará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc2e0-113">This solution will use the following:</span></span>  
  
- <span data-ttu-id="fc2e0-114">Un Http recibe filtro ISAPI de BTS para recibir el mensaje AS2/EDI del remitente **(/Contoso/BTSHTTPReceive.dll**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-114">A BTS Http Receive ISAPI Filter to receive the AS2/EDI message from the sender **(/Contoso/BTSHTTPReceive.dll**).</span></span>  
  
- <span data-ttu-id="fc2e0-115">Una página Web de ASPX para simular el socio comercial al devolver una confirmación 997 y MDN (**http://localhost/Fabrikam/Default.aspx**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-115">An ASPX Web page to simulate the partner by returning a 997 acknowledgment and an MDN (**http://localhost/Fabrikam/Default.aspx**).</span></span>  
  
- <span data-ttu-id="fc2e0-116">Un archivo de proyecto que va a utilizar para implementar un esquema 864 y otros esquemas (**Schemas.btproj**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-116">A project file that you will use to deploy an 864 schema and other schemas (**Schemas.btproj**).</span></span>  
  
- <span data-ttu-id="fc2e0-117">Una recepción HTTP unidireccional ubicación para recibir el archivo EDI (**Receive_AS2**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-117">A one-way HTTP receive location to receive the EDI file (**Receive_AS2**).</span></span> <span data-ttu-id="fc2e0-118">Esta ubicación de recepción utiliza la canalización AS2EdiReceive que contenga el descodificador AS2 y desensamblador EDI.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-118">This receive location uses the default AS2EdiReceive pipeline that contains the AS2 Decoder and EDI Disassembler.</span></span>  
  
- <span data-ttu-id="fc2e0-119">Un HTTP dinámico puerto de envío para devolver un MDN asíncrono (**Send_Async_MDN**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-119">A dynamic HTTP send port to return an asynchronous MDN (**Send_Async_MDN**).</span></span> <span data-ttu-id="fc2e0-120">Este puerto de envío utiliza la canalización AS2Send que contenga el codificador AS2.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-120">This send port uses the AS2Send pipeline that contains the AS2 Encoder.</span></span>  
  
- <span data-ttu-id="fc2e0-121">Un archivo unidireccional estático puerto de envío para enrutar la carga EDI en un archivo XML en una carpeta de back-end (**Send_Payload_EdiXml**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-121">A static one-way FILE send port to route the EDI payload in an XML file to a back-end folder (**Send_Payload_EdiXml**).</span></span> <span data-ttu-id="fc2e0-122">Este puerto de envío utiliza la canalización de envío PassThruTransmit.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-122">This send port uses the PassThruTransmit send pipeline.</span></span>  
  
- <span data-ttu-id="fc2e0-123">Un HTTP unidireccional estático puerto de envío para devolver una confirmación 997 al socio comercial a través de AS2 (**Send_Async_997**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-123">A static one-way HTTP send port to return a 997 acknowledgment to the partner over AS2 (**Send_Async_997**).</span></span> <span data-ttu-id="fc2e0-124">Este puerto de envío utiliza la canalización AS2Send que incluye el codificador AS2 pero no necesita el ensamblador EDI.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-124">This send port uses the AS2Send pipeline that includes the AS2 Encoder, but has no need for the EDI Assembler.</span></span>  
  
- <span data-ttu-id="fc2e0-125">Un archivo de proyecto que va a utilizar para crear una aplicación para enviar el archivo EDI del socio comercial Fabrikam a BizTalk (**Sender.csproj**).</span><span class="sxs-lookup"><span data-stu-id="fc2e0-125">A project file that you will use to build an application to send the EDI file from the Fabrikam partner to BizTalk (**Sender.csproj**).</span></span>  
  
  <span data-ttu-id="fc2e0-126">**Flujo de mensajes**</span><span class="sxs-lookup"><span data-stu-id="fc2e0-126">**Message Flow**</span></span>  
  
  <span data-ttu-id="fc2e0-127">El flujo de mensajes en la solución completa será como se muestra en la siguiente figura:</span><span class="sxs-lookup"><span data-stu-id="fc2e0-127">The message flow in the completed solution will be as shown in the following figure:</span></span>  
  
  <span data-ttu-id="fc2e0-128">![Flujo de mensajes del tutorial de AS2](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")</span><span class="sxs-lookup"><span data-stu-id="fc2e0-128">![AS2 tutorial message flow](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")</span></span>  
  
  <span data-ttu-id="fc2e0-129">Los componentes de tutorial procesan los mensajes como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="fc2e0-129">The tutorial components process the message as follows:</span></span>  
  
1. <span data-ttu-id="fc2e0-130">Usa el **aplicación sender.exe** para enviar el mensaje EDI/AS2 original del socio comercial Fabrikam al equipo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-130">You use the **sender.exe application** to send the original EDI/AS2 message from the partner Fabrikam to the BizTalk Server computer.</span></span> <span data-ttu-id="fc2e0-131">Sender.exe envía el mensaje EDI/AS2 al directorio virtual de Contoso.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-131">Sender.exe sends the EDI/AS2 message to the Contoso virtual directory.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fc2e0-132">Puede que los eventos de esta lista no se produzcan en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-132">The events in this list may not occur in the order shown.</span></span>  
   >   
   >  <span data-ttu-id="fc2e0-133">El mensaje de prueba es X12_00401_864.edi en \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-133">The test message is X12_00401_864.edi in \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial.</span></span>  
  
2. <span data-ttu-id="fc2e0-134">El **Receive_AS2** unidireccional recibe ubicación recibe el mensaje EDI de Fabrikam. utiliza la extensión ISAPI BTSHTTPReceive.dll para recoger el archivo del directorio virtual de Contoso.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-134">The **Receive_AS2** one-way receive location receives the EDI message from Fabrikam, using the BTSHTTPReceive.dll ISAPI extension to pick the file up from the Contoso virtual directory.</span></span> <span data-ttu-id="fc2e0-135">La canalización de recepción descodifica el mensaje AS2, desensambla el intercambio EDI y, a continuación, coloca el mensaje XML en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-135">The receive pipeline decodes the AS2 message, disassembles the EDI interchange, and then drops the message XML into the MessageBox.</span></span>  
  
3. <span data-ttu-id="fc2e0-136">La canalización de recepción genera un MDN para el mensaje AS2 y cuando se configura para que el MDN sea asíncrono, la canalización de recepción coloca el MDN en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-136">The receive pipeline generates an MDN for the AS2 message, and since the MDN is set up to be asynchronous, the receive pipeline drops the MDN into the MessageBox.</span></span>  
  
4. <span data-ttu-id="fc2e0-137">La canalización de recepción genera una confirmación 997 en respuesta al intercambio EDI y coloca esta confirmación en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-137">The receive pipeline generates a 997 acknowledgment in response to the EDI interchange, and drops the 997 into the MessageBox.</span></span>  
  
5. <span data-ttu-id="fc2e0-138">El **Send_Payload_EdiXml** puerto de envío unidireccional estático recoge la carga EDI del cuadro de mensajes, filtrando el BTS. Propiedad de contexto de MessageType.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-138">The **Send_Payload_EdiXml** static one-way send port picks up the EDI payload from the MessageBox, filtering on the BTS.MessageType context property.</span></span>  
  
6. <span data-ttu-id="fc2e0-139">La carga del puerto de envío envía el archivo XML que contiene la carga EDI a la aplicación de Contoso de back-end, representada por el \\_EDIXMLToContoso carpeta.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-139">The payload send port sends the XML file containing the EDI payload to the back-end Contoso application, represented by the \\_EDIXMLToContoso folder.</span></span> <span data-ttu-id="fc2e0-140">Este puerto de envío utiliza una canalización de envío PassThruTransmit.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-140">This send port uses a PassThruTransmit send pipeline.</span></span>  
  
7. <span data-ttu-id="fc2e0-141">El **Send_Async_MDN** puerto de envío dinámico recoge el MDN asíncrono del cuadro de mensajes, filtrando por la propiedad de contexto EdiIntAS.IsAS2AsynchronousMdn.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-141">The **Send_Async_MDN** dynamic send port picks up the asynchronous MDN from the MessageBox, filtering on the EdiIntAS.IsAS2AsynchronousMdn context property.</span></span>  
  
8. <span data-ttu-id="fc2e0-142">El MDN enviar puerto devuelve el MDN a la \\carpeta _MDNToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-142">The MDN send port returns the MDN to the \\_MDNToFabrikam folder.</span></span> <span data-ttu-id="fc2e0-143">Puesto que se trata de un puerto de envío dinámico, utilizará la dirección en la línea Receipt-Delivery-Option en el encabezado del mensaje (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) para enrutar el mensaje a la \\carpeta _MDNToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-143">Since this is a dynamic send port, it will use the address in the Receipt-Delivery-Option line in the header of the message (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) to route the message to the \\_MDNToFabrikam folder.</span></span>  
  
9. <span data-ttu-id="fc2e0-144">El **Send_Async_997** enviar puerto recoge el 997 del cuadro de mensajes, filtrando el BTS. Propiedad de contexto de MessageType.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-144">The **Send_Async_997** send port picks up the 997 from the MessageBox, filtering on the BTS.MessageType context property.</span></span>  
  
10. <span data-ttu-id="fc2e0-145">El 997 puerto de envío utilizará transporte HTTP para enviar el mensaje 997 generada por el EdiReceive canalización de recepción la \\carpeta _997ToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-145">The 997 send port uses HTTP transport to send the 997 message generated by the EdiReceive receive pipeline to the \\_997ToFabrikam folder.</span></span> <span data-ttu-id="fc2e0-146">El puerto de envío envía el mensaje a la página default.aspx de Fabrikam, usando el URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-146">The send port sends the message to the Fabrikam default.aspx page, using the URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**.</span></span> <span data-ttu-id="fc2e0-147">La página default.aspx, envía el 997 a la \\carpeta _997ToFabrikam.</span><span class="sxs-lookup"><span data-stu-id="fc2e0-147">The default.aspx page then sends the 997 to the \\_997ToFabrikam folder.</span></span>  
  
    <span data-ttu-id="fc2e0-148">Para hacer este tutorial, debe tener conocimientos acerca de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fc2e0-148">To do this tutorial, you should be knowledgeable about the following:</span></span>  
  
-   <span data-ttu-id="fc2e0-149">Componentes de canalizaciones y canalizaciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fc2e0-149">BizTalk Server pipelines and pipeline components</span></span>  
  
-   <span data-ttu-id="fc2e0-150">Adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="fc2e0-150">HTTP Adapter</span></span>  
  
-   <span data-ttu-id="fc2e0-151">Puertos y ubicaciones de recepción</span><span class="sxs-lookup"><span data-stu-id="fc2e0-151">Receive ports and locations</span></span>  
  
-   <span data-ttu-id="fc2e0-152">Los puertos de envío</span><span class="sxs-lookup"><span data-stu-id="fc2e0-152">Send ports</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc2e0-153">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fc2e0-153">In This Section</span></span>  
  
-   [<span data-ttu-id="fc2e0-154">Paso 1: Preparar el tutorial de AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-154">Step 1: Prepare for the AS2 Tutorial</span></span>](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [<span data-ttu-id="fc2e0-155">Paso 2: Crear e implementar el esquema X12 de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc2e0-155">Step 2: Create and Deploy the Sample X12 Schema</span></span>](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [<span data-ttu-id="fc2e0-156">Paso 3: Configurar un perfil de entidad y negocio para la organización</span><span class="sxs-lookup"><span data-stu-id="fc2e0-156">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [<span data-ttu-id="fc2e0-157">Paso 4: Configurar un perfil de entidad y negocio para el socio comercial</span><span class="sxs-lookup"><span data-stu-id="fc2e0-157">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [<span data-ttu-id="fc2e0-158">Paso 5: Configurar las páginas web de los socios comerciales</span><span class="sxs-lookup"><span data-stu-id="fc2e0-158">Step 5: Configure the Trading Partner Web Pages</span></span>](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [<span data-ttu-id="fc2e0-159">Paso 6: Configurar la ubicación de recepción EDI/AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-159">Step 6: Configure the EDI-AS2 Receive Location</span></span>](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [<span data-ttu-id="fc2e0-160">Paso 7: Configurar el puerto de envío MDN</span><span class="sxs-lookup"><span data-stu-id="fc2e0-160">Step 7: Configure the MDN Send Port</span></span>](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [<span data-ttu-id="fc2e0-161">Paso 8: Configurar el puerto de envío 997</span><span class="sxs-lookup"><span data-stu-id="fc2e0-161">Step 8: Configure the 997 Send Port</span></span>](../core/step-8-configure-the-997-send-port.md)  
  
-   [<span data-ttu-id="fc2e0-162">Paso 9: Configurar el puerto de envío de carga EDI</span><span class="sxs-lookup"><span data-stu-id="fc2e0-162">Step 9: Configure the EDI Payload Send Port</span></span>](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [<span data-ttu-id="fc2e0-163">Paso 10: Configurar el acuerdo entre socios comerciales X12 y AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-163">Step 10: Configure the X12 and AS2 Trading Partner Agreement</span></span>](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [<span data-ttu-id="fc2e0-164">Paso 11: Probar la solución AS2</span><span class="sxs-lookup"><span data-stu-id="fc2e0-164">Step 11: Test the AS2 Solution</span></span>](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="fc2e0-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc2e0-165">See Also</span></span>  
 [<span data-ttu-id="fc2e0-166">Tutoriales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="fc2e0-166">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)