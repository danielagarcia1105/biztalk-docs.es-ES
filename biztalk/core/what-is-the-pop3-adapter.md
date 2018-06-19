---
title: ¿Qué es el adaptador de POP3? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, availability
- authenticating, POP3 adapters
- POP3 adapters, data duplication
- data duplication
- POP3 adapters, receive adapters
- high availability, POP3 adapters
- POP3 adapters, supported platforms
- POP3 adapters, authenticating
- POP3 adapters, algorithims
- receive adapters, POP3 adapters
ms.assetid: 05e9598b-cdfe-4216-b6bf-1b84f8ddfeae
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592e0475b607de3f9df528a4bab777aa0fb7635d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290628"
---
# <a name="what-is-the-pop3-adapter"></a><span data-ttu-id="c8f82-103">¿Qué es el adaptador de POP3?</span><span class="sxs-lookup"><span data-stu-id="c8f82-103">What Is the POP3 Adapter?</span></span>
<span data-ttu-id="c8f82-104">Esta sección describe el adaptador de recepción POP3.</span><span class="sxs-lookup"><span data-stu-id="c8f82-104">This section describes the POP3 receive adapter.</span></span>  
  
## <a name="pop3-receive-adapter"></a><span data-ttu-id="c8f82-105">Adaptador de recepción POP3</span><span class="sxs-lookup"><span data-stu-id="c8f82-105">POP3 Receive Adapter</span></span>  
 <span data-ttu-id="c8f82-106">El adaptador de recepción POP3 permite mover los datos desde un buzón habilitado para POP3 al servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c8f82-106">The POP3 receive adapter enables you to move data from a POP3-enabled mailbox to BizTalk Server.</span></span>  
  
 <span data-ttu-id="c8f82-107">Las principales características del adaptador de recepción POP3 son:</span><span class="sxs-lookup"><span data-stu-id="c8f82-107">The key features of the POP3 receive adapter are:</span></span>  
  
-   <span data-ttu-id="c8f82-108">Extracción de archivos del buzón del servidor POP3 a petición.</span><span class="sxs-lookup"><span data-stu-id="c8f82-108">Pulling files from the POP3 server mailbox on demand.</span></span>  
  
-   <span data-ttu-id="c8f82-109">Ejecución de sondeos basados en una programación configurable.</span><span class="sxs-lookup"><span data-stu-id="c8f82-109">Running polls based on a configurable schedule.</span></span>  
  
-   <span data-ttu-id="c8f82-110">Realización de sondeos del buzón del servidor POP3 y envío de datos directamente al servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c8f82-110">Polling the POP3 server mailbox and sending data directly to BizTalk Server.</span></span>  
  
-   <span data-ttu-id="c8f82-111">Especificación del buzón del servidor POP3 como dirección IP o nombre de host o dirección IP, puerto, nombre de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="c8f82-111">Specifying the POP3 server mailbox as an IP address or host name, port, user name, and password.</span></span>  
  
-   <span data-ttu-id="c8f82-112">Capacidad para descargar el correo electrónico desde servidores de correo que requieren conexiones Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="c8f82-112">Ability to download e-mail from mail servers that require Secure Sockets Layer (SSL) connections.</span></span>  
  
-   <span data-ttu-id="c8f82-113">Entrega de archivos garantizada.</span><span class="sxs-lookup"><span data-stu-id="c8f82-113">Guaranteed file delivery.</span></span>  
  
-   <span data-ttu-id="c8f82-114">Procesamiento de MIME implícito.</span><span class="sxs-lookup"><span data-stu-id="c8f82-114">Implicit MIME processing.</span></span> <span data-ttu-id="c8f82-115">No resulta necesario utilizar un descodificador de MIME en una canalización de recepción al usar el adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="c8f82-115">It is not necessary to use a MIME decoder in a receive pipeline when using the POP3 adapter.</span></span>  
  
## <a name="pop3-adapter-supported-platforms"></a><span data-ttu-id="c8f82-116">Plataformas compatibles con el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c8f82-116">POP3 Adapter Supported Platforms</span></span>  
 <span data-ttu-id="c8f82-117">El adaptador de POP3 está diseñado para funcionar con cualquier servidor POP3 que se ajuste a las siguientes normas RFC:</span><span class="sxs-lookup"><span data-stu-id="c8f82-117">The POP3 adapter is designed to work with any POP3 servers that conform to the following RFCs:</span></span>  
  
-   <span data-ttu-id="c8f82-118">**RFC 1939.**</span><span class="sxs-lookup"><span data-stu-id="c8f82-118">**RFC 1939.**</span></span> <span data-ttu-id="c8f82-119">Post Office Protocol Version 3 (vea [http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))</span><span class="sxs-lookup"><span data-stu-id="c8f82-119">Post Office Protocol Version 3 (see [http://go.microsoft.com/fwlink/?LinkId=58808](http://go.microsoft.com/fwlink/?LinkId=58808))</span></span>  
  
-   <span data-ttu-id="c8f82-120">**RFC 1734.**</span><span class="sxs-lookup"><span data-stu-id="c8f82-120">**RFC 1734.**</span></span> <span data-ttu-id="c8f82-121">POP3 AUTHentication command (vea [http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))</span><span class="sxs-lookup"><span data-stu-id="c8f82-121">POP3 AUTHentication command (see [http://go.microsoft.com/fwlink/?LinkId=58809](http://go.microsoft.com/fwlink/?LinkId=58809))</span></span>  
  
-   <span data-ttu-id="c8f82-122">**RFC 2045.**</span><span class="sxs-lookup"><span data-stu-id="c8f82-122">**RFC 2045.**</span></span> <span data-ttu-id="c8f82-123">Multipurpose Internet Mail Extensions (MIME) Part One: Formato of Internet Message Bodies (vea [http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))</span><span class="sxs-lookup"><span data-stu-id="c8f82-123">Multipurpose Internet Mail Extensions (MIME) Part One: Format of Internet Message Bodies (see [http://go.microsoft.com/fwlink/?LinkId=58810](http://go.microsoft.com/fwlink/?LinkId=58810))</span></span>  
  
-   <span data-ttu-id="c8f82-124">**RFC 2046.**</span><span class="sxs-lookup"><span data-stu-id="c8f82-124">**RFC 2046.**</span></span> <span data-ttu-id="c8f82-125">Multipurpose Internet Mail Extensions (MIME) parte dos: Tipos de medios (vea [http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))</span><span class="sxs-lookup"><span data-stu-id="c8f82-125">Multipurpose Internet Mail Extensions (MIME) Part Two: Media Types (see [http://go.microsoft.com/fwlink/?LinkId=58811](http://go.microsoft.com/fwlink/?LinkId=58811))</span></span>  
  
-   <span data-ttu-id="c8f82-126">**RFC 2047.**</span><span class="sxs-lookup"><span data-stu-id="c8f82-126">**RFC 2047.**</span></span> <span data-ttu-id="c8f82-127">MIME (Multipurpose Internet Mail Extensions) parte tres: Extensiones de encabezado de mensaje de texto no ASCII (vea [http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))</span><span class="sxs-lookup"><span data-stu-id="c8f82-127">MIME (Multipurpose Internet Mail Extensions) Part Three: Message Header Extensions for Non-ASCII Text (see [http://go.microsoft.com/fwlink/?LinkId=58812](http://go.microsoft.com/fwlink/?LinkId=58812))</span></span>  
  
 <span data-ttu-id="c8f82-128">Se realizaron pruebas exhaustivas del adaptador de POP3 con respecto a Microsoft Exchange Server 2003.</span><span class="sxs-lookup"><span data-stu-id="c8f82-128">The POP3 adapter was tested extensively against Microsoft Exchange Server 2003.</span></span>  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a><span data-ttu-id="c8f82-129">Consideraciones para evitar el duplicado de datos al utilizar el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c8f82-129">Considerations for Preventing Data Duplication When Using the POP3 Adapter</span></span>  
 <span data-ttu-id="c8f82-130">El adaptador de POP3 no es un adaptador transaccional y, en consecuencia, está sujeto al procesamiento de varias copias de un mismo mensaje, lo que puede dar lugar al duplicado de datos.</span><span class="sxs-lookup"><span data-stu-id="c8f82-130">The POP3 adapter is not a transactional adapter and therefore is subject to processing multiple copies of the same message, potentially causing data duplication.</span></span> <span data-ttu-id="c8f82-131">Es posible que el adaptador de POP3 entregue copias duplicadas de un mensaje en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="c8f82-131">It is possible that the POP3 adapter will deliver duplicate copies of a message in the following scenarios:</span></span>  
  
-   <span data-ttu-id="c8f82-132">El adaptador de POP3 siempre elimina mensajes de correo electrónico del buzón para cuya supervisión está configurado tras enviar correctamente el mensaje de correo electrónico al servidor BizTalk Server para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c8f82-132">The POP3 adapter always deletes e-mails from the mailbox that it is configured to monitor after the e-mail has been successfully submitted to BizTalk Server for processing.</span></span> <span data-ttu-id="c8f82-133">Si el adaptador de POP3 recupera un mensaje de correo electrónico del buzón, lo envía al servidor BizTalk Server para su procesamiento y no logra eliminar el mensaje de correo electrónico del buzón, el mensaje se reenviará al servidor BizTalk Server la próxima vez que el adaptador de POP3 efectúe un sondeo del buzón.</span><span class="sxs-lookup"><span data-stu-id="c8f82-133">If the POP3 adapter retrieves an e-mail from a mailbox, submits the e-mail to BizTalk Server for processing, and fails to delete the e-mail from the mailbox, the e-mail will be resubmitted to BizTalk Server the next time that the POP3 adapter polls the mailbox.</span></span>  
  
-   <span data-ttu-id="c8f82-134">Si varias instancias del adaptador de POP3 de distintas instancias de host de BizTalk supervisan el mismo buzón de forma simultánea y el servidor POP3 permite varias conexiones concurrentes a los buzones correspondientes, el adaptador puede entregar copias duplicadas de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c8f82-134">If multiple instances of the POP3 adapter in separate BizTalk Host instances are monitoring the same mailbox simultaneously and the POP3 server allows multiple concurrent connections to its mailboxes, then the adapter may deliver duplicate copies of messages.</span></span>  
  
## <a name="high-availability-for-the-pop3-adapter"></a><span data-ttu-id="c8f82-135">Alta disponibilidad del adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c8f82-135">High Availability for the POP3 Adapter</span></span>  
 <span data-ttu-id="c8f82-136">Algunos servidores POP3 permiten varias conexiones concurrentes a un buzón dado.</span><span class="sxs-lookup"><span data-stu-id="c8f82-136">Some POP3 servers permit multiple concurrent connections to a given mailbox.</span></span> <span data-ttu-id="c8f82-137">Si más de una instancia del adaptador de POP3 está configurada para recuperar correo de un buzón de un servidor POP3 de este tipo, se pueden duplicar los datos.</span><span class="sxs-lookup"><span data-stu-id="c8f82-137">If more than one instance of the POP3 adapter is configured to retrieve mail from a mailbox on such a POP3 server then data duplication can occur.</span></span> <span data-ttu-id="c8f82-138">Por lo tanto, se debería configurar únicamente una instancia del adaptador de POP3 para recuperar el correo de un buzón que permite varias conexiones concurrentes.</span><span class="sxs-lookup"><span data-stu-id="c8f82-138">Therefore you should configure only one instance of the POP3 adapter to retrieve mail from a mailbox that permits multiple concurrent connections.</span></span>  
  
 <span data-ttu-id="c8f82-139">Para proporcionar tolerancia a errores para el adaptador de POP3 en este caso, se debería configurar un solo controlador de recepción del adaptador de POP3 para que se ejecutase en un host de BizTalk agrupado.</span><span class="sxs-lookup"><span data-stu-id="c8f82-139">To provide fault tolerance for the POP3 adapter in this scenario, a single POP3 adapter receive handler should be configured to run in a clustered BizTalk Host.</span></span> <span data-ttu-id="c8f82-140">Para obtener más información, consulte [consideraciones para ejecutar controladores de adaptador dentro de un Host en clúster](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span><span class="sxs-lookup"><span data-stu-id="c8f82-140">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a><span data-ttu-id="c8f82-141">Advertencias de autenticación cuando al conectarse varias instancias del adaptador de POP3 al mismo buzón</span><span class="sxs-lookup"><span data-stu-id="c8f82-141">Authentication Warnings When Multiple Instances of the POP3 Adapter Connect to the Same Mailbox</span></span>  
 <span data-ttu-id="c8f82-142">BizTalk Server puede configurarse para que más de una instancia del adaptador de POP3 recupere correo del mismo buzón.</span><span class="sxs-lookup"><span data-stu-id="c8f82-142">BizTalk Server may be configured to have more than one instance of the POP3 adapter retrieve mail from the same mailbox.</span></span> <span data-ttu-id="c8f82-143">En este caso, es posible que se generen advertencias de autenticación en el registro de aplicaciones de BizTalk Server a causa del mecanismo de bloqueo que emplean algunos servidores POP3.</span><span class="sxs-lookup"><span data-stu-id="c8f82-143">In such a case, it is possible that authentication warnings may be generated in the BizTalk Server Application log because of the locking mechanism employed by some POP3 servers.</span></span> <span data-ttu-id="c8f82-144">Estas advertencias no afectarán a la funcionalidad del adaptador de POP3 y puede omitirse sin riesgos en este caso.</span><span class="sxs-lookup"><span data-stu-id="c8f82-144">These warnings will have no impact on the POP3 adapter functionality and can be safely ignored in this scenario.</span></span>  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a><span data-ttu-id="c8f82-145">Los mensajes cifrados que recibe el adaptador de POP3, enviados a la cola de suspensión, pueden visualizarse como texto no cifrado</span><span class="sxs-lookup"><span data-stu-id="c8f82-145">Encrypted Messages Received by the POP3 Adapter that are sent to the Suspended Queue may be Viewable in Clear Text</span></span>  
 <span data-ttu-id="c8f82-146">El adaptador de POP3 puede configurarse para descifrar mensajes de correo electrónico cifrados digitalmente.</span><span class="sxs-lookup"><span data-stu-id="c8f82-146">You can configure the POP3 adapter to decrypt digitally encrypted e-mails.</span></span> <span data-ttu-id="c8f82-147">Esto se hace estableciendo el **aplicar descodificación MIME** propiedad **True** para ubicaciones de recepción que utilice POP3 el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c8f82-147">This is done by setting the **Apply MIME Decoding** property to **True** for receive locations that use the POP3 adapter.</span></span> <span data-ttu-id="c8f82-148">Si el adaptador de POP3 recibe un correo electrónico cifrado digitalmente y la **aplicar descodificación MIME** propiedad para la ubicación de recepción se establece en **True** , a continuación, el adaptador de POP3 intenta descifrar el correo electrónico como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="c8f82-148">If the POP3 Adapter receives a digitally encrypted e-mail and the **Apply MIME Decoding** property for the receive location is set to **True** then the POP3 adapter attempts to decrypt the e-mail as follows:</span></span>  
  
-   <span data-ttu-id="c8f82-149">El adaptador de POP3 busca un certificado privado que coincida con el certificado público utilizado para cifrar el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c8f82-149">The POP3 Adapter searches for a private certificate that matches the public certificate used to encrypt the e-mail.</span></span> <span data-ttu-id="c8f82-150">El certificado privado debe encontrarse en el almacén de certificados Personal del servidor que ejecuta la instancia de host a la que el controlador de recepción POP3 se encuentra enlazado.</span><span class="sxs-lookup"><span data-stu-id="c8f82-150">The private certificate must be in the Personal certificate store of the server that is running the host instance that the POP3 receive handler is bound to.</span></span>  
  
-   <span data-ttu-id="c8f82-151">Si el adaptador de POP3 encuentra un certificado privado correspondiente, lo utiliza para descifrar el mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c8f82-151">If the POP3 Adapter locates a corresponding private certificate, it uses the private certificate to decrypt the e-mail message.</span></span>  
  
-   <span data-ttu-id="c8f82-152">El mensaje de correo electrónico se descifra y se almacena en el cuadro de mensajes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c8f82-152">The e-mail is decrypted and persisted to the BizTalk MessageBox.</span></span>  
  
 <span data-ttu-id="c8f82-153">Si un mensaje se suspende después de que se descifre y se almacene en el cuadro de mensajes de BizTalk, el contenido del mensaje resultará visible como texto no cifrado en la cola de suspensión de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c8f82-153">If a message is suspended after being decrypted and persisted to the BizTalk MessageBox, the contents of the message will be visible in clear text in the BizTalk suspended queue.</span></span>  
  
 <span data-ttu-id="c8f82-154">Si es preciso evitar la visualización del texto de un mensaje seguro en la cola de suspensión, siga los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="c8f82-154">If you need to prevent the display of secure message text in the suspended queue, follow these steps:</span></span>  
  
-   <span data-ttu-id="c8f82-155">Establecer el **aplicar descodificación MIME** propiedad **False** para dicho adaptador de POP3 de uso de ubicaciones de recepción y descifrar el mensaje en una canalización con el componente de canalización SMIME.</span><span class="sxs-lookup"><span data-stu-id="c8f82-155">Set the **Apply MIME Decoding** property to **False** for receive locations that use the POP3 adapter and decrypt the message in a pipeline with the SMIME pipeline component.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8f82-156">Con ello, se evitará la posibilidad de promover propiedades específicas de correo electrónico al contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="c8f82-156">This approach will prevent you from being able to promote e-mail specific properties to the message context.</span></span>  
  
-   <span data-ttu-id="c8f82-157">Si resulta necesario promocionar propiedades específicas de correo electrónico al contexto de mensaje y garantizar que los mensajes cifrados sigan cifrados al enrutarse a la cola de suspensión, lleve a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8f82-157">If you need to promote e-mail specific properties to the message context and ensure that encrypted messages remain encrypted if they are routed to the suspended queue, follow these steps:</span></span>  
  
    -   <span data-ttu-id="c8f82-158">Active la opción para **habilitar enrutamiento para mensajes con errores** en el puerto de recepción que aloja las ubicaciones de recepción que utilizan el adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="c8f82-158">Check the option to **Enable routing for failed messages** on the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
    -   <span data-ttu-id="c8f82-159">Cree una orquestación para efectuar una suscripción a mensajes con errores de entrega al puerto de recepción que aloja las ubicaciones de recepción que utilizan el adaptador de POP3.</span><span class="sxs-lookup"><span data-stu-id="c8f82-159">Create an orchestration to subscribe to messages that fail delivery to the receive port that houses the receive location(s) that use the POP3 adapter.</span></span>  
  
    -   <span data-ttu-id="c8f82-160">Configure la orquestación con un puerto de envío que cifre el mensaje en una canalización mediante el componente de canalización de SMIME.</span><span class="sxs-lookup"><span data-stu-id="c8f82-160">Configure the orchestration with a send port that encrypts the message in a pipeline using the SMIME pipeline component.</span></span>  
  
    -   <span data-ttu-id="c8f82-161">Configure la orquestación con una forma de suspensión para suspender la instancia de orquestación y el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c8f82-161">Configure the orchestration with a suspend shape to suspend the orchestration instance and the message.</span></span>  
  
    -   <span data-ttu-id="c8f82-162">Genere la orquestación e impleméntela; seguidamente, enlace la orquestación implementada al puerto de recepción adecuado.</span><span class="sxs-lookup"><span data-stu-id="c8f82-162">Build and deploy the orchestration, bind the deployed orchestration to the appropriate receive port.</span></span>  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a><span data-ttu-id="c8f82-163">Tamaño máximo de mensajes compatible con el adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c8f82-163">Maximum Message Size Supported by the POP3 Adapter</span></span>  
 <span data-ttu-id="c8f82-164">Se han efectuado pruebas con el adaptador de POP3 que permiten afirmar la compatibilidad con la recepción de mensajes de hasta 50 MB de tamaño.</span><span class="sxs-lookup"><span data-stu-id="c8f82-164">The POP3 adapter has been tested with and supports receiving messages up to 50 MB in size.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f82-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f82-165">See Also</span></span>  
 [<span data-ttu-id="c8f82-166">Adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="c8f82-166">POP3 Adapter</span></span>](../core/pop3-adapter.md)