---
title: Configuración de las propiedades de confirmación de reserva (EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6062b881-3214-4e68-acbc-1f8c255fd86b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d9369eb7fff1a6217da774aaf62af6e036d0abd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233020"
---
# <a name="configuring-fallback-acknowledgement-properties-edifact"></a><span data-ttu-id="82584-102">Configuración de las propiedades de confirmación de reserva (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="82584-102">Configuring Fallback Acknowledgement Properties (EDIFACT)</span></span>
<span data-ttu-id="82584-103">En el acuerdo de reserva, puede especificar qué tipo de confirmación se va a devolver a una entidad.</span><span class="sxs-lookup"><span data-stu-id="82584-103">In the fallback agreement, you can specify what type of acknowledgment to return to a party.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="82584-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82584-104">Prerequisites</span></span>  
 <span data-ttu-id="82584-105">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82584-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="82584-106">Para configurar las propiedades globales de confirmación (CONTRL) de EDIFACT</span><span class="sxs-lookup"><span data-stu-id="82584-106">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="82584-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="82584-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="82584-108">En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración de intercambio** sección, haga clic en  **Confirmaciones**.</span><span class="sxs-lookup"><span data-stu-id="82584-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="82584-109">Seleccione **recepción del mensaje (CONTRL) esperada** para devolver una confirmación técnica (CONTRL) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="82584-109">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
4.  <span data-ttu-id="82584-110">Seleccione **confirmación (CONTRL) esperada** para devolver una confirmación funcional (CONTRL) al remitente del intercambio.</span><span class="sxs-lookup"><span data-stu-id="82584-110">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span>  
  
5.  <span data-ttu-id="82584-111">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="82584-111">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82584-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="82584-112">See Also</span></span>  
 [<span data-ttu-id="82584-113">Configurar propiedades de acuerdo de reserva de EDIFACT para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="82584-113">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)