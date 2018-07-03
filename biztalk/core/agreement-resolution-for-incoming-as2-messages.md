---
title: Resolución del acuerdo para mensajes AS2 entrantes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 746d01af-de6a-4d5d-9433-b0e1a2b41861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25a464025377eae7fd70992359d3be1582fa748a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016732"
---
# <a name="agreement-resolution-for-incoming-as2-messages"></a><span data-ttu-id="38627-102">Resolución del acuerdo para mensajes AS2 entrantes</span><span class="sxs-lookup"><span data-stu-id="38627-102">Agreement Resolution for Incoming AS2 Messages</span></span>
<span data-ttu-id="38627-103">Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje con codificación EDIINT/AS2 sobre el transporte HTTP/HTTPS, intenta determinar el perfil de negocio del socio comercial que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="38627-103">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDIINT/AS2-encoded message over HTTP/HTTPS transport, it attempts to determine the trading partner’s business profile that sent the message.</span></span> <span data-ttu-id="38627-104">Para ello, trata de realizar lo que se indica a continuación (en el mismo orden que se muestra):</span><span class="sxs-lookup"><span data-stu-id="38627-104">It does so by attempting to do the following (in the order shown):</span></span>  
  
1. <span data-ttu-id="38627-105">Establece una correspondencia entre el AS2-del encabezado del mensaje entrante con el valor de **AS2-desde** en el **identificadores** página del acuerdo AS2 unidireccional en el **laspropiedadesdelacuerdo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="38627-105">Make a match between the AS2-From header in the incoming message with the value for **AS2-From** in the **Identifiers** page of the one-way AS2 agreement in the **Agreement Properties** dialog box.</span></span>  
  
2. <span data-ttu-id="38627-106">Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede determinar el acuerdo, intentará corresponder la propiedad de contexto AS2-From que se haya establecido para el mensaje entrante con el nombre de un socio comercial.</span><span class="sxs-lookup"><span data-stu-id="38627-106">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement, it will attempt to match the AS2-From context property that is set for the incoming message with the name of a trading partner.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38627-107">Puesto que el encabezado AS2-From solo puede contener caracteres ASCII, debe asegurarse de que el nombre del socio comercial y el alias AS2-From contienen únicamente caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="38627-107">Since the AS2-From header can only contain ASCII characters, you must ensure that your trading partner name and the AS2-From alias also contain only ASCII characters.</span></span> <span data-ttu-id="38627-108">Si no se encuentra una coincidencia exacta, BizTalk no podrá determinar el acuerdo basándose en los encabezados de mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="38627-108">If an exact match does not occur, BizTalk will be unable to determine the agreement based on the incoming message headers.</span></span>  
  
 <span data-ttu-id="38627-109">La canalización de recepción AS2 solo procesará el mensaje si se ha determinado un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="38627-109">The AS2 receive pipeline will process the message only if an agreement is determined.</span></span> <span data-ttu-id="38627-110">A diferencia del procesamiento EDI, no existen propiedades AS2 de reserva que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] pueda usar en caso de que no pueda determinar el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="38627-110">Unlike in EDI processing, there are no fallback AS2 properties that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can use if it cannot determine the agreement.</span></span>  
  
 <span data-ttu-id="38627-111">Una vez que la canalización haya determinado el acuerdo, comprobará la configuración de la **encabezado del mensaje de configuración para la validación y MDN en su lugar el contrato usa** propiedad en el **validación** página de AS2 unidireccional acuerdo en el **configuración del acuerdo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="38627-111">Once the pipeline has determined the agreement, it will check the setting of the **Use agreement settings for validation and MDN instead message header** property in the **Validation** page of the one-way AS2 agreement in the **Agreement Settings** dialog box.</span></span> <span data-ttu-id="38627-112">Si está activada esa propiedad, la canalización de recepción usará las propiedades de acuerdo para procesar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="38627-112">If that property is checked, the receive pipeline will use the agreement properties to process the message.</span></span> <span data-ttu-id="38627-113">Si la propiedad está desactivada, la canalización de recepción usará los valores del encabezado de AS2 del mensaje para llevar a cabo el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="38627-113">If the property is cleared, the receive pipeline will use the values in the AS2 header of the message to process it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38627-114">Es posible que el acuerdo AS2 que se determina durante la resolución de acuerdo no sea el mismo que la carga EDI.</span><span class="sxs-lookup"><span data-stu-id="38627-114">The AS2 agreement that is determined during agreement resolution may not be the same agreement as the EDI payload.</span></span> <span data-ttu-id="38627-115">No hay ningún requisito que indique que AS2 y EDI deben compartir el mismo acuerdo, ya que el acuerdo AS2 puede representar una cámara de compensación que enruta documentos EDI de varias entidades.</span><span class="sxs-lookup"><span data-stu-id="38627-115">There is no requirement that AS2 and EDI must share the same agreement, as the AS2 agreement may represent a clearinghouse that routes EDI documents from multiple parties.</span></span>  
  
 <span data-ttu-id="38627-116">Para obtener más detalles sobre el proceso de recepción, vea [procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md).</span><span class="sxs-lookup"><span data-stu-id="38627-116">For more details on the receive process, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38627-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="38627-117">See Also</span></span>  
 [<span data-ttu-id="38627-118">Cómo recibe BizTalk Server los mensajes AS2</span><span class="sxs-lookup"><span data-stu-id="38627-118">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)