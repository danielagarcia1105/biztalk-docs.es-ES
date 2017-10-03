---
title: "Configuración de las propiedades de confirmación de reserva (X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 216961dea0bdf4a67c550fba8a599eff2d0c89ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a><span data-ttu-id="9c816-102">Configuración de propiedades de confirmación de reserva (X12)</span><span class="sxs-lookup"><span data-stu-id="9c816-102">Configuring Fallback Acknowledgement Properties (X12)</span></span>
<span data-ttu-id="9c816-103">En el acuerdo de reserva, puede especificar cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera confirmaciones en respuesta a intercambios codificados en X12 recibidos de la entidad y el tipo de confirmación devuelta a una entidad.</span><span class="sxs-lookup"><span data-stu-id="9c816-103">In the fallback agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="9c816-104">Esta sección proporciona instrucciones acerca de cómo hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="9c816-104">This section provides instructions on how to do the same.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c816-105">Las propiedades de confirmación descritas aquí se aplican también para las confirmaciones de HIPAA.</span><span class="sxs-lookup"><span data-stu-id="9c816-105">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9c816-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9c816-106">Prerequisites</span></span>  
 <span data-ttu-id="9c816-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c816-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="9c816-108">Para configurar las propiedades de confirmación de X12</span><span class="sxs-lookup"><span data-stu-id="9c816-108">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="9c816-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="9c816-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="9c816-110">En el **X12 configuración de reserva** cuadro de diálogo la **X12 páginas del acuerdo** , bajo la **configuración de intercambio** sección, haga clic en **confirmaciones**.</span><span class="sxs-lookup"><span data-stu-id="9c816-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="9c816-111">Seleccione **TA1 esperado** para devolver una confirmación técnica (TA1) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="9c816-111">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span>  
  
4.  <span data-ttu-id="9c816-112">Seleccione **997 esperado** para devolver una confirmación funcional (997) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="9c816-112">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span>  
  
5.  <span data-ttu-id="9c816-113">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9c816-113">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c816-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c816-114">See Also</span></span>  
 [<span data-ttu-id="9c816-115">Configuración de X12 propiedades de acuerdo de reserva para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="9c816-115">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)