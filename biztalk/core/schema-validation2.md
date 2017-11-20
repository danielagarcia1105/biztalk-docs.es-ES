---
title: Esquema Validation2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 317fa8e0e5e557993922bba383ebf5eca460fa69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-validation"></a><span data-ttu-id="6a954-102">Validación de esquemas</span><span class="sxs-lookup"><span data-stu-id="6a954-102">Schema Validation</span></span>
<span data-ttu-id="6a954-103">La canalización de recepción EDI y la canalización de envío EDI validan un mensaje usando los siguientes esquemas:</span><span class="sxs-lookup"><span data-stu-id="6a954-103">The EDI receive pipeline and EDI send pipeline validate a message using the following schemas:</span></span>  
  
-   <span data-ttu-id="6a954-104">**Validación de sobres**: esquema de servicio en `Microsoft.BizTalk.Edi.BaseArtifacts.dll` en[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a954-104">**Envelope validation**: Service schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span></span>  
  
-   <span data-ttu-id="6a954-105">**Validación del conjunto de transacciones**: esquemas de mensaje en el esquema de almacenamiento en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span><span class="sxs-lookup"><span data-stu-id="6a954-105">**Transaction set validation**: Message schemas in the schema store in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span></span>  
  
-   <span data-ttu-id="6a954-106">**Validación del mensaje de confirmación**: CONTRL, 997 y TA1 esquema en `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.</span><span class="sxs-lookup"><span data-stu-id="6a954-106">**Acknowledgment message validation**: CONTRL, 997, and TA1 schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.</span></span>  
  
 <span data-ttu-id="6a954-107">El programa de instalación implementa automáticamente los esquemas de `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.</span><span class="sxs-lookup"><span data-stu-id="6a954-107">The schemas in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` are automatically deployed by the setup program.</span></span> <span data-ttu-id="6a954-108">Estos esquemas se enumeran en la **esquemas** nodo de la **aplicación EDI de BizTalk** en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="6a954-108">These schemas are listed in the **Schemas** node of the **BizTalk EDI Application** in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="6a954-109">Para utilizar los esquemas del mensaje, debe instalarlos en el disco duro del servidor ejecutando el archivo autoextraíble MicrosoftEdiXSDTemplates.exe de la carpeta [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI y, a continuación, implementarlos en su proyecto en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a954-109">To use the message schemas, you must install them on the hard drive of your server by executing the MicrosoftEdiXSDTemplates.exe self-extracting file in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder, and then deploy them in your project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6a954-110">**Determinación de esquemas**</span><span class="sxs-lookup"><span data-stu-id="6a954-110">**Schema Determination**</span></span>  
  
 <span data-ttu-id="6a954-111">Cuando la canalización de recepción EDI procesa un mensaje de recepción, determina el espacio de nombres del esquema que va a usarse en el procesamiento del mensaje a través del proceso de búsqueda del acuerdo y de detección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="6a954-111">When the EDI receive pipeline processes a receive message, it determines the namespace of the schema to use in processing the message through the agreement lookup and schema discovery process.</span></span> <span data-ttu-id="6a954-112">Para obtener más información, consulte [resolución de acuerdos, detección de esquemas y autorización para los mensajes de EDI recibidos](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span><span class="sxs-lookup"><span data-stu-id="6a954-112">For more information, see [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
 <span data-ttu-id="6a954-113">Cuando la canalización de envío EDI crea un mensaje para enviarlo, usa las propiedades del acuerdo para rellenar el sobre y, después, realiza la validación de esquema de la información del conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="6a954-113">When the EDI send pipeline creates a message to send, it uses agreement properties to populate the envelope, and then performs schema validation of the information in the transaction set.</span></span> <span data-ttu-id="6a954-114">Tras cargar el esquema, la canalización de envío valida el esquema con respecto a las propiedades del acuerdo (o del acuerdo de reserva si no se ha designado ningún acuerdo).</span><span class="sxs-lookup"><span data-stu-id="6a954-114">After loading the schema, the send pipeline validates the schema against agreement properties (or fallback agreement if no agreement has been designated).</span></span> <span data-ttu-id="6a954-115">Si el esquema se valida, la canalización valida el conjunto de transacciones en relación con el esquema.</span><span class="sxs-lookup"><span data-stu-id="6a954-115">If the schema validates, the pipeline validates the transaction set against the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a954-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a954-116">See Also</span></span>  
 [<span data-ttu-id="6a954-117">Validación del mensaje EDI</span><span class="sxs-lookup"><span data-stu-id="6a954-117">EDI Message Validation</span></span>](../core/edi-message-validation.md)