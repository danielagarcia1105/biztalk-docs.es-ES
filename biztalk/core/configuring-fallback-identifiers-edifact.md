---
title: Configuración de identificadores de reserva (EDIFACT). | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2ce56c1-44f1-42dc-94e8-36e5ba664f53
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7db7e20f8ccb4db8da53483e7c33285f4b75afb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991989"
---
# <a name="configuring-fallback-identifiers-edifact"></a><span data-ttu-id="6241b-102">Configuración de identificadores de reserva (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="6241b-102">Configuring Fallback Identifiers (EDIFACT)</span></span>
<span data-ttu-id="6241b-103">En el acuerdo de reserva, debe establecer la contraseña de referencia del destinatario para comprobar que no se recibe el intercambio por parte de destinatarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="6241b-103">In the fallback agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6241b-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6241b-104">Prerequisites</span></span>  
 <span data-ttu-id="6241b-105">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6241b-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-recipient-password"></a><span data-ttu-id="6241b-106">Para establecer el remitente, destinatario y la contraseña de destinatario</span><span class="sxs-lookup"><span data-stu-id="6241b-106">To set the sender, recipient, recipient password</span></span>  
  
1. <span data-ttu-id="6241b-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="6241b-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="6241b-108">En el **configuración de reserva de EDIFACT** cuadro de diálogo el **páginas del acuerdo EDIFACT** , bajo el **configuración de intercambio** sección, haga clic en **identificadores** .</span><span class="sxs-lookup"><span data-stu-id="6241b-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="6241b-109">En el **remitente (UNB2)** sección, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6241b-109">In the **Sender (UNB2)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="6241b-110">Para **identificación (UNB2.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo.</span><span class="sxs-lookup"><span data-stu-id="6241b-110">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="6241b-111">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6241b-111">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="6241b-112">Para **calificador de código (UNB2.2)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6241b-112">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="6241b-113">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="6241b-113">This is an optional field.</span></span>  
  
   3.  <span data-ttu-id="6241b-114">Para **(UNB2.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="6241b-114">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="6241b-115">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="6241b-115">This is an optional field.</span></span>  
  
   4.  <span data-ttu-id="6241b-116">Para **Id. de referencia (UNB7)**, escriba un valor alfanumérico con un carácter como mínimo y seis caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="6241b-116">For **Application reference ID (UNB7)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="6241b-117">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6241b-117">This is a required field.</span></span>  
  
4. <span data-ttu-id="6241b-118">En el **destinatario (UNB3)** sección, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6241b-118">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
   1.  <span data-ttu-id="6241b-119">Para **identificación (UNB3.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo.</span><span class="sxs-lookup"><span data-stu-id="6241b-119">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="6241b-120">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="6241b-120">This is a required field.</span></span>  
  
   2.  <span data-ttu-id="6241b-121">Para **calificador de código (UNB3.2)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6241b-121">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="6241b-122">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="6241b-122">This is an optional field.</span></span>  
  
   3.  <span data-ttu-id="6241b-123">Para **(UNB3.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="6241b-123">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="6241b-124">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="6241b-124">This is an optional field.</span></span>  
  
   4.  <span data-ttu-id="6241b-125">Si es necesario, en el **contraseña de referencia de destinatario (UNB6)** sección, especifique valores para la contraseña de referencia del destinatario.</span><span class="sxs-lookup"><span data-stu-id="6241b-125">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="6241b-126">Para **valor (UNB6.1)**, escriba un valor alfanumérico con un mínimo y 14 como máximo.</span><span class="sxs-lookup"><span data-stu-id="6241b-126">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="6241b-127">Para **calificador (UNB6.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="6241b-127">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="6241b-128">Estos son los campos opcionales.</span><span class="sxs-lookup"><span data-stu-id="6241b-128">These are optional fields.</span></span> <span data-ttu-id="6241b-129">Si estos valores no coinciden con los campos UNB6.1 y UNB6.2 en un intercambio recibido, BizTalk Server suspenderá el intercambio.</span><span class="sxs-lookup"><span data-stu-id="6241b-129">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="6241b-130">La combinación de **UNB6.1** y **UNB6.2** deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="6241b-130">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="6241b-131">Si escribe valores para UNB6.1 y UNB6.2, aplique los cambios y deje en blanco UNB6.1, el valor de UNB6.2 también se eliminará y el campo quedará deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="6241b-131">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5. <span data-ttu-id="6241b-132">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6241b-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6241b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="6241b-133">See Also</span></span>  
 [<span data-ttu-id="6241b-134">Configuración de las propiedades de acuerdos de reserva de EDIFACT para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="6241b-134">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)