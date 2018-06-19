---
title: Habilitar la recepción de varios intercambios en un único mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c98bcd2e-495a-49d8-a471-6e23b1e161f9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec1b282908424100ddfd0363fd6bede9011d53a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240836"
---
# <a name="enabling-the-receiving-of-multiple-interchanges-in-a-single-message"></a><span data-ttu-id="16f40-102">Habilitar la recepción de varios intercambios en un único mensaje</span><span class="sxs-lookup"><span data-stu-id="16f40-102">Enabling the Receiving of Multiple Interchanges in a Single Message</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="16f40-103"> puede procesar un mensaje que contiene varios intercambios.</span><span class="sxs-lookup"><span data-stu-id="16f40-103"> can process a message that contains multiple interchanges.</span></span> <span data-ttu-id="16f40-104">Por ejemplo, un mensaje X12 incluye varios encabezados ISA y finalizadores IEA.</span><span class="sxs-lookup"><span data-stu-id="16f40-104">For an X12 message, such a message would include multiple ISA headers and IEA trailers.</span></span> <span data-ttu-id="16f40-105">Por otro lado, un mensaje EDIFACT incluye varios encabezados UNA/UNB y finalizadores UNZ.</span><span class="sxs-lookup"><span data-stu-id="16f40-105">For an EDIFACT message, such a message would include multiple UNA/UNB headers and UNZ trailers.</span></span>  
  
 <span data-ttu-id="16f40-106">Para habilitar el Desensamblador EDI en la canalización EdiReceive o AS2EdiReceive para que analice varios intercambios en un único mensaje, debe establecer el **DetectMID** propiedad de canalización **True**.</span><span class="sxs-lookup"><span data-stu-id="16f40-106">To enable the EDI Disassembler in the EdiReceive or AS2EdiReceive pipeline to parse multiple interchanges in a single message, you must set the **DetectMID** pipeline property to **True**.</span></span> <span data-ttu-id="16f40-107">(MID significa desensamblado de varios intercambios). Esta propiedad está establecida en True de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="16f40-107">(MID stands for multiple interchange disassembling.) This property is set to True by default.</span></span>  
  
 <span data-ttu-id="16f40-108">Cuando la canalización de recepción que incluye el desensamblador EDI recibe un mensaje con varios intercambios, el desensamblador analizará cada uno de los intercambios, desde el encabezado hasta el finalizador del intercambio.</span><span class="sxs-lookup"><span data-stu-id="16f40-108">When the receive pipeline that includes the EDI Disassembler receives a message with multiple interchange, the Disassembler will parse each interchange from the interchange header to the interchange trailer.</span></span> <span data-ttu-id="16f40-109">Este procesamiento se realiza de acuerdo con las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="16f40-109">This processing is done according to the following rules:</span></span>  
  
-   <span data-ttu-id="16f40-110">Todos los intercambios del mismo mensaje deben estar codificados de la misma forma, bien X12 bien EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="16f40-110">All interchanges in the same message must be of the same encoding type, either X12 or EDIFACT.</span></span> <span data-ttu-id="16f40-111">Si el mensaje contiene intercambios con más de un tipo de codificación, el desensamblador EDI procesará todos los intercambios con el mismo tipo de codificación como el primer intercambio del mensaje.</span><span class="sxs-lookup"><span data-stu-id="16f40-111">If the message contains interchanges of more than one encoding type, the EDI Disassembler will process all interchanges that have the same encoding type as the first interchange in the message.</span></span> <span data-ttu-id="16f40-112">El desensamblador omitirá en el primer intercambio todos los intercambios que cuenten con otro tipo de codificación.</span><span class="sxs-lookup"><span data-stu-id="16f40-112">The Disassembler will ignore all interchanges that are of a different encoding type from the first interchange.</span></span>  
  
-   <span data-ttu-id="16f40-113">El desensamblador EDI omitirá todos los caracteres existentes entre el finalizador de un intercambio y el encabezado del siguiente.</span><span class="sxs-lookup"><span data-stu-id="16f40-113">The EDI Disassembler will ignore any character between the interchange trailer of one interchange and the interchange heading of the next interchange.</span></span>  
  
-   <span data-ttu-id="16f40-114">Si habilita la autenticación seleccionando la opción el **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** propiedad para el puerto de recepción y, a continuación, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] le suspender el mensaje completo si se produce un error en cualquiera de los distintos intercambios del mensaje.</span><span class="sxs-lookup"><span data-stu-id="16f40-114">If you enable authentication by selecting either the **Drop messages if authentication fails** or the **Keep messages if authentication fails** property for the receive port, then [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the entire message if any one of the multiple interchanges in the message fails.</span></span>  
  
-   <span data-ttu-id="16f40-115">Si habilita la autenticación y alguno de los intercambios del mismo mensaje no se resuelve para un acuerdo, se suspenderán todos los intercambios del mensaje y no se devolverá ninguna confirmación, ni siquiera para los intercambios que sí se resolvieron para un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="16f40-115">If you enable authentication, and if any one interchange in the same message does not resolve to an agreement, then all interchanges in the message will be suspended, and no acknowledgments will be returned, even for those interchanges that did resolve to an agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="16f40-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="16f40-116">Prerequisites</span></span>  
 <span data-ttu-id="16f40-117">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16f40-117">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-enable-the-receiving-of-multiple-interchanges-in-a-message"></a><span data-ttu-id="16f40-118">Para habilitar la recepción de varios intercambios en un mensaje</span><span class="sxs-lookup"><span data-stu-id="16f40-118">To enable the receiving of multiple interchanges in a message</span></span>  
  
1.  <span data-ttu-id="16f40-119">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **ubicaciones de recepción** nodo, haga la ubicación de recepción que desea habilitar para que reciba varios intercambios en un único mensaje y, a continuación, haga clic en  **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="16f40-119">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, click the **Receive Locations** node, right-click the receive location that you want to enable to receive multiple interchange in a single message, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="16f40-120">Haga clic en el botón de puntos suspensivos que aparece junto a la canalización de recepción (que debe ser EdiReceive o AS2EdiReceive).</span><span class="sxs-lookup"><span data-stu-id="16f40-120">Click the ellipses next to the receive pipeline (which must be either EdiReceive or AS2EdiReceive).</span></span>  
  
3.  <span data-ttu-id="16f40-121">En el **configurar canalización** cuadro de diálogo, establezca la **DetectMID** propiedad de canalización **True**.</span><span class="sxs-lookup"><span data-stu-id="16f40-121">In the **Configure Pipeline** dialog box, set the **DetectMID** pipeline property to **True**.</span></span>  
  
4.  <span data-ttu-id="16f40-122">Haga clic en **Aceptar**, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="16f40-122">Click **OK**, then click **OK** again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16f40-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="16f40-123">See Also</span></span>  
 [<span data-ttu-id="16f40-124">Configurar puertos para una solución EDI</span><span class="sxs-lookup"><span data-stu-id="16f40-124">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)