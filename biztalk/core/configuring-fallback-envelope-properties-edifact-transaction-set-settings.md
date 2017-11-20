---
title: "Configuración de las propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c93f9aae6d67e5dc56d383626e36d1db412be9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a><span data-ttu-id="0f36b-102">Configuración de propiedades de sobres de reserva (configuración del conjunto de transacciones EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="0f36b-102">Configuring Fallback Envelope Properties (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="0f36b-103">En el **sobres** página de la **configuración del conjunto de transacciones** sección, defina cómo BizTalk Server genera los segmentos UNG para un intercambio con codificación EDIFACT que envía a la entidad.</span><span class="sxs-lookup"><span data-stu-id="0f36b-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="0f36b-104">El segmento UNG es el encabezado que identifica y especifica un grupo funcional de un intercambio codificado en EDIFACT.</span><span class="sxs-lookup"><span data-stu-id="0f36b-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="0f36b-105">Contiene información acerca de la fecha y la hora en la que el grupo funcional se preparó, junto con el tipo y la versión del documento en el grupo funcional.</span><span class="sxs-lookup"><span data-stu-id="0f36b-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f36b-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f36b-106">Prerequisites</span></span>  
 <span data-ttu-id="0f36b-107">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f36b-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-segments"></a><span data-ttu-id="0f36b-108">Para definir segmentos UNG</span><span class="sxs-lookup"><span data-stu-id="0f36b-108">To define the UNG segments</span></span>  
  
1.  <span data-ttu-id="0f36b-109">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="0f36b-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="0f36b-110">En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración del conjunto de transacciones** sección, haga clic en **sobres** .</span><span class="sxs-lookup"><span data-stu-id="0f36b-110">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="0f36b-111">Para **Id. de grupo funcional (UNG1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-111">For **Functional group ID (UNG1)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="0f36b-112">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-112">This is a required field.</span></span>  
  
4.  <span data-ttu-id="0f36b-113">Escriba los valores para identificar **remitente de aplicación (UNG2)**.</span><span class="sxs-lookup"><span data-stu-id="0f36b-113">Enter values to identify **Application sender (UNG2)**.</span></span>  
  
    -   <span data-ttu-id="0f36b-114">Para **identificación (UNG2.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-114">For **Identification (UNG2.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="0f36b-115">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-115">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f36b-116">Para **calificador de código (UNG2.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-116">For **Code qualifier (UNG2.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="0f36b-117">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="0f36b-117">This is an optional field.</span></span>  
  
5.  <span data-ttu-id="0f36b-118">Escriba los valores para identificar **destinatario de la aplicación (UNG3)**.</span><span class="sxs-lookup"><span data-stu-id="0f36b-118">Enter values to identify **Application recipient (UNG3)**.</span></span>  
  
    -   <span data-ttu-id="0f36b-119">Para **identificación (UNG3.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 35 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-119">For **Identification (UNG3.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="0f36b-120">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-120">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f36b-121">Para **calificador de código (UNG3.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de cuatro caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-121">For **Code qualifier (UNG3.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="0f36b-122">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="0f36b-122">This is an optional field.</span></span>  
  
6.  <span data-ttu-id="0f36b-123">Para **Agencia de control (UNG6)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-123">For **Controlling agency (UNG6)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="0f36b-124">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-124">This is a required field.</span></span>  
  
7.  <span data-ttu-id="0f36b-125">Escriba los valores para identificar **versión del mensaje (UNG7)**.</span><span class="sxs-lookup"><span data-stu-id="0f36b-125">Enter values to identify **Message version (UNG7)**.</span></span>  
  
    -   <span data-ttu-id="0f36b-126">Para **versión (UNG7.1)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-126">For **Version (UNG7.1)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="0f36b-127">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f36b-128">Para **versión (UNG7.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de tres caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-128">For **Release (UNG7.2)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="0f36b-129">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f36b-130">Para **código (UNG7.3) asignado a la asociación**, escriba un valor alfanumérico con un mínimo de 1 carácter y un máximo de 6 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-130">For **Association assigned code (UNG7.3)**, enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="0f36b-131">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="0f36b-131">This is an optional field.</span></span>  
  
8.  <span data-ttu-id="0f36b-132">Para **contraseña de aplicaciones (UNG8)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 14 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0f36b-132">For **Application password (UNG8)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="0f36b-133">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0f36b-133">This is a required field.</span></span>  
  
9. <span data-ttu-id="0f36b-134">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0f36b-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f36b-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f36b-135">See Also</span></span>  
 [<span data-ttu-id="0f36b-136">Configurar la configuración de propiedades de acuerdo de reserva de EDIFACT para la transacción</span><span class="sxs-lookup"><span data-stu-id="0f36b-136">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)