---
title: Configuración de la validación (configuración de intercambio EDIFACT) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55820ebc-fe21-48a3-8985-1bf4184176ac
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a700282aee9651b8f259c931a460a774f900a4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999733"
---
# <a name="configuring-validation-edifact-interchange-settings"></a><span data-ttu-id="7a762-102">Configuración de la validación (configuración de intercambio de EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="7a762-102">Configuring Validation (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="7a762-103">En esta sección se proporcionan instrucciones acerca de cómo impedir que se procesen números de control duplicados.</span><span class="sxs-lookup"><span data-stu-id="7a762-103">This section provides instructions on how to prevent duplicate control numbers from being processed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7a762-104">Ninguna propiedad está deshabilitada en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="7a762-104">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a762-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7a762-105">Prerequisites</span></span>  
 <span data-ttu-id="7a762-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a762-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-duplicate-validation"></a><span data-ttu-id="7a762-107">Para configurar la validación de duplicados</span><span class="sxs-lookup"><span data-stu-id="7a762-107">To configure duplicate validation</span></span>  
  
1. <span data-ttu-id="7a762-108">Cree un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="7a762-108">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="7a762-109">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7a762-109">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="7a762-110">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **validación**.</span><span class="sxs-lookup"><span data-stu-id="7a762-110">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="7a762-111">Seleccione el **número de control de intercambio (UNB5)** casilla de verificación para habilitar la canalización de recepción bloquee los intercambios duplicados.</span><span class="sxs-lookup"><span data-stu-id="7a762-111">Select the **Interchange control number (UNB5)** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="7a762-112">Si se selecciona, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio para el intercambio recibido no coincida con el número de control de intercambio de otro intercambio recibido.</span><span class="sxs-lookup"><span data-stu-id="7a762-112">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number for the received interchange does not match the interchange control number of another received interchange.</span></span> <span data-ttu-id="7a762-113">Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.</span><span class="sxs-lookup"><span data-stu-id="7a762-113">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="7a762-114">Si **número de control de intercambio (UNB5)** está seleccionado, en el **comprobar unb5 duplicado dentro de** , escriba el número de días para buscar un intercambio duplicado.</span><span class="sxs-lookup"><span data-stu-id="7a762-114">If **Interchange control number (UNB5)** is selected, in the **Check for duplicate UNB5 within** field, enter the number of days to check for a duplicate interchange.</span></span>  
  
5. <span data-ttu-id="7a762-115">Seleccione **el número de control de grupo (UNG5) en intercambio** para impedir que la canalización de recepción procese grupos duplicados.</span><span class="sxs-lookup"><span data-stu-id="7a762-115">Select **Group control number (UNG5) in interchange** to prevent the receive pipeline from processing duplicate groups.</span></span>  
  
6. <span data-ttu-id="7a762-116">Seleccione **establecer Control número transacciones (UNH1) en el grupo** para evitar que la canalización de recepción de procesamiento de transacciones duplicados de conjuntos.</span><span class="sxs-lookup"><span data-stu-id="7a762-116">Select **Transaction Set Control Number (UNH1) in group** to prevent the receive pipeline from processing duplicate transaction sets.</span></span>  
  
7. <span data-ttu-id="7a762-117">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7a762-117">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a762-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a762-118">See Also</span></span>  
 [<span data-ttu-id="7a762-119">Configuración de las opciones de intercambio (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="7a762-119">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)