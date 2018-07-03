---
title: Configuración de confirmaciones (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28df03b8955c17888a4722c361a2e4481c63b413
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970701"
---
# <a name="configuring-acknowledgements-x12"></a><span data-ttu-id="17755-102">Configuración de confirmaciones (X12)</span><span class="sxs-lookup"><span data-stu-id="17755-102">Configuring Acknowledgements (X12)</span></span>
<span data-ttu-id="17755-103">En el acuerdo de socios comerciales, se puede especificar cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera las confirmaciones en respuesta a intercambios con codificación X12 recibidos de la entidad y qué tipo de confirmación se devuelve a la entidad.</span><span class="sxs-lookup"><span data-stu-id="17755-103">In the partner agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="17755-104">También se puede especificar si una confirmación debe procesarse por lotes y si se generan bucles AK2 para los conjuntos de transacciones aceptados.</span><span class="sxs-lookup"><span data-stu-id="17755-104">You can also specify whether to batch an acknowledgement and whether AK2 loops are generated for accepted transaction sets.</span></span> <span data-ttu-id="17755-105">Esta sección proporciona instrucciones acerca de cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="17755-105">This section provides instructions on how to do so.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17755-106">Las propiedades de confirmación descritas aquí se aplican también para las confirmaciones de HIPAA.</span><span class="sxs-lookup"><span data-stu-id="17755-106">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="17755-107">Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="17755-107">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="17755-108">**Incluir bucle AK2 para conjuntos de transacciones aceptadas (si se desactiva, bucle se generará sólo si AK501 no es igual a)**.</span><span class="sxs-lookup"><span data-stu-id="17755-108">**Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span>  
> 
>   <span data-ttu-id="17755-109">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="17755-109">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="17755-110">Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="17755-110">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="17755-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="17755-111">Prerequisites</span></span>  
 <span data-ttu-id="17755-112">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17755-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="17755-113">Para configurar las propiedades de confirmación de X12</span><span class="sxs-lookup"><span data-stu-id="17755-113">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="17755-114">Crear un acuerdo de codificación, como se describe en X12 [configuración General de las opciones (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="17755-114">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="17755-115">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="17755-115">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="17755-116">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio**, haga clic en **confirmaciones**.</span><span class="sxs-lookup"><span data-stu-id="17755-116">On a one-way agreement tab, under **Interchange Settings**, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="17755-117">Seleccione **TA1 esperado** para devolver una confirmación técnica (TA1) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="17755-117">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="17755-118">Si ha seleccionado, seleccione **no procesar por lotes TA1** para enviar cada confirmación técnica por separado, o bien deje la casilla desactivada para procesar por lotes las confirmaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="17755-118">If selected, select **Do not batch TA1** to send each technical acknowledgment separately, or leave the check box cleared to batch the technical acknowledgments.</span></span>  
  
4.  <span data-ttu-id="17755-119">Seleccione **997 esperado** para devolver una confirmación funcional (997) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="17755-119">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="17755-120">Si ha seleccionado, seleccione **no procesar por lotes 997** para enviar cada confirmación funcional por separado, o bien deje la casilla desactivada para procesar por lotes las confirmaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="17755-120">If selected, select **Do not batch 997** to send each functional acknowledgment separately, or leave the check box cleared to batch the functional acknowledgments.</span></span>  
  
5.  <span data-ttu-id="17755-121">Para habilitar la generación de bucles AK2 en 997 confirmaciones para conjuntos de transacciones aceptadas, seleccione **incluir bucle AK2 para conjuntos de transacciones aceptadas (si se desactiva, bucle se generará sólo si AK501 no es igual a)**.</span><span class="sxs-lookup"><span data-stu-id="17755-121">To enable generation of AK2 loops in 997 acknowledgments for accepted transaction sets, select **Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span> <span data-ttu-id="17755-122">Para obtener más información acerca de los bucles AK2, vea [X12 confirmación 997](../core/x12-997-acknowledgment.md).</span><span class="sxs-lookup"><span data-stu-id="17755-122">For more information about AK2 loops, see [X12 997 Acknowledgment](../core/x12-997-acknowledgment.md).</span></span>  
  
6.  <span data-ttu-id="17755-123">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17755-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17755-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="17755-124">See Also</span></span>  
 [<span data-ttu-id="17755-125">Configuración de las opciones de intercambio (X12)</span><span class="sxs-lookup"><span data-stu-id="17755-125">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)