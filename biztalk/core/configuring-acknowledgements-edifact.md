---
title: Configuración de confirmaciones (EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe376437c2d6657acb98d548c2c1373b050d599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233500"
---
# <a name="configuring-acknowledgements-edifact"></a><span data-ttu-id="8c3ff-102">Configuración de confirmaciones (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="8c3ff-102">Configuring Acknowledgements (EDIFACT)</span></span>
<span data-ttu-id="8c3ff-103">En el acuerdo de socios comerciales, puede especificar qué tipo de confirmación se va a devolver a una entidad y qué tipo de puerto de envío se va a usar para enviar la confirmación.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-103">In the partner agreement, you can specify what type of acknowledgment to return to a party and what kind of send port to use in sending the acknowledgment.</span></span> <span data-ttu-id="8c3ff-104">También se especifica si se va a procesar por lotes una confirmación, el número de referencia inicial del conjunto de transacciones correspondiente a la confirmación y si se generan bucles SG1/SG4 para los conjuntos de transacciones aceptados.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-104">You also specify whether to batch an acknowledgment, what the starting transaction set reference number is for the acknowledgment, and whether SG1/SG4 loops are generated for accepted transaction sets.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c3ff-105">Las propiedades siguientes están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="8c3ff-106">**Generar bucle SG1/SG4 en conjuntos de transacciones aceptadas (si se desactiva, bucle se generará sólo si UCM.5 no es igual a 7)**.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-106">**Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span>  
>   
>  <span data-ttu-id="8c3ff-107">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="8c3ff-108">Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c3ff-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8c3ff-109">Prerequisites</span></span>  
 <span data-ttu-id="8c3ff-110">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c3ff-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="8c3ff-111">Para configurar las propiedades globales de confirmación (CONTRL) de EDIFACT</span><span class="sxs-lookup"><span data-stu-id="8c3ff-111">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="8c3ff-112">Crear un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ff-112">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="8c3ff-113">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8c3ff-114">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **confirmaciones**.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-114">On a one-way agreement tab, under **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="8c3ff-115">En el **sección EDIFACT ACK (Control)**, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c3ff-115">In the **EDIFACT ACK (Control) section**, do the following:</span></span>  
  
    1.  <span data-ttu-id="8c3ff-116">Seleccione **recepción del mensaje (CONTRL) esperada** para devolver una confirmación técnica (CONTRL) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-116">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="8c3ff-117">Si **recepción del mensaje (CONTRL) esperada** está seleccionada, seleccione **no por lotes de recepción del mensaje del mensaje (CONTRL)** para enviar cada confirmación por separado o déjela desactivada para procesar por lotes las confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-117">If **Receipt of message (CONTRL) expected** is selected, select **Do not batch receipt of message (CONTRL) message** to send each acknowledgment separately, or leave cleared to batch the acknowledgments.</span></span>  
  
    2.  <span data-ttu-id="8c3ff-118">Seleccione **confirmación (CONTRL) esperada** para devolver una confirmación funcional (CONTRL) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-118">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="8c3ff-119">Si **confirmación (CONTRL) esperada** está seleccionada, seleccione **no procesar por lotes confirmación (CONTRL)** para enviar cada confirmación funcional por separado o déjela desactivada para procesar por lotes funcional confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-119">If **Acknowledgement (CONTRL) expected** is selected, select **Do not batch Acknowledgement (CONTRL)** to send each functional acknowledgment separately, or leave cleared to batch the functional acknowledgments.</span></span>  
  
4.  <span data-ttu-id="8c3ff-120">En el **informe de aceptación del estado del conjunto de transacciones** sección para forzar la generación de bucles SG1/SG4 en confirmaciones CONTRL funcionales para conjuntos de transacciones aceptados, seleccione **SG1/SG4 generar bucle para aceptado conjuntos de transacciones (si se desactiva, bucle se generará sólo si UCM.5 no es igual a 7)**.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-120">In the **Transaction set status acceptance reporting** section, to force generation of SG1/SG4 loops in functional CONTRL acknowledgments for accepted transaction sets, select **Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span> <span data-ttu-id="8c3ff-121">Para obtener más información acerca de los bucles SG1/SG4, vea [mensaje CONTRL de EDIFACT como confirmación funcional](../core/edifact-contrl-message-as-functional-acknowledgment.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ff-121">For more information about SG1/SG4 loops, see [EDIFACT CONTRL Message as Functional Acknowledgment](../core/edifact-contrl-message-as-functional-acknowledgment.md).</span></span>  
  
5.  <span data-ttu-id="8c3ff-122">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8c3ff-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c3ff-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c3ff-123">See Also</span></span>  
 [<span data-ttu-id="8c3ff-124">Configuración de intercambio (EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="8c3ff-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)