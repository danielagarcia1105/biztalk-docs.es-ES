---
title: Configuración de las propiedades de confirmación de reserva (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce33f5dd-fbd5-448c-8ea3-05dd1467131a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed4ce98bd4191d79ef05742b389e1d065325d8ed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008981"
---
# <a name="configuring-fallback-acknowledgement-properties-x12"></a><span data-ttu-id="18e7f-102">Configuración de propiedades de confirmación de reserva (X12)</span><span class="sxs-lookup"><span data-stu-id="18e7f-102">Configuring Fallback Acknowledgement Properties (X12)</span></span>
<span data-ttu-id="18e7f-103">En el acuerdo de reserva, puede especificar cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] genera confirmaciones en respuesta a intercambios codificados en X12 recibidos de la entidad y el tipo de confirmación devuelta a una entidad.</span><span class="sxs-lookup"><span data-stu-id="18e7f-103">In the fallback agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="18e7f-104">Esta sección proporciona instrucciones acerca de cómo hacer lo mismo.</span><span class="sxs-lookup"><span data-stu-id="18e7f-104">This section provides instructions on how to do the same.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18e7f-105">Las propiedades de confirmación descritas aquí se aplican también para las confirmaciones de HIPAA.</span><span class="sxs-lookup"><span data-stu-id="18e7f-105">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18e7f-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="18e7f-106">Prerequisites</span></span>  
 <span data-ttu-id="18e7f-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18e7f-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="18e7f-108">Para configurar las propiedades de confirmación de X12</span><span class="sxs-lookup"><span data-stu-id="18e7f-108">To configure X12 ACK properties</span></span>  
  
1. <span data-ttu-id="18e7f-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="18e7f-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="18e7f-110">En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración de intercambio** sección, haga clic en **confirmaciones**.</span><span class="sxs-lookup"><span data-stu-id="18e7f-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3. <span data-ttu-id="18e7f-111">Seleccione **TA1 esperado** para devolver una confirmación técnica (TA1) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="18e7f-111">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span>  
  
4. <span data-ttu-id="18e7f-112">Seleccione **997 esperado** para devolver una confirmación funcional (997) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="18e7f-112">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span>  
  
5. <span data-ttu-id="18e7f-113">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="18e7f-113">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e7f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="18e7f-114">See Also</span></span>  
 [<span data-ttu-id="18e7f-115">Configuración de las propiedades de acuerdos de reserva de X12 para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="18e7f-115">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)