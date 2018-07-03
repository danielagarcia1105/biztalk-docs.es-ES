---
title: Configuración de las propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f060b37004346ae5b7419acbe9f1fcf1d128179
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020264"
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a><span data-ttu-id="e226c-102">Configuración de propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e226c-102">Configuring Fallback Envelope Properties (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="e226c-103">En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos UNG para un intercambio con codificación EDIFACT que envía a la entidad.</span><span class="sxs-lookup"><span data-stu-id="e226c-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="e226c-104">El segmento UNG es el encabezado que identifica y especifica un grupo funcional de un intercambio codificado en EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="e226c-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="e226c-105">Contiene información acerca de la fecha y la hora en la que el grupo funcional se preparó, junto con el tipo y la versión del documento en el grupo funcional.</span><span class="sxs-lookup"><span data-stu-id="e226c-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e226c-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e226c-106">Prerequisites</span></span>  
 <span data-ttu-id="e226c-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e226c-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-segments"></a><span data-ttu-id="e226c-108">Para definir segmentos UNG</span><span class="sxs-lookup"><span data-stu-id="e226c-108">To define the UNG segments</span></span>  
  
1. <span data-ttu-id="e226c-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="e226c-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="e226c-110">En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración del conjunto de transacciones** sección, haga clic en **sobres** .</span><span class="sxs-lookup"><span data-stu-id="e226c-110">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="e226c-111">Para **Id. de grupo funcional (UNG1)**, escriba un valor alfanumérico con un carácter como mínimo y seis caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="e226c-111">For **Functional group ID (UNG1)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="e226c-112">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-112">This is a required field.</span></span>  
  
4. <span data-ttu-id="e226c-113">Escriba los valores que identificar **remitente de la aplicación (UNG2)**.</span><span class="sxs-lookup"><span data-stu-id="e226c-113">Enter values to identify **Application sender (UNG2)**.</span></span>  
  
   -   <span data-ttu-id="e226c-114">Para **identificación (UNG2.1)**, escriba un valor alfanumérico con un carácter como mínimo y 35 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="e226c-114">For **Identification (UNG2.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="e226c-115">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-115">This is a required field.</span></span>  
  
   -   <span data-ttu-id="e226c-116">Para **calificador de código (UNG2.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres.</span><span class="sxs-lookup"><span data-stu-id="e226c-116">For **Code qualifier (UNG2.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="e226c-117">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="e226c-117">This is an optional field.</span></span>  
  
5. <span data-ttu-id="e226c-118">Escriba los valores que identificar **destinatario de la aplicación (UNG3)**.</span><span class="sxs-lookup"><span data-stu-id="e226c-118">Enter values to identify **Application recipient (UNG3)**.</span></span>  
  
   -   <span data-ttu-id="e226c-119">Para **identificación (UNG3.1)**, escriba un valor alfanumérico con un carácter como mínimo y 35 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="e226c-119">For **Identification (UNG3.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="e226c-120">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-120">This is a required field.</span></span>  
  
   -   <span data-ttu-id="e226c-121">Para **calificador de código (UNG3.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres.</span><span class="sxs-lookup"><span data-stu-id="e226c-121">For **Code qualifier (UNG3.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="e226c-122">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="e226c-122">This is an optional field.</span></span>  
  
6. <span data-ttu-id="e226c-123">Para **Agencia de control (UNG6)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="e226c-123">For **Controlling agency (UNG6)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="e226c-124">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-124">This is a required field.</span></span>  
  
7. <span data-ttu-id="e226c-125">Escriba los valores que identificar **versión del mensaje (UNG7)**.</span><span class="sxs-lookup"><span data-stu-id="e226c-125">Enter values to identify **Message version (UNG7)**.</span></span>  
  
   -   <span data-ttu-id="e226c-126">Para **versión (UNG7.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="e226c-126">For **Version (UNG7.1)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="e226c-127">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-127">This is a required field.</span></span>  
  
   -   <span data-ttu-id="e226c-128">Para **versión (UNG7.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="e226c-128">For **Release (UNG7.2)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="e226c-129">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-129">This is a required field.</span></span>  
  
   -   <span data-ttu-id="e226c-130">Para **asignado a la asociación (UNG7.3) código**, escriba un valor alfanumérico con un mínimo de 1 carácter y un máximo de 6 caracteres.</span><span class="sxs-lookup"><span data-stu-id="e226c-130">For **Association assigned code (UNG7.3)**, enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="e226c-131">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="e226c-131">This is an optional field.</span></span>  
  
8. <span data-ttu-id="e226c-132">Para **contraseña de aplicaciones (UNG8)**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="e226c-132">For **Application password (UNG8)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="e226c-133">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e226c-133">This is a required field.</span></span>  
  
9. <span data-ttu-id="e226c-134">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e226c-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e226c-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="e226c-135">See Also</span></span>  
 [<span data-ttu-id="e226c-136">Configuración de las propiedades de acuerdos de reserva de EDIFACT para valores de conjuntos de transacciones</span><span class="sxs-lookup"><span data-stu-id="e226c-136">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)