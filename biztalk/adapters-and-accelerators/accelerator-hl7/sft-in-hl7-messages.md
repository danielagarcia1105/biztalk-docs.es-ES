---
title: SFT en mensajes HL7 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bf3ac5-8197-4ea3-ace8-ff59ac32313c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58cf1536d8619e47a9a33c77e4f95387e0ebb559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sft-in-hl7-messages"></a><span data-ttu-id="bb918-102">SFT en mensajes HL7</span><span class="sxs-lookup"><span data-stu-id="bb918-102">SFT in HL7 Messages</span></span>
[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]<span data-ttu-id="bb918-103">admite la adición de segmentos de software (SFT) a los mensajes.</span><span class="sxs-lookup"><span data-stu-id="bb918-103"> supports adding software segments (SFT) to messages.</span></span> <span data-ttu-id="bb918-104">Segmentos SFT proporcionan información adicional acerca de los productos de software que se utiliza como aplicaciones de envío.</span><span class="sxs-lookup"><span data-stu-id="bb918-104">SFT segments provide additional information about the software products used as sending applications.</span></span> <span data-ttu-id="bb918-105">Segmentos SFT se utilizan principalmente para diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="bb918-105">SFT segments are primarily used for diagnostics.</span></span> <span data-ttu-id="bb918-106">Como parte de la versión 2.5 de HL7 estándar, segmentos SFT se muestran en la confirmación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb918-106">As a part of the HL7 v2.5 standard, SFT segments are displayed in the application acknowledgement.</span></span>  
  
## <a name="message-instance-with-sft-segment"></a><span data-ttu-id="bb918-107">Instancia de mensaje con el segmento SFT</span><span class="sxs-lookup"><span data-stu-id="bb918-107">Message instance with SFT segment</span></span>  
 <span data-ttu-id="bb918-108">Utilice el procedimiento siguiente para crear un mensaje de ADT^A01.txt con un segmento SFT.</span><span class="sxs-lookup"><span data-stu-id="bb918-108">Use the following procedure to create an ADT^A01.txt message with an SFT segment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb918-109">Cuando se crea este mensaje en el Bloc de notas, elimine el después de la última línea retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="bb918-109">When you create this message in Notepad, delete the carriage return following the last line.</span></span>  
  
#### <a name="to-create-an-adta01txt-message-with-an-sft-segment"></a><span data-ttu-id="bb918-110">Para crear un mensaje de ADT^A01.txt con un segmento SFT</span><span class="sxs-lookup"><span data-stu-id="bb918-110">To create an ADT^A01.txt message with an SFT segment</span></span>  
  
1.  <span data-ttu-id="bb918-111">Abra el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bb918-111">Open Notepad.</span></span>  
  
2.  <span data-ttu-id="bb918-112">Copie el texto siguiente en el Bloc de notas:</span><span class="sxs-lookup"><span data-stu-id="bb918-112">Copy the following text into Notepad:</span></span>  
  
    ```  
    MSH|^~\&|Tutorial_ADTSystem|MCM|Tutorial_BatchDest||199112311501||  
    ADT^A01|000001|P|2.5|||AL|AL  
    SFT|ST^A^1^2^ISO^String&String&DNS^AM^String&String&DNS^P^String|  
    String|String|String|String|DTM^H  
    EVN|P12|DTM^D|DTM^H|01|ST^ST&ST&ST&ST&ST|DTM^H|Table^ST^DNS  
    PID||ST^ST^ISO|ST^ST^ISO|ST^ST^ISO|surname^prefix^own^spouse^partner  
    |surname^prefix^own^spouse^partner|DTM^H|A|  
    surname^prefix^own^spouse^partner|ST^ST^ACR^ST^ST^ACR|  
    address^street^number|countrycode|ST^ASN^BP|ST^ASN^BP|  
    ST^ST^ACR^ST^ST^ACR|||ST^ST^ISO|ST|ST^Table^DT|ST^ST^ISO||  
    ST|N|1|ST^ST^ACR^ST^ST^ACR|||DTM^H|N|N|US|DTM^H|Table^String^DNS|  
    ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|String|  
    ST^ST^ACR^ST^ST^ACR  
    PD1|C|A|||F|string|F|F|N||ST^ST^ACR^ST^ST^ACR|N|string||  
    ST^ST^ACR^ST^ST^ACR|A|string|string|USA|E1... E9|ACT  
    ROL||AD|ST^ST^ACR^ST^ST^ACR|ST^surname&prefix&own&partner&spouse|  
    DTM^H|DTM^H|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR  
    ^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR  
    PV1||B||A|ST^ST^ISO|||||CAR||ST|R|9|A9|ST||ST|ST^ST^ISO|ST^DTM&H|  
    ST|ST|ST|ST|ST|1|1|ST|ST|ST|ST|3|3|ST|ST|06||ST^ST^ACR^ST^ST^ACR|  
    ST|H|ST|||DTM^H|DTM^H||||||A  
    PV2||ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|  
    String|String|HO|DTM^H|DTM^H|1|1|string||string|N|D|string|CH|N|  
    1|F|N||AI|1|sttring|01|strhi|edwqed|ST^ST^ACR^ST^ST^ACR|jhgjk|N|  
    DTM^H|N|N|N|N|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|  
    ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|F|F|  
    ST^ST^ACR^ST^ST^ACR|jhklh|DTM^H|DTM^H|L  
    ROL||AD|ST^ST^ACR^ST^ST^ACR|ST^surname&prefix&own&partner&spouse|  
    DTM^H|DTM^H|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|  
    ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR  
    DB1|1|AP|ST^ST|N|string|string|string|string  
    OBX|1|AD|ST^ST^ACR^ST^ST^ACR|string|string|ST^ST^ACR^ST^ST^ACR|  
    string|AA|1|A|C|DTM^H|string|DTM^H|ST^ST^ACR^ST^ST^ACR||  
    ST^ST^ACR^ST^ST^ACR  
    AL1|1|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR||string|string  
    DG1|1|ST|ST^ST^ACR^ST^ST^ACR|ST|DTM^H|A|ST^ST^ACR^ST^ST^ACR|  
    ST^ST^ACR^ST^ST^ACR|N|ST|ST^ST^ACR^ST^ST^ACR||||1||R|N|DTM^H||A  
    DRG|ST^ST^ACR^ST^ST^ACR|DTM^H|N|ST|ST^ST^ACR^ST^ST^ACR|||C||N|E  
    PR1|1|ST|ST^ST^ACR^ST^ST^ACR|ST|DTM^H|A|||ST|1|||  
    ST^ST^ACR^ST^ST^ACR|0|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|1|  
    ST^ST^ACR^ST^ST^ACR||A  
    ROL||AD|ST^ST^ACR^ST^ST^ACR|ST^surname&prefix&own&partner&spouse|  
    DTM^H|DTM^H|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|  
    ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR  
    IN1|1|ST^ST^ACR^ST^ST^ACR|ST|||surname&prfix&own&partner&spouse|  
    ST^ASN^BP^ST^1^1^1^1^ST^ST^ST^ST|string||||string|string|  
    ST^DT^ST|string|surname&prefix&own&partner&spouse|  
    ST^ST^ACR^ST^ST^ACR|DTM^H||M|CO|string|N|string|N|string|_|  
    string|DTM^H||M|string|1|1|string  
    IN2||string||string|E|string|surname&prefix&own&partner&spouse|  
    string|surname&prefix&own&partner&spouse|string  
    IN3|1|||N||DTM^H|DTM^H||string|string  
    ROL||AD|ST^ST^ACR^ST^ST^ACR|ST^surname&prefix&own&partner&spouse|  
    DTM^H|DTM^H|ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR|  
    ST^ST^ACR^ST^ST^ACR|ST^ST^ACR^ST^ST^ACR  
    ACC|DTM^H|ST^ST^ACR^ST^ST^ACR|string|ST^ST^ACR^ST^ST^ACR|N|N||  
    string|string|N  
    UB1|1|1|1|1|1|1|string|1|1||1|ST^ST^ACR^ST^ST^ACR|  
    ST^ST^ACR^ST^ST^ACR|string|string||ST^ST^ACR^ST^ST^ACR|string|  
    string|string|string|string|string  
    UB2|1|string|string|string|string||||string|string|string|string|  
    string|string|string|string|1  
    PDA|ST^ST^ACR^ST^ST^ACR||N|DTM^H|  
    ST^surnamr&prefix&own&partner&spouse|N||  
    ST^surnamr&prefix&own&partner&spouse|N  
    ```  
  
3.  <span data-ttu-id="bb918-113">Guarde el archivo y, a continuación, cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="bb918-113">Save the file, and then close Notepad.</span></span>  
  
4.  <span data-ttu-id="bb918-114">Compruebe la carpeta de confirmación de la entidad de origen.</span><span class="sxs-lookup"><span data-stu-id="bb918-114">Check the Acknowledgement folder of the source party.</span></span>  
  
     <span data-ttu-id="bb918-115">La confirmación de cuerpo de este mensaje contiene los segmentos SFT del mensaje.</span><span class="sxs-lookup"><span data-stu-id="bb918-115">The body acknowledgement of this message contains the SFT segments of the message.</span></span> <span data-ttu-id="bb918-116">La confirmación para el mensaje anterior es:</span><span class="sxs-lookup"><span data-stu-id="bb918-116">The ACK for the above message is:</span></span>  
  
    ```  
    MSH|^~\&|Tutorial_BatchDest||Tutorial_ADTSystem|MCM|20070508175311||ACK^A01^ACK|000001|P|2.5|||AL  
    MSA|AA|000001  
    SFT|ST^A^1^2^ISO^String&String&DNS^AM^String&String&DNS^P^String|String|String|String|String|DTM^H  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bb918-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb918-117">See Also</span></span>  
 <span data-ttu-id="bb918-118">[Mensajería HL7](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md) </span><span class="sxs-lookup"><span data-stu-id="bb918-118">[HL7 Messaging](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md) </span></span>  
[<span data-ttu-id="bb918-119">Obtenga información sobre el Acelerador para HL7 y las herramientas de BizTalk disponibles</span><span class="sxs-lookup"><span data-stu-id="bb918-119">Learn the HL7 accelerator and the BizTalk tools available</span></span>](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)