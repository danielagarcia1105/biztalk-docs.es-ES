---
title: Configuración de identificadores (EDIFACT). | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 097292f2-1aa5-42e4-aeee-c7d4cbdae17c
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c50743c237c66edcba1e6609dcd1ab9cb0081bc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997221"
---
# <a name="configuring-identifiers-edifact"></a><span data-ttu-id="aafd7-102">Configuración de identificadores (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="aafd7-102">Configuring Identifiers (EDIFACT)</span></span>
<span data-ttu-id="aafd7-103">En el acuerdo de socios comerciales, debe establecer la contraseña de referencia del destinatario para comprobar que no se recibe el intercambio por parte de destinatarios no autorizados.</span><span class="sxs-lookup"><span data-stu-id="aafd7-103">In the partner agreement, you must set the recipient reference password, in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aafd7-104">Las siguientes propiedades están deshabilitadas en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** casilla durante la creación de la entidad para el que se crea el contrato.</span><span class="sxs-lookup"><span data-stu-id="aafd7-104">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="aafd7-105">**DestinationPartyName** en **resoluciones de acuerdos adicionales** sección.</span><span class="sxs-lookup"><span data-stu-id="aafd7-105">**DestinationPartyName** under **Additional Agreement Resolvers** section.</span></span>  
> 
>   <span data-ttu-id="aafd7-106">Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad.</span><span class="sxs-lookup"><span data-stu-id="aafd7-106">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="aafd7-107">Por ejemplo, si crea dos entidades, entidad A y entidad B, y para la entidad A ha desactivado la casilla de verificación, la lista anterior de propiedades están deshabilitadas en el **entidad A -> entidad B** ficha de acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="aafd7-107">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aafd7-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="aafd7-108">Prerequisites</span></span>  
 <span data-ttu-id="aafd7-109">Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aafd7-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-the-sender-recipient-and-recipient-password"></a><span data-ttu-id="aafd7-110">Procedimiento para establecer el remitente, el destinatario y la contraseña de destinatario</span><span class="sxs-lookup"><span data-stu-id="aafd7-110">To set the sender, recipient, and recipient password</span></span>  
  
1.  <span data-ttu-id="aafd7-111">Cree un acuerdo de codificación, como se describe en EDIFACT [configuración General de configuración (EDIFACT)](../core/configuring-general-settings-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="aafd7-111">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="aafd7-112">Para actualizar un acuerdo existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aafd7-112">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="aafd7-113">En una ficha de acuerdo unidireccional, bajo **configuración de intercambio** sección, haga clic en **identificadores**.</span><span class="sxs-lookup"><span data-stu-id="aafd7-113">On a one-way agreement tab, under **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="aafd7-114">En el **remitente (UNB2)** sección, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aafd7-114">In the **Sender (UNB2)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="aafd7-115">Para **identificación (UNB2.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-115">For **Identification (UNB2.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="aafd7-116">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="aafd7-116">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="aafd7-117">Para **calificador de código (UNB2.2)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="aafd7-117">For **Code qualifier (UNB2.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="aafd7-118">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="aafd7-118">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="aafd7-119">Para **(UNB2.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-119">For **Reverse routing address (UNB2.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="aafd7-120">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="aafd7-120">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="aafd7-121">En el **destinatario (UNB3)** sección, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aafd7-121">In the **Recipient (UNB3)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="aafd7-122">Para **identificación (UNB3.1)**, escriba un valor alfanumérico con un mínimo y 35 como máximo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-122">For **Identification (UNB3.1)**, enter an alphanumeric value with a minimum of one and a maximum of 35.</span></span> <span data-ttu-id="aafd7-123">Este campo es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="aafd7-123">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="aafd7-124">Para **calificador de código (UNB3.2)**, seleccione un valor de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="aafd7-124">For **Code qualifier (UNB3.2)**, select a value from the drop-down list.</span></span> <span data-ttu-id="aafd7-125">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="aafd7-125">This is an optional field.</span></span>  
  
    3.  <span data-ttu-id="aafd7-126">Para **(UNB3.3) la dirección de enrutamiento inverso**, escriba un valor alfanumérico con un carácter como mínimo y 14 caracteres como máximo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-126">For **Reverse routing address (UNB3.3)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="aafd7-127">Se trata de un campo opcional.</span><span class="sxs-lookup"><span data-stu-id="aafd7-127">This is an optional field.</span></span>  
  
    4.  <span data-ttu-id="aafd7-128">Si es necesario, en el **contraseña de referencia de destinatario (UNB6)** sección, especifique valores para la contraseña de referencia del destinatario.</span><span class="sxs-lookup"><span data-stu-id="aafd7-128">If required, in the **Recipient reference password (UNB6)** section, enter values for the recipient reference password.</span></span> <span data-ttu-id="aafd7-129">Para **valor (UNB6.1)**, escriba un valor alfanumérico con un mínimo y 14 como máximo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-129">For **Value (UNB6.1)**, enter an alphanumeric value with a minimum of one and a maximum of 14.</span></span> <span data-ttu-id="aafd7-130">Para **calificador (UNB6.2)**, escriba un valor alfanumérico con un carácter como mínimo y un máximo de dos caracteres.</span><span class="sxs-lookup"><span data-stu-id="aafd7-130">For **Qualifier (UNB6.2)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="aafd7-131">Estos son los campos opcionales.</span><span class="sxs-lookup"><span data-stu-id="aafd7-131">These are optional fields.</span></span> <span data-ttu-id="aafd7-132">Si estos valores no coinciden con los campos UNB6.1 y UNB6.2 en un intercambio recibido, BizTalk Server suspenderá el intercambio.</span><span class="sxs-lookup"><span data-stu-id="aafd7-132">If these values do not match the UNB6.1 and UNB6.2 fields in a received interchange, BizTalk Server will suspend the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="aafd7-133">La combinación de **UNB6.1** y **UNB6.2** deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="aafd7-133">The combination of **UNB6.1** and **UNB6.2** must be unique.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="aafd7-134">Si escribe valores para UNB6.1 y UNB6.2, aplique los cambios y deje en blanco UNB6.1, el valor de UNB6.2 también se eliminará y el campo quedará deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="aafd7-134">If you enter values for both UNB6.1 and UNB6.2, apply the changes and then blank out UNB6.1, the value in UNB6.2 will also be deleted and the field will be disabled.</span></span>  
  
5.  <span data-ttu-id="aafd7-135">En el **resoluciones de acuerdos adicionales** sección, para **DestinationPartyName** propiedad, especifique un valor para la entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="aafd7-135">In the **Additional Agreement Resolvers** section, for **DestinationPartyName** property, specify a value for the destination party.</span></span> <span data-ttu-id="aafd7-136">Este valor también se usa para resolver los mensajes de salida a un acuerdo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-136">This value is also used to resolve outbound messages to an agreement.</span></span> <span data-ttu-id="aafd7-137">Para obtener más información, vea [resolución de acuerdos y determinación de esquemas para mensajes EDI salientes](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span><span class="sxs-lookup"><span data-stu-id="aafd7-137">For more information see, [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aafd7-138">Normalmente no es necesario establecer la **DestinationPartyName** propiedad.</span><span class="sxs-lookup"><span data-stu-id="aafd7-138">You typically do not need to set the **DestinationPartyName** property.</span></span> <span data-ttu-id="aafd7-139">Esta propiedad está disponible como parte de las propiedades de acuerdo para admitir escenarios de actualización.</span><span class="sxs-lookup"><span data-stu-id="aafd7-139">This property is available as part of the agreement properties to support upgrade scenarios.</span></span> <span data-ttu-id="aafd7-140">Al actualizar desde BizTalk Server 2006 R2 o BizTalk Server 2009, el **DestinationPartyName** propiedad está establecida en el nombre de la entidad en BizTalk Server 2006 R2 o BizTalk Server 2009.</span><span class="sxs-lookup"><span data-stu-id="aafd7-140">When upgrading from BizTalk Server 2006 R2 or BizTalk Server 2009, the **DestinationPartyName** property is set to the name of the party in BizTalk Server 2006 R2 or BizTalk Server 2009.</span></span>  
  
6.  <span data-ttu-id="aafd7-141">Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="aafd7-141">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="aafd7-142">Si hace clic en **Aceptar** o **aplicar** en esta fase, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="aafd7-142">If you click **OK** or **Apply** at this stage, you will get an error.</span></span> <span data-ttu-id="aafd7-143">Eso es porque aún tiene que proporcionar valores UNB2 y UNB3 en la **identificadores** pestaña de la ficha del acuerdo unidireccional.</span><span class="sxs-lookup"><span data-stu-id="aafd7-143">That is because you still need to provide UNB2 and UNB3 values on the **Identifiers** tab for the other one-way agreement tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aafd7-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="aafd7-144">See Also</span></span>  
 [<span data-ttu-id="aafd7-145">Configuración de las opciones de intercambio (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="aafd7-145">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)