---
title: Configuración de identificadores de reserva (EDIFACT) | Documentos de Microsoft
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
ms.openlocfilehash: 81ddf25726d7413727fef1f4f41d99916c18c21d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233556"
---
# <a name="configuring-fallback-identifiers-edifact"></a><span data-ttu-id="b52f2-102">Configuración de identificadores de reserva (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="b52f2-102">Configuring Fallback Identifiers (EDIFACT)</span></span>
<span data-ttu-id="b52f2-103">En el acuerdo de reserva, debe establecer la contraseña de referencia del destinatario para comprobar que no se recibe el intercambio por parte de destinatarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="b52f2-103">In the fallback agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b52f2-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b52f2-104">Prerequisites</span></span>  
 <span data-ttu-id="b52f2-105">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52f2-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-recipient-password"></a><span data-ttu-id="b52f2-106">Para establecer el remitente, destinatario y la contraseña de destinatario</span><span class="sxs-lookup"><span data-stu-id="b52f2-106">To set the sender, recipient, recipient password</span></span>  
  
1.  <span data-ttu-id="b52f2-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo y, a continuación, haga clic en **configuración de reserva de EDIFACT**.</span><span class="sxs-lookup"><span data-stu-id="b52f2-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="b52f2-108">En el **configuración de reserva de EDIFACT** cuadro de diálogo la **páginas del acuerdo EDIFACT** , bajo la **configuración de intercambio** sección, haga clic en **identificadores** .</span><span class="sxs-lookup"><span data-stu-id="b52f2-108">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="b52f2-109">En el **remitente (UNB2)** sección, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b52f2-109">In the **Sender (UNB2)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="b52f2-110">Para **identificación (UNB2.1)**, escriba un valor alfanumérico con un mínimo y un máximo de 35.</span><span class="sxs-lookup"><span data-stu-id="b52f2-110">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="b52f2-111">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b52f2-111">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="b52f2-112">Para **calificador de código (UNB2.2)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b52f2-112">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="b52f2-113">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="b52f2-113">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="b52f2-114">Para **invertir la dirección de enrutamiento (UNB2.3)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 14 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b52f2-114">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="b52f2-115">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="b52f2-115">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="b52f2-116">Para **identificador de referencia de aplicaciones (UNB7)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de seis caracteres.</span><span class="sxs-lookup"><span data-stu-id="b52f2-116">For **Application reference ID (UNB7)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="b52f2-117">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b52f2-117">This is a required field.</span></span>  
  
4.  <span data-ttu-id="b52f2-118">En el **destinatario (UNB3)** sección, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b52f2-118">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="b52f2-119">Para **identificación (UNB3.1)**, escriba un valor alfanumérico con un mínimo y un máximo de 35.</span><span class="sxs-lookup"><span data-stu-id="b52f2-119">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="b52f2-120">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b52f2-120">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="b52f2-121">Para **calificador de código (UNB3.2)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b52f2-121">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="b52f2-122">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="b52f2-122">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="b52f2-123">Para **invertir la dirección de enrutamiento (UNB3.3)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de 14 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b52f2-123">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="b52f2-124">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="b52f2-124">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="b52f2-125">Si es necesario, en el **contraseña de referencia de destinatario (UNB6)** sección, especifique valores para la contraseña de referencia del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b52f2-125">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="b52f2-126">Para **valor (UNB6.1)**, escriba un valor alfanumérico con un mínimo y un máximo de 14.</span><span class="sxs-lookup"><span data-stu-id="b52f2-126">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="b52f2-127">Para **calificador (UNB6.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="b52f2-127">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="b52f2-128">Estos son los campos opcionales.</span><span class="sxs-lookup"><span data-stu-id="b52f2-128">These are optional fields.</span></span> <span data-ttu-id="b52f2-129">Si estos valores no coinciden con los campos UNB6.1 y UNB6.2 en un intercambio recibido, BizTalk Server suspenderá el intercambio.</span><span class="sxs-lookup"><span data-stu-id="b52f2-129">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b52f2-130">La combinación de **UNB6.1** y **UNB6.2** deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="b52f2-130">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b52f2-131">Si escribe valores para UNB6.1 y UNB6.2, aplique los cambios y deje en blanco UNB6.1, el valor de UNB6.2 también se eliminará y el campo quedará deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="b52f2-131">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5.  <span data-ttu-id="b52f2-132">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b52f2-132">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b52f2-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b52f2-133">See Also</span></span>  
 [<span data-ttu-id="b52f2-134">Configurar propiedades de acuerdo de reserva de EDIFACT para el procesamiento de intercambio</span><span class="sxs-lookup"><span data-stu-id="b52f2-134">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)