---
title: Configuración de las propiedades de validación de reserva (X12) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a64431d-373a-4d63-9b83-cbb323620152
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f9dca1416b106e951b32efe79d18260201dc48
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973933"
---
# <a name="configuring-fallback-validation-properties-x12"></a><span data-ttu-id="32c39-102">Configuración de propiedades de validación de reserva (X12)</span><span class="sxs-lookup"><span data-stu-id="32c39-102">Configuring Fallback Validation Properties (X12)</span></span>
<span data-ttu-id="32c39-103">La configuración de reserva de generación de validación de intercambio X12 define cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprueba si hay números de control duplicados en el intercambio recibido.</span><span class="sxs-lookup"><span data-stu-id="32c39-103">X12 interchange validation generation fallback settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] checks for duplicate control numbers in the received interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32c39-104">La configuración descrita aquí también se aplica a la validación de intercambio HIPAA.</span><span class="sxs-lookup"><span data-stu-id="32c39-104">The settings described here also apply to HIPAA interchange validation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32c39-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="32c39-105">Prerequisites</span></span>  
 <span data-ttu-id="32c39-106">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32c39-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-validation"></a><span data-ttu-id="32c39-107">Para configurar la validación</span><span class="sxs-lookup"><span data-stu-id="32c39-107">To configure validation</span></span>  
  
1. <span data-ttu-id="32c39-108">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **X12 configuración de reserva**.</span><span class="sxs-lookup"><span data-stu-id="32c39-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="32c39-109">En el **X12 configuración de reserva** cuadro de diálogo el **X12 páginas del acuerdo** , bajo el **configuración de intercambio** sección, haga clic en **validación**.</span><span class="sxs-lookup"><span data-stu-id="32c39-109">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Validation**.</span></span>  
  
3. <span data-ttu-id="32c39-110">Seleccione el **número de Control de intercambio** casilla de verificación para habilitar la canalización de recepción bloquee los intercambios duplicados.</span><span class="sxs-lookup"><span data-stu-id="32c39-110">Select the **Interchange Control Number** check box to enable the receive pipeline to block duplicate interchanges.</span></span> <span data-ttu-id="32c39-111">Si se ha seleccionado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comprobará que el número de control de intercambio (ISA13) para el intercambio recibido no coincide con el número de control de intercambio.</span><span class="sxs-lookup"><span data-stu-id="32c39-111">If selected, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will check that the interchange control number (ISA13) for the received interchange does not match the interchange control number.</span></span> <span data-ttu-id="32c39-112">Si se detecta una coincidencia, la canalización de recepción no procesará el intercambio.</span><span class="sxs-lookup"><span data-stu-id="32c39-112">If a match is detected, the receive pipeline will not process the interchange.</span></span>  
  
4. <span data-ttu-id="32c39-113">Si **Interchange Control Number** está seleccionado, en el **comprobar isa13 duplicados dentro de** , escriba el número de días que se realizará una comprobación de intercambios duplicados mediante un determinado número de control de intercambio.</span><span class="sxs-lookup"><span data-stu-id="32c39-113">If **Interchange Control Number** is selected, in the **Check for duplicate ISA13 within** field, enter the number of days that a check for a duplicate interchange will be performed using a specific interchange control number.</span></span>  
  
5. <span data-ttu-id="32c39-114">Seleccione **número de Control de grupo** para impedir que la canalización de recepción procese los intercambios con números de control de grupo duplicados (GS6).</span><span class="sxs-lookup"><span data-stu-id="32c39-114">Select **Group Control Number** to prevent the receive pipeline from processing interchanges with duplicate group control numbers (GS6).</span></span>  
  
6. <span data-ttu-id="32c39-115">Seleccione **número de Control de conjunto de transacciones** para impedir que la canalización de recepción procese los intercambios con números de control de conjunto de transacciones duplicados (ST2).</span><span class="sxs-lookup"><span data-stu-id="32c39-115">Select **Transaction Set Control Number** to prevent the receive pipeline from processing interchanges with duplicate transaction set control numbers (ST2).</span></span>  
  
7. <span data-ttu-id="32c39-116">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="32c39-116">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c39-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c39-117">See Also</span></span>  
 [<span data-ttu-id="32c39-118">Configuración de las propiedades de acuerdos de reserva de X12 para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="32c39-118">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)