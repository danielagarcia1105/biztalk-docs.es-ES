---
title: "Configuración de la validación (configuración de intercambio de X12) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdad7016-1d66-4d11-b620-c28368f00133
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0edfe66791fa5c041c66a3adddde61730afe54ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-x12-interchange-settings"></a><span data-ttu-id="9fcec-102">Configuración de la validación (configuración de intercambio de X12)</span><span class="sxs-lookup"><span data-stu-id="9fcec-102">Configuring Validation (X12-Interchange Settings)</span></span>
<span data-ttu-id="9fcec-103">La configuración de la generación de validación de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprueba si existen números de control duplicados en el intercambio recibido.</span><span class="sxs-lookup"><span data-stu-id="9fcec-103">X12 interchange validation generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fcec-104">La configuración descrita aquí también se aplica a la validación de intercambio HIPAA.</span><span class="sxs-lookup"><span data-stu-id="9fcec-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9fcec-105">Ninguna propiedad se deshabilita en esta página, incluso si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="9fcec-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9fcec-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9fcec-106">Prerequisites</span></span>  
 <span data-ttu-id="9fcec-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fcec-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="9fcec-108">Para configurar la validación</span><span class="sxs-lookup"><span data-stu-id="9fcec-108">To configure validation</span></span>  
  
1.  <span data-ttu-id="9fcec-109">Crear un acuerdo de codificación, como se describe en X12 [General configuración (X12)](../core/configuring-general-settings-x12.md).</span><span class="sxs-lookup"><span data-stu-id="9fcec-109">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="9fcec-110">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9fcec-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="9fcec-111">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **validación**.</span><span class="sxs-lookup"><span data-stu-id="9fcec-111">On a one-way agreement tab, under **Interchange Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="9fcec-112">Seleccione el **número de Control de intercambio** casilla de verificación para habilitar la canalización de recepción y bloquear los intercambios duplicados.</span><span class="sxs-lookup"><span data-stu-id="9fcec-112">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="9fcec-113">Si se ha seleccionado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio (ISA13) para el intercambio recibido no coincide con el número de control de intercambio.</span><span class="sxs-lookup"><span data-stu-id="9fcec-113">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="9fcec-114">Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.</span><span class="sxs-lookup"><span data-stu-id="9fcec-114">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4.  <span data-ttu-id="9fcec-115">Si **número de Control de intercambio** está seleccionada, en la **comprobar isa13 duplicados dentro de** , escriba el número de días que se realizará una comprobación de intercambios duplicados mediante un determinado número de control de intercambio.</span><span class="sxs-lookup"><span data-stu-id="9fcec-115">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5.  <span data-ttu-id="9fcec-116">Seleccione **número de Control de grupo** para impedir que la canalización de recepción procese los intercambios con números de control de grupo duplicado (GS6).</span><span class="sxs-lookup"><span data-stu-id="9fcec-116">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6.  <span data-ttu-id="9fcec-117">Seleccione **número de Control de conjunto de transacciones** para impedir que la canalización de recepción procese los intercambios con números de control de conjunto de transacciones duplicados (ST2).</span><span class="sxs-lookup"><span data-stu-id="9fcec-117">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7.  <span data-ttu-id="9fcec-118">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9fcec-118">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcec-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fcec-119">See Also</span></span>  
 [<span data-ttu-id="9fcec-120">Configuración de intercambio (X12)</span><span class="sxs-lookup"><span data-stu-id="9fcec-120">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)