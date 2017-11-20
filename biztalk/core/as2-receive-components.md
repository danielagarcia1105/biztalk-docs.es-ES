---
title: "AS2 Componentes de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c919a54a307a234237dd4086a0abf2a2c0c2fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="as2-receive-components"></a><span data-ttu-id="c220b-102">Componentes de recepción de AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-102">AS2 Receive Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c220b-103"> usa varios componentes para recibir mensajes AS2.</span><span class="sxs-lookup"><span data-stu-id="c220b-103"> uses several components to receive AS2 messages.</span></span>  
  
## <a name="as2-receive-pipelines"></a><span data-ttu-id="c220b-104">Canalizaciones de recepción AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-104">AS2 Receive Pipelines</span></span>  
 <span data-ttu-id="c220b-105">La mayor parte del procesamiento de recepción de AS2 se realiza en las siguientes canalizaciones de recepción de AS2.</span><span class="sxs-lookup"><span data-stu-id="c220b-105">Most AS2 receive processing is performed in the following AS2 receive pipelines.</span></span> <span data-ttu-id="c220b-106">Estas canalizaciones se instalan en `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` en \Program componentes de BizTalk Server 20xx\Pipeline\\.</span><span class="sxs-lookup"><span data-stu-id="c220b-106">These pipelines are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="c220b-107">**Canalización AS2EdiReceive**</span><span class="sxs-lookup"><span data-stu-id="c220b-107">**AS2EdiReceive Pipeline**</span></span>  
  
 <span data-ttu-id="c220b-108">Esta canalización procesa los mensajes EDI recibidos a través de AS2, que incluye los MDN.</span><span class="sxs-lookup"><span data-stu-id="c220b-108">This pipeline processes EDI messages received over AS2, including MDNs.</span></span> <span data-ttu-id="c220b-109">La canalización consta de los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="c220b-109">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="c220b-110">Descodificador AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-110">AS2 Decoder</span></span>  
  
-   <span data-ttu-id="c220b-111">Desensamblador EDI</span><span class="sxs-lookup"><span data-stu-id="c220b-111">EDI Disassembler</span></span>  
  
-   <span data-ttu-id="c220b-112">BatchMarker.</span><span class="sxs-lookup"><span data-stu-id="c220b-112">BatchMarker.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c220b-113">Cuando se utiliza la canalización AS2EdiReceive, debe agregar la cuenta de usuario que el proceso de instancia de host aislado de BizTalk esté ejecutando en el grupo de usuarios de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c220b-113">When using the AS2EdiReceive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="c220b-114">La canalización AS2EdiReceive se ejecuta en el proceso de instancia de host aislado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c220b-114">The AS2EdiReceive pipeline executes in the BizTalk Isolated Host Instance process.</span></span> <span data-ttu-id="c220b-115">La canalización AS2EdiReceive obtiene acceso al almacén de SSO, que requiere que el usuario se encuentre en el grupo de usuarios de la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c220b-115">The AS2EdiReceive pipeline accesses the SSO store, which requires that the user is in the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="c220b-116">**Canalización AS2Receive**</span><span class="sxs-lookup"><span data-stu-id="c220b-116">**AS2Receive Pipeline**</span></span>  
  
 <span data-ttu-id="c220b-117">Esta canalización procesa los mensajes recibidos a través de AS2 cuando los mensajes no están codificados en EDI.</span><span class="sxs-lookup"><span data-stu-id="c220b-117">This pipeline processes messages received over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="c220b-118">Estos mensajes se tratan como mensajes binarios.</span><span class="sxs-lookup"><span data-stu-id="c220b-118">These messages are treated as binary messages.</span></span> <span data-ttu-id="c220b-119">La canalización también procesa los MDN recibidos a través de AS2.</span><span class="sxs-lookup"><span data-stu-id="c220b-119">The pipeline also processes MDNs received over AS2.</span></span> <span data-ttu-id="c220b-120">La canalización consta de los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="c220b-120">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="c220b-121">Descodificador AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-121">AS2 Decoder</span></span>  
  
-   <span data-ttu-id="c220b-122">Desensamblador AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-122">AS2 Disassembler.</span></span>  
  
## <a name="as2-receive-pipeline-components"></a><span data-ttu-id="c220b-123">Componentes de la canalización de recepción AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-123">AS2 Receive Pipeline Components</span></span>  
 <span data-ttu-id="c220b-124">Las canalizaciones de recepción AS2 usan los siguientes componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="c220b-124">The AS2 receive pipelines use the following pipeline components.</span></span> <span data-ttu-id="c220b-125">Estos componentes se instalan en `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` en \Program componentes de BizTalk Server 20xx\Pipeline\\.</span><span class="sxs-lookup"><span data-stu-id="c220b-125">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c220b-126">La canalización de recepción AS2 solo se admite en un proceso de Host de BizTalk de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c220b-126">The AS2 Receive pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="c220b-127">**Descodificador de AS2**</span><span class="sxs-lookup"><span data-stu-id="c220b-127">**AS2 Decoder**</span></span>  
  
 <span data-ttu-id="c220b-128">El Descodificador AS2 se incluye en la fase de descodificación de las canalizaciones de recepción AS2EDIReceivePipeline y AS2Receive.</span><span class="sxs-lookup"><span data-stu-id="c220b-128">The AS2 Decoder is included in the decode stage of both the AS2EDIReceivePipeline and AS2Receive receive pipelines.</span></span> <span data-ttu-id="c220b-129">Usa el componente de canalización S/MIME de BizTalk para proporcionar la funcionalidad de descodificación S/MIME a mensajes AS2 y MDN.</span><span class="sxs-lookup"><span data-stu-id="c220b-129">It uses the BizTalk S/MIME Pipeline Component to provide S/MIME decoding functionality to AS2 and MDN messages.</span></span>  
  
-   <span data-ttu-id="c220b-130">Procesa encabezados AS2/HTTP.</span><span class="sxs-lookup"><span data-stu-id="c220b-130">Processes AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="c220b-131">Comprueba la firma en caso de que el mensaje estuviera firmado.</span><span class="sxs-lookup"><span data-stu-id="c220b-131">Verifies the signature, if the message was signed</span></span>  
  
-   <span data-ttu-id="c220b-132">Descifra los mensajes si estaban cifrados (para un mensaje EDI/AS2, no un MDN).</span><span class="sxs-lookup"><span data-stu-id="c220b-132">Decrypts the messages, if the message was encrypted (for an EDI/AS2 message, not an MDN)</span></span>  
  
-   <span data-ttu-id="c220b-133">Descomprime el mensaje si estaba comprimido.</span><span class="sxs-lookup"><span data-stu-id="c220b-133">Decompresses the message, if the message was compressed</span></span>  
  
-   <span data-ttu-id="c220b-134">Reconcilia un MDN recibido con el mensaje de salida original.</span><span class="sxs-lookup"><span data-stu-id="c220b-134">Reconciles a received MDN with the original outbound message</span></span>  
  
-   <span data-ttu-id="c220b-135">Actualiza y correlaciona registros en la base de datos sin repudio.</span><span class="sxs-lookup"><span data-stu-id="c220b-135">Updates and correlates records in the non-repudiation database</span></span>  
  
-   <span data-ttu-id="c220b-136">Escribe registros para los informes de estado de AS2.</span><span class="sxs-lookup"><span data-stu-id="c220b-136">Writes records for AS2 status reporting</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c220b-137">Si se produce un error durante el procesamiento de la recepción de un mensaje AS2, el descodificador AS2 detendrá el procesamiento inferior de los mensajes (por ejemplo, el desensamblador EDI no analizará el intercambio).</span><span class="sxs-lookup"><span data-stu-id="c220b-137">If an error occurs during receive-side processing of an AS2 message, the AS2 Decoder will stop further downstream message processing (for example, the EDI disassembler will not parse the interchange).</span></span> <span data-ttu-id="c220b-138">Sin embargo, el desensamblador AS2 o el desensamblador EDI seguirán generando el MDN.</span><span class="sxs-lookup"><span data-stu-id="c220b-138">However, the AS2 Disassembler or EDI Disassembler must still generate the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c220b-139">En mensajes AS2, se usa la codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="c220b-139">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="c220b-140">La codificación Base64 solo se aplica a firmas en mensajes AS2 y MDN.</span><span class="sxs-lookup"><span data-stu-id="c220b-140">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
 <span data-ttu-id="c220b-141">**Desensamblador AS2**</span><span class="sxs-lookup"><span data-stu-id="c220b-141">**AS2 Disassembler**</span></span>  
  
 <span data-ttu-id="c220b-142">En la canalización de recepción AS2Receive, el desensamblador AS2 lleva a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c220b-142">In the AS2Receive receive pipeline, the AS2 Disassembler does the following:</span></span>  
  
-   <span data-ttu-id="c220b-143">Determina si es necesario un MDN y si este debe ser sincrónico o asíncrono.</span><span class="sxs-lookup"><span data-stu-id="c220b-143">Determines whether an MDN is required, and whether the MDN should be synchronous or asynchronous.</span></span>  
  
-   <span data-ttu-id="c220b-144">Genera un MDN AS2.</span><span class="sxs-lookup"><span data-stu-id="c220b-144">Generates an AS2 MDN.</span></span>  
  
-   <span data-ttu-id="c220b-145">Si el MDN es sincrónico, establece la propiedad `EdiIntAS.IsAS2AsynchronousMDN` como False; si es asíncrono, establece la propiedad Async como True.</span><span class="sxs-lookup"><span data-stu-id="c220b-145">If the MDN is synchronous, sets the `EdiIntAS.IsAS2AsynchronousMDN` property to False; if asynchronous, sets the property to True.</span></span>  
  
-   <span data-ttu-id="c220b-146">Establece las propiedades y los tokens de correlación en el MDN.</span><span class="sxs-lookup"><span data-stu-id="c220b-146">Sets the correlation tokens and properties on the MDN.</span></span>  
  
 <span data-ttu-id="c220b-147">**Desensamblador EDI**</span><span class="sxs-lookup"><span data-stu-id="c220b-147">**EDI Disassembler**</span></span>  
  
 <span data-ttu-id="c220b-148">En AS2EDIReceivePipeline, el desensamblador EDI analizará el mensaje EDI en mensajes XML intermedios para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c220b-148">In the AS2EDIReceivePipeline, the EDI Disassembler will parse the EDI message into intermediate XML message(s) for processing.</span></span> <span data-ttu-id="c220b-149">Para obtener más información, consulte [cómo funciona el de desensamblador de EDI](../core/how-the-edi-disassembler-works.md).</span><span class="sxs-lookup"><span data-stu-id="c220b-149">For more information, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
 <span data-ttu-id="c220b-150">**BatchMarker**</span><span class="sxs-lookup"><span data-stu-id="c220b-150">**BatchMarker**</span></span>  
  
 <span data-ttu-id="c220b-151">En AS2EDIReceivePipeline, el componente de canalización BatchMarker establece las propiedades de contexto AgreementPartIdForSend y ToBeBatched que son necesarias para el procesamiento de un intercambio por lotes.</span><span class="sxs-lookup"><span data-stu-id="c220b-151">In the AS2EDIReceivePipeline, the BatchMarker pipeline component sets the AgreementPartIdForSend and ToBeBatched context properties that are required for processing a batched interchange.</span></span> <span data-ttu-id="c220b-152">Este componente se incluye en la última fase (resolución de acuerdos) de la canalización AS2EDIReceive.</span><span class="sxs-lookup"><span data-stu-id="c220b-152">This component is included in the last stage (agreement resolution) of the AS2EDIReceive pipeline.</span></span> <span data-ttu-id="c220b-153">Todas las canalizaciones que vayan a procesar por lotes los mensajes EDI deben incluir el componente de canalización BatchMarker.</span><span class="sxs-lookup"><span data-stu-id="c220b-153">All pipelines that will batch EDI messages should include the BatchMarker pipeline component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c220b-154">El componente de canalización BatchMarker no se incluye en la canalización AS2Receive usada para procesar mensajes que no son EDI.</span><span class="sxs-lookup"><span data-stu-id="c220b-154">The BatchMarker pipeline component is not included in the AS2Receive pipeline that is used to process non-EDI messages.</span></span> <span data-ttu-id="c220b-155">Sin embargo, puede incluir el componente BatchMarker en una canalización de recepción personalizada que no incluya el desensamblador EDI.</span><span class="sxs-lookup"><span data-stu-id="c220b-155">However, you can include the BatchMarker component in a custom receive pipeline that does not include the EDI Dissassembler.</span></span> <span data-ttu-id="c220b-156">Para obtener más información, vea "Procesamiento de EDI no mensajes en el componente de BatchMarker" en [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).</span><span class="sxs-lookup"><span data-stu-id="c220b-156">For more information, see "Processing Non-EDI Messages in the BatchMarker Component" in [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="c220b-157">Adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="c220b-157">HTTP Adapter</span></span>  
 <span data-ttu-id="c220b-158">Los puertos y las ubicaciones de recepción usadas para el procesamiento de AS2 usan el adaptador de HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c220b-158">The receive ports and locations used for AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="c220b-159">El adaptador de HTTP está configurado para la transmisión unidireccional y de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="c220b-159">The HTTP Adapter is configured for either one-way and request-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="c220b-160">Base de datos sin repudio</span><span class="sxs-lookup"><span data-stu-id="c220b-160">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c220b-161"> usa la base de datos sin repudio (la tabla EdiMessageContent de la base de datos BizTalkDTADb) para realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c220b-161"> uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c220b-162">La tabla EdiMessageContent se encuentra en la base de datos BizTalkDTADb solo si una de las propiedades de acuerdo de almacenamiento sin repudio está activada.</span><span class="sxs-lookup"><span data-stu-id="c220b-162">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties has been checked.</span></span>  
  
-   <span data-ttu-id="c220b-163">Proporciona una pista sin repudio para el MDN firmado.</span><span class="sxs-lookup"><span data-stu-id="c220b-163">Provides a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="c220b-164">Correlaciona un mensaje de salida con su MDN entrante.</span><span class="sxs-lookup"><span data-stu-id="c220b-164">Correlates an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="c220b-165">Almacena mensajes a través de varios cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="c220b-165">Stores messages through various state changes</span></span>  
  
-   <span data-ttu-id="c220b-166">Asocia códigos de error con respuesta HTTP y MDN.</span><span class="sxs-lookup"><span data-stu-id="c220b-166">Associates error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="c220b-167">Muestra registros en función de los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="c220b-167">Displays records based on filter criteria</span></span>  
  
-   <span data-ttu-id="c220b-168">Archiva registros marcados.</span><span class="sxs-lookup"><span data-stu-id="c220b-168">Archives marked records.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c220b-169">Para asegurarse de la autenticación e integridad de los mensajes almacenados en la base de datos de recepción sin repudio, deben usarse firmas digitales en todos los mensajes que se van a almacenar en la base de datos, tanto los MDN como los mensajes AS2 originales.</span><span class="sxs-lookup"><span data-stu-id="c220b-169">To ensure authentication and integrity of messages stored in the non-repudiation receipt database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="c220b-170">Para obtener más información, vea la sección 9.1 de [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span><span class="sxs-lookup"><span data-stu-id="c220b-170">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c220b-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="c220b-171">See Also</span></span>  
 [<span data-ttu-id="c220b-172">Cómo BizTalk Server recibe mensajes AS2</span><span class="sxs-lookup"><span data-stu-id="c220b-172">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)