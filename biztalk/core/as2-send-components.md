---
title: AS2 Componentes de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1dbee64dc2e3484e85e6d8e41ce31a77713ffec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231972"
---
# <a name="as2-send-components"></a><span data-ttu-id="ae420-102">Componentes de envío de AS2</span><span class="sxs-lookup"><span data-stu-id="ae420-102">AS2 Send Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ae420-103"> utiliza varios componentes para enviar mensajes AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-103"> uses several components to send AS2 messages.</span></span>  
  
## <a name="as2-send-pipelines"></a><span data-ttu-id="ae420-104">Canalizaciones de envío de AS2</span><span class="sxs-lookup"><span data-stu-id="ae420-104">AS2 Send Pipelines</span></span>  
 <span data-ttu-id="ae420-105">La mayor parte del procesamiento de envío de AS2 se realiza en las siguientes canalizaciones de envío de AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-105">Most AS2 send processing is performed in the following AS2 send pipelines.</span></span> <span data-ttu-id="ae420-106">Estas canalizaciones se instalan en `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` en \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components.</span><span class="sxs-lookup"><span data-stu-id="ae420-106">These pipelines are installed in `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae420-107">La canalización de envío de AS2 solo se admite en un proceso de Host de BizTalk de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="ae420-107">The AS2 Send pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="ae420-108">**Canalización AS2EDISend**</span><span class="sxs-lookup"><span data-stu-id="ae420-108">**AS2EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="ae420-109">Esta canalización genera y envía los mensajes EDI a través de AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-109">This pipeline generates and sends EDI messages over AS2.</span></span> <span data-ttu-id="ae420-110">La canalización consta de los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="ae420-110">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="ae420-111">Ensamblador EDI</span><span class="sxs-lookup"><span data-stu-id="ae420-111">EDI Assembler</span></span>  
  
-   <span data-ttu-id="ae420-112">Codificador AS2</span><span class="sxs-lookup"><span data-stu-id="ae420-112">AS2 Encoder</span></span>  
  
 <span data-ttu-id="ae420-113">Esta canalización no se usa para generar y enviar MDN a través de AS2, ya que el MDN no necesita que el ensamblador EDI lo procese.</span><span class="sxs-lookup"><span data-stu-id="ae420-113">This pipeline is not used to generate and send MDNs over AS2, because the MDN does not need to be processed by the EDI Assembler.</span></span> <span data-ttu-id="ae420-114">Use la canalización AS2Send para enviar MDN.</span><span class="sxs-lookup"><span data-stu-id="ae420-114">Use the AS2SendPipeline to send MDNs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae420-115">La ejecución de la canalización AS2EDISend desde una orquestación no está admitida.</span><span class="sxs-lookup"><span data-stu-id="ae420-115">Running the AS2EDISend pipeline from an orchestration is not supported.</span></span>  
  
 <span data-ttu-id="ae420-116">**Canalización AS2Send**</span><span class="sxs-lookup"><span data-stu-id="ae420-116">**AS2Send Pipeline**</span></span>  
  
 <span data-ttu-id="ae420-117">Esta canalización envía mensajes a través de AS2 cuando los mensajes no están codificados en EDI.</span><span class="sxs-lookup"><span data-stu-id="ae420-117">This pipeline sends messages over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="ae420-118">También envía MDN a través de AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-118">It also sends MDNs over AS2.</span></span> <span data-ttu-id="ae420-119">La canalización consta de los siguientes componentes de canalización:</span><span class="sxs-lookup"><span data-stu-id="ae420-119">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="ae420-120">Codificador AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-120">AS2 Encoder.</span></span>  
  
 <span data-ttu-id="ae420-121">Si los mensajes que van a enviarse a través de AS2 no son mensajes EDI ni XML, puede crear una canalización AS2Send personalizada para controlar estos mensajes.</span><span class="sxs-lookup"><span data-stu-id="ae420-121">If the messages to be sent over AS2 are neither EDI nor XML messages, you can create a customized AS2Send pipeline to handle these messages.</span></span> <span data-ttu-id="ae420-122">Esta canalización debe tener un ensamblador personalizado para convertir el XML intermedio de BizTalk Server a otro formato antes de codificar el mensaje en EDIINT/AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-122">This pipeline must have a customized assembler to convert the intermediate XML in BizTalk Server into the other format before encoding the message in EDIINT/AS2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae420-123">La ejecución de la canalización AS2Send desde una orquestación no está admitida.</span><span class="sxs-lookup"><span data-stu-id="ae420-123">Running the AS2Send pipeline from an orchestration is not supported.</span></span>  
  
## <a name="as2-send-pipeline-components"></a><span data-ttu-id="ae420-124">Componentes de la canalización de envío de AS2</span><span class="sxs-lookup"><span data-stu-id="ae420-124">AS2 Send Pipeline Components</span></span>  
 <span data-ttu-id="ae420-125">Las canalizaciones de envío de AS2 usan los siguientes componentes de canalización.</span><span class="sxs-lookup"><span data-stu-id="ae420-125">The AS2 send pipelines use the following pipeline components.</span></span> <span data-ttu-id="ae420-126">Estos componentes se instalan en `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` en \Program componentes de BizTalk Server 20xx\Pipeline\\.</span><span class="sxs-lookup"><span data-stu-id="ae420-126">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="ae420-127">**Ensamblador EDI**</span><span class="sxs-lookup"><span data-stu-id="ae420-127">**EDI Assembler**</span></span>  
  
 <span data-ttu-id="ae420-128">En las canalizaciones de envío de EDIINT, el ensamblador EDI serializa el intercambio EDI.</span><span class="sxs-lookup"><span data-stu-id="ae420-128">In the EDIINT send pipelines, the EDI Assembler serializes the EDI interchange.</span></span>  
  
 <span data-ttu-id="ae420-129">**Codificador AS2**</span><span class="sxs-lookup"><span data-stu-id="ae420-129">**AS2 Encoder**</span></span>  
  
 <span data-ttu-id="ae420-130">El codificador AS2 se incluye en la fase de codificación de las canalizaciones de envío AS2.</span><span class="sxs-lookup"><span data-stu-id="ae420-130">The AS2 Encoder is included in the encode stage of the AS2 send pipelines.</span></span> <span data-ttu-id="ae420-131">Usa el componente de canalización S/MIME de BizTalk para proporcionar la funcionalidad de codificación S/MIME a mensajes AS2 y MDN.</span><span class="sxs-lookup"><span data-stu-id="ae420-131">It uses the BizTalk S/MIME pipeline component to provide S/MIME encoding functionality to AS2 and MDN messages.</span></span> <span data-ttu-id="ae420-132">El codificador AS2 realiza las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ae420-132">The AS2 Encoder does the following:</span></span>  
  
-   <span data-ttu-id="ae420-133">Aplica encabezados AS2/HTTP.</span><span class="sxs-lookup"><span data-stu-id="ae420-133">Applies AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="ae420-134">Firma mensajes salientes, si esta opción está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ae420-134">Signs outgoing messages, if enabled</span></span>  
  
-   <span data-ttu-id="ae420-135">Cifra mensajes salientes, si esta opción está habilitada (para EDI/AS2, no MDN).</span><span class="sxs-lookup"><span data-stu-id="ae420-135">Encrypts outgoing messages, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="ae420-136">Comprime el mensaje saliente, si esta opción está habilitada (para EDI/AS2, no MDN).</span><span class="sxs-lookup"><span data-stu-id="ae420-136">Compresses the message, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="ae420-137">Almacena la carga en su formato correspondiente si la **NRR habilitado para mensajes AS2 salientes descodificados** propiedad está seleccionada y almacena el mensaje en su formato correspondiente si la **NRR habilitado para mensajes AS2 salientes codificados** propiedad está seleccionada</span><span class="sxs-lookup"><span data-stu-id="ae420-137">Stores the payload in wire format if the **NRR enabled for outbound decoded AS2 messages** property is selected, and stores the message in wire format if the **NRR enabled for outbound encoded AS2 messages** property is selected</span></span>  
  
-   <span data-ttu-id="ae420-138">Calcula el valor MIC y lo guarda en el almacén de datos</span><span class="sxs-lookup"><span data-stu-id="ae420-138">Computes the MIC value and stores it in the data store</span></span>  
  
-   <span data-ttu-id="ae420-139">Actualiza y correlaciona registros en la base de datos de recepción sin repudio.</span><span class="sxs-lookup"><span data-stu-id="ae420-139">Updates and correlates records in the non-repudiation receipt database</span></span>  
  
-   <span data-ttu-id="ae420-140">Para mensajes MDN, funciona igual que una canalización de paso a través: enruta el MDN generado por el descodificador AS2 en la canalización de recepción AS2Receive.</span><span class="sxs-lookup"><span data-stu-id="ae420-140">For MDN messages, acts as a passthrough pipeline, routing the MDN generated by the AS2 Decoder in the AS2Receive receive pipeline.</span></span> <span data-ttu-id="ae420-141">Si la configuración lo requiere, el codificador AS2 firmará el MDN.</span><span class="sxs-lookup"><span data-stu-id="ae420-141">If required by the configuration settings, the AS2 Encoder will sign the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ae420-142">En mensajes AS2, se usa la codificación de 8 bits.</span><span class="sxs-lookup"><span data-stu-id="ae420-142">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="ae420-143">La codificación Base64 solo se aplica a firmas en mensajes AS2 y MDN.</span><span class="sxs-lookup"><span data-stu-id="ae420-143">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="ae420-144">Adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="ae420-144">HTTP Adapter</span></span>  
 <span data-ttu-id="ae420-145">Los puertos de envío utilizados para el procesamiento de EDIINT AS2 utilizan el adaptador de HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae420-145">The send ports used for EDIINT AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="ae420-146">El adaptador de HTTP está configurado en la transmisión de petición-respuesta y en la unidireccional.</span><span class="sxs-lookup"><span data-stu-id="ae420-146">The HTTP Adapter is configured in both one-way and solicit-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="ae420-147">Base de datos sin repudio</span><span class="sxs-lookup"><span data-stu-id="ae420-147">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ae420-148"> usa la base de datos sin repudio (la tabla EdiMessageContent de la base de datos BizTalkDTADb) para realizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ae420-148"> uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae420-149">La tabla EdiMessageContent existe en la base de datos de BizTalkDTADb sólo si una de las propiedades del acuerdo de almacenamiento sin repudio está activada.</span><span class="sxs-lookup"><span data-stu-id="ae420-149">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties are checked.</span></span>  
  
-   <span data-ttu-id="ae420-150">Proporcionar una pista sin repudio para el MDN firmado.</span><span class="sxs-lookup"><span data-stu-id="ae420-150">Provide a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="ae420-151">Correlacionar un mensaje de salida con su MDN entrante.</span><span class="sxs-lookup"><span data-stu-id="ae420-151">Correlate an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="ae420-152">Almacenar mensajes a través de varios cambios de estado.</span><span class="sxs-lookup"><span data-stu-id="ae420-152">Store messages through various state changes</span></span>  
  
-   <span data-ttu-id="ae420-153">Asociar códigos de error con respuesta HTTP y MDN.</span><span class="sxs-lookup"><span data-stu-id="ae420-153">Associate error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="ae420-154">Mostrar registros en función de los criterios de filtro.</span><span class="sxs-lookup"><span data-stu-id="ae420-154">Display records based on filter criteria</span></span>  
  
-   <span data-ttu-id="ae420-155">Archivar registros marcados.</span><span class="sxs-lookup"><span data-stu-id="ae420-155">Archive marked records</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ae420-156">Para asegurarse de la autenticación e integridad de los mensajes almacenados en la base de datos sin repudio, pueden usarse firmas digitales en todos los mensajes que se van a almacenar en la base de datos, tanto los MDN como los mensajes AS2 originales.</span><span class="sxs-lookup"><span data-stu-id="ae420-156">To ensure authentication and integrity of messages stored in the non-repudiation database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="ae420-157">Para obtener más información, vea la sección 9.1 de [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span><span class="sxs-lookup"><span data-stu-id="ae420-157">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae420-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae420-158">See Also</span></span>  
 [<span data-ttu-id="ae420-159">Cómo BizTalk Server envía mensajes AS2</span><span class="sxs-lookup"><span data-stu-id="ae420-159">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)