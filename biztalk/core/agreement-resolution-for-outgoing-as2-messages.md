---
title: "Resolución del acuerdo para mensajes AS2 salientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 578d7565-534c-4c13-b473-975f347f3a9b
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cf35a15ca7d0e27ba0c2bf1a05781d6512e0bef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="agreement-resolution-for-outgoing-as2-messages"></a><span data-ttu-id="91d40-102">Resolución del acuerdo para mensajes AS2 salientes</span><span class="sxs-lookup"><span data-stu-id="91d40-102">Agreement Resolution for Outgoing AS2 Messages</span></span>
<span data-ttu-id="91d40-103">Si una canalización de envío AS2 procesa un mensaje codificado con EDIINT/AS2 saliente a través del transporte HTTP/HTTPS, determina el acuerdo que resolverá el mensaje.</span><span class="sxs-lookup"><span data-stu-id="91d40-103">When an AS2 send pipeline processes an outgoing EDIINT/AS2-encoded message over HTTP/HTTPS transport, it determines the agreement that the message will resolve to.</span></span> <span data-ttu-id="91d40-104">Utilizará dichas propiedades de acuerdo para procesar el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="91d40-104">It will then use those agreement properties to process the outgoing message.</span></span> <span data-ttu-id="91d40-105">La canalización de envío usará los siguientes criterios para determinar el acuerdo (en orden de prioridad):</span><span class="sxs-lookup"><span data-stu-id="91d40-105">The send pipeline will use the following criteria to determine the agreement (in order of priority):</span></span>  
  
1.  <span data-ttu-id="91d40-106">La canalización de envío intenta establecer una correspondencia entre las propiedades AS2From y AS2To del contexto y los valores de AS2From y AS2To especificados como parte de las propiedades del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="91d40-106">The send pipeline attempts to match the AS2From and AS2To context properties with the values of AS2From and AS2To specified as part of the agreement properties.</span></span>  
  
2.  <span data-ttu-id="91d40-107">Si se produce un error en el paso anterior, la canalización de envío intentará hacer coincidir la propiedad de contexto AS2To del mensaje saliente con el valor de la propiedad AS2To, que se ha establecido como resolución de acuerdo adicional en el **identificadores** ficha del acuerdo Propiedades.</span><span class="sxs-lookup"><span data-stu-id="91d40-107">If the previous step fails, the send pipeline will attempt to match the AS2To context property of the outbound message with the value of AS2To property, which is set as additional agreement resolver in the **Identifiers** tab of agreement properties.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="91d40-108"> no escribe la propiedad AS2To en el contexto.</span><span class="sxs-lookup"><span data-stu-id="91d40-108"> does not write the AS2To property to the context.</span></span> <span data-ttu-id="91d40-109">Si desea realizar la resolución del acuerdo en la propiedad de contexto AS2To, deberá incorporar una orquestación personalizada o un componente de canalización personalizado para ello.</span><span class="sxs-lookup"><span data-stu-id="91d40-109">If you want to perform agreement resolution on the AS2To context property, you will have to incorporate a custom orchestration or a custom pipeline component to do so.</span></span> <span data-ttu-id="91d40-110">Para obtener más información, consulte [propiedades de contexto de AS2 de escritura para la resolución de entidades salientes](../core/writing-as2-context-properties-for-outbound-party-resolution.md).</span><span class="sxs-lookup"><span data-stu-id="91d40-110">For more information, see [Writing AS2 Context Properties for Outbound Party Resolution](../core/writing-as2-context-properties-for-outbound-party-resolution.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91d40-111">Si está utilizando un puerto de envío dinámico, la propiedad AS2To se debe escribir en el contexto de la resolución del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="91d40-111">When you are using a dynamic send port, the AS2To property must be written to the context for agreement resolution.</span></span>  
  
3.  <span data-ttu-id="91d40-112">Si se produce un error en el paso anterior, la canalización de envío tratará de establecer una correspondencia entre el puerto de envío asociado al acuerdo y el puerto de envío que se ha suscrito al mensaje.</span><span class="sxs-lookup"><span data-stu-id="91d40-112">If the previous step fails, the send pipeline will attempt to match the send port that is associated with an agreement with the send port that subscribed to the message.</span></span> <span data-ttu-id="91d40-113">El puerto de envío está asociado con el acuerdo en el **puertos de envío** página del acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="91d40-113">The send port is associated with the agreement in the **Send Ports** page of the one-way AS2 agreement of the **Agreement Properties** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91d40-114">A diferencia del procesamiento EDI, no existen propiedades AS2 de reserva que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueda usar en caso de que no pueda determinar el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="91d40-114">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span> <span data-ttu-id="91d40-115">Sin embargo, hay un acuerdo predeterminado que se usa para enviar un MDN.</span><span class="sxs-lookup"><span data-stu-id="91d40-115">There is, however, a default agreement used to send an MDN.</span></span> <span data-ttu-id="91d40-116">Además, ni el puerto de envío ni la propiedad de contexto Http.UserHttpHeaders se usan para resolver el acuerdo de un MDN.</span><span class="sxs-lookup"><span data-stu-id="91d40-116">In addition, neither the send port nor the Http.UserHttpHeaders context property is used to resolve the agreement for an MDN.</span></span> <span data-ttu-id="91d40-117">Para obtener más información, vea la sección "Acuerdo resolución para un MDN" de [enviar un MDN saliente](../core/sending-an-outgoing-mdn.md).</span><span class="sxs-lookup"><span data-stu-id="91d40-117">For more information, see the "Agreement Resolution for an MDN" section of [Sending an Outgoing MDN](../core/sending-an-outgoing-mdn.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91d40-118">Si AS2-a propiedades de acuerdo en el **identificadores** página del acuerdo AS2 unidireccional de la **propiedades del acuerdo de** cuadro de diálogo se establece de forma predeterminada para un nombre de entidad en inglés y el valor de AS2-al encabezado de AS2 mensajes se establece en un nombre no está en inglés, a continuación, no se encontrará la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="91d40-118">If the AS2-To agreement property in the **Identifiers** page of the one-way AS2 agreement of the **Agreement Properties** dialog box is set by default to an English party name, and the value in the AS2-To header of the AS2 message is set to a non-English name, then the match will not be found.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91d40-119">Al enviar EDI sobre AS2, es necesario utilizar acuerdos independientes para EDI y AS2.</span><span class="sxs-lookup"><span data-stu-id="91d40-119">When sending EDI over AS2, you are required to use separate agreements for both EDI and AS2.</span></span>  
  
 <span data-ttu-id="91d40-120">Para obtener más detalles sobre el proceso de envío, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).</span><span class="sxs-lookup"><span data-stu-id="91d40-120">For more details on the send process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d40-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="91d40-121">See Also</span></span>  
 [<span data-ttu-id="91d40-122">Cómo BizTalk Server envía mensajes AS2</span><span class="sxs-lookup"><span data-stu-id="91d40-122">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)