---
title: Configuración de las propiedades de validación de reserva (EDIFACT) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b925d063-e24b-4cfb-acbd-dcadb511011d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf0e103eb2e20bb64973cd207ed2a55c2f91e58d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233204"
---
# <a name="configuring-fallback-validation-properties-edifact"></a><span data-ttu-id="eab2f-102">Configuración de las propiedades de validación de reserva (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="eab2f-102">Configuring Fallback Validation Properties (EDIFACT)</span></span>
<span data-ttu-id="eab2f-103">En esta sección se proporcionan instrucciones acerca de cómo impedir que se procesen números de control duplicados.</span><span class="sxs-lookup"><span data-stu-id="eab2f-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eab2f-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="eab2f-104">Prerequisites</span></span>  
 <span data-ttu-id="eab2f-105">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eab2f-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="eab2f-106">Para configurar la validación de duplicados</span><span class="sxs-lookup"><span data-stu-id="eab2f-106">To configure duplicate validation</span></span>  
  
1.  <span data-ttu-id="eab2f-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="eab2f-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="eab2f-108">En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración de intercambio** sección, haga clic en **validación** .</span><span class="sxs-lookup"><span data-stu-id="eab2f-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="eab2f-109">Seleccione el **número de control de intercambio (UNB5)** casilla de verificación para habilitar la canalización de recepción y bloquear los intercambios duplicados.</span><span class="sxs-lookup"><span data-stu-id="eab2f-109">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="eab2f-110">Si se selecciona, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio para el intercambio recibido no coincida con el número de control de intercambio de otro intercambio recibido.</span><span class="sxs-lookup"><span data-stu-id="eab2f-110">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="eab2f-111">Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.</span><span class="sxs-lookup"><span data-stu-id="eab2f-111">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="eab2f-112">Si **número de control de intercambio (UNB5)** está seleccionada, en la **comprobar unb5 duplicados dentro de** , escriba el número de días para comprobar si un intercambio duplicado.</span><span class="sxs-lookup"><span data-stu-id="eab2f-112">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5.  <span data-ttu-id="eab2f-113">Seleccione **el número de control de grupo (UNG5) en intercambio** para impedir que la canalización de recepción procese grupos duplicados.</span><span class="sxs-lookup"><span data-stu-id="eab2f-113">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6.  <span data-ttu-id="eab2f-114">Seleccione **establecer Control número transacciones (UNH1) en el grupo** impedir que la canalización de recepción procese una transacción duplicada establece.</span><span class="sxs-lookup"><span data-stu-id="eab2f-114">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7.  <span data-ttu-id="eab2f-115">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="eab2f-115">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab2f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="eab2f-116">See Also</span></span>  
 [<span data-ttu-id="eab2f-117">Configurar propiedades de acuerdo de reserva de EDIFACT para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="eab2f-117">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)