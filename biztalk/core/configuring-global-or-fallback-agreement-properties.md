---
title: Configurar propiedades del acuerdo de reserva o globales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb693a17cad17eadaf0d005d12075dde30daa33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233212"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a><span data-ttu-id="67e55-102">Configuración de las propiedades de acuerdos globales o de respaldo</span><span class="sxs-lookup"><span data-stu-id="67e55-102">Configuring Global or Fallback Agreement Properties</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="67e55-103"> usa propiedades de acuerdo de reserva para procesar un mensaje si no descubre un acuerdo que resolver durante un intercambio.</span><span class="sxs-lookup"><span data-stu-id="67e55-103"> uses fallback agreement properties to process a message when it does not discover an agreement to resolve to for an interchange.</span></span> <span data-ttu-id="67e55-104">Las propiedades del acuerdo de reserva no se usan cuando el acuerdo es conocido y no se aplica a ningún acuerdo.</span><span class="sxs-lookup"><span data-stu-id="67e55-104">Fallback agreement properties are not used when the agreement is known, and do not apply to any or all agreements.</span></span>  
  
 <span data-ttu-id="67e55-105">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje, intenta hacer coincidir la información del remitente para un acuerdo con la información del remitente en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="67e55-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives a message, it attempts to match the sender information for an agreement with the sender information in the message.</span></span> <span data-ttu-id="67e55-106">La información del remitente se encuentra en los elementos de datos ISA5 e ISA6 para mensajes X12 y en los elementos de datos UNB2.1 y UNB 2.2 para EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="67e55-106">The sender information is in the ISA5 and ISA6 data elements for X12 message, and the UNB2.1 and UNB 2.2 data elements for EDIFACT.</span></span> <span data-ttu-id="67e55-107">La información del contrato está en las pestañas identificador en la pestaña del acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="67e55-107">The agreement information is in the Identifier tabs in the one-way agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="67e55-108">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no descubre el acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará las propiedades del acuerdo de reserva para determinar el espacio de nombres, procesar el mensaje y enviar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="67e55-108">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not discover the agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to determine the namespace, process the message, and send any acknowledgments.</span></span>  
  
 <span data-ttu-id="67e55-109">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envía un mensaje, la canalización de envío de EDI determina el acuerdo que el mensaje resuelve mediante la coincidencia del puerto de envío que se suscribe al mensaje XML en el cuadro de mensajes con el puerto de envío asociado al acuerdo.</span><span class="sxs-lookup"><span data-stu-id="67e55-109">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends a message, the EDI send pipeline determines the agreement that the message resolves to by matching the send port that subscribes to the XML message in the MessageBox, with the send port associated with the agreement.</span></span> <span data-ttu-id="67e55-110">Si el puerto de envío no está asociado con un acuerdo, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usará las propiedades del acuerdo de reserva para procesar el mensaje para el envío.</span><span class="sxs-lookup"><span data-stu-id="67e55-110">If the send port is not associated with an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses the fallback agreement properties to process the message for sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67e55-111">La asociación del puerto de envío es solo un modo de resolver acuerdos.</span><span class="sxs-lookup"><span data-stu-id="67e55-111">Send port association is only one way of doing agreement resolution.</span></span> <span data-ttu-id="67e55-112">Para obtener más información acerca de la resolución del acuerdo para los mensajes salientes, vea [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span><span class="sxs-lookup"><span data-stu-id="67e55-112">For more information about agreement resolution for outgoing messages, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67e55-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="67e55-113">In This Section</span></span>  
  
-   [<span data-ttu-id="67e55-114">Configuración de X12 propiedades de acuerdo de reserva</span><span class="sxs-lookup"><span data-stu-id="67e55-114">Configuring X12 Fallback Agreement Properties</span></span>](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [<span data-ttu-id="67e55-115">Configuración de las propiedades del acuerdo de reserva de EDIFACT</span><span class="sxs-lookup"><span data-stu-id="67e55-115">Configuring EDIFACT Fallback Agreement Properties</span></span>](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a><span data-ttu-id="67e55-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="67e55-116">See Also</span></span>  
 [<span data-ttu-id="67e55-117">Rol de los acuerdos en el procesamiento de EDI</span><span class="sxs-lookup"><span data-stu-id="67e55-117">The Role of Agreements in EDI Processing</span></span>](../core/the-role-of-agreements-in-edi-processing.md)