---
title: Comprobar un mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, verifying
- verifying, messages
ms.assetid: df2b72bb-4dc1-4fdd-8f63-35fc73a12151
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f2fdc186e93bd182b3021a3ef8fc258cee59923
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961650"
---
# <a name="verifying-a-message"></a><span data-ttu-id="a539a-102">Comprobación de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a539a-102">Verifying a Message</span></span>
<span data-ttu-id="a539a-103">En esta sección se describe cómo comprobar un mensaje que se ha reparado.</span><span class="sxs-lookup"><span data-stu-id="a539a-103">This section describes how to verify a message that has been repaired.</span></span>  
  
### <a name="to-verify-a-message"></a><span data-ttu-id="a539a-104">Para comprobar un mensaje</span><span class="sxs-lookup"><span data-stu-id="a539a-104">To verify a message</span></span>  
  
1.  <span data-ttu-id="a539a-105">En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.</span><span class="sxs-lookup"><span data-stu-id="a539a-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="a539a-106">En la ventana principal, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="a539a-106">In the Home window, click **Documents**.</span></span>  
  
3.  <span data-ttu-id="a539a-107">En la ventana de documentos, en **las bibliotecas de documentos**, haga clic en  **\< *nombre de departamento*\>_Verifier**.</span><span class="sxs-lookup"><span data-stu-id="a539a-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Verifier**.</span></span>  
  
4.  <span data-ttu-id="a539a-108">En la ventana de comprobar, haga clic en **Bandeja de entrada**.</span><span class="sxs-lookup"><span data-stu-id="a539a-108">In the Verify window, click **Inbox**.</span></span>  
  
5.  <span data-ttu-id="a539a-109">En la ventana de la Bandeja de entrada de comprobar, seleccione el título del mensaje, haga clic en la flecha situada a la derecha del título del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.</span><span class="sxs-lookup"><span data-stu-id="a539a-109">In the Verify Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  
  
6.  <span data-ttu-id="a539a-110">En el **descarga de archivos** cuadro de diálogo, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="a539a-110">In the **File Download** dialog box, click **Open**.</span></span>  
  
7.  <span data-ttu-id="a539a-111">En los Roles actuales: RekeyVerify panel de la [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **errores**.</span><span class="sxs-lookup"><span data-stu-id="a539a-111">In the Current Roles: RekeyVerify pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="a539a-112">Revise cualquier error que se muestra en el **Parse y errores de validación XML** cuadro y **errores de validación de BRE** cuadro.</span><span class="sxs-lookup"><span data-stu-id="a539a-112">Review any errors shown in the **Parse and XML Validation Errors** box and the **BRE Validation Errors** box.</span></span>  
  
8.  <span data-ttu-id="a539a-113">En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, desplácese a la ubicación del error y compruebe que se ha corregido el error.</span><span class="sxs-lookup"><span data-stu-id="a539a-113">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="a539a-114">Puede ver ¿cuál fue el error original, haga clic en **errores** en la función actual: RekeyVerify panel y ver el error en uno de los paneles de error.</span><span class="sxs-lookup"><span data-stu-id="a539a-114">You can see what the original error was by clicking **Errors** in the Current Role: RekeyVerify pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="a539a-115">También puede comparar las versiones sin reparar y reparadas del mensaje, haga clic en **detalles del mensaje** en la función actual: RekeyVerify panel.</span><span class="sxs-lookup"><span data-stu-id="a539a-115">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: RekeyVerify pane.</span></span>  
  
9. <span data-ttu-id="a539a-116">Para asegurarse de que el mensaje se validará, haga clic en **validación** en la función actual: RekeyVerify panel y, a continuación, haga clic en **mensaje Validate**.</span><span class="sxs-lookup"><span data-stu-id="a539a-116">To ensure that the message will validate, click **Validation** in the Current Role: RekeyVerify pane, and then click **Validate Message**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a539a-117">El panel de resultados de validación del mensaje en la función actual: panel RekeyVerify indica todos los campos en el mensaje que necesita para la regeneración de claves.</span><span class="sxs-lookup"><span data-stu-id="a539a-117">The Results pane under Message Validation in the Current Role: RekeyVerify pane indicates all fields in the message that you need to rekey.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="a539a-118">marca estos campos en el panel de mensajes con un asterisco rojo.</span><span class="sxs-lookup"><span data-stu-id="a539a-118"> marks these fields in the Message pane with a red asterisk.</span></span>  
  
10. <span data-ttu-id="a539a-119">Regenerar los datos en todos los campos en el panel de mensajes marcados con un asterisco rojo (lo que indica que los datos deben regeneración antes de su envío).</span><span class="sxs-lookup"><span data-stu-id="a539a-119">Rekey data into all fields in the Message pane marked with a red asterisk (indicating that the data must be rekeyed before submission).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a539a-120">Puede mostrar los datos que necesita para la regeneración de claves en campos de mensaje, haga clic en **detalles del mensaje** en la función actual: RekeyVerify panel y para desplazarse por el mensaje original para el campo.</span><span class="sxs-lookup"><span data-stu-id="a539a-120">You can display the data that you need to rekey into message fields by clicking **Message Details** in the Current Role: RekeyVerify pane, and scrolling through the original message to the field.</span></span> <span data-ttu-id="a539a-121">Esto es así a menos que se produjo un error de validación en uno de los campos de regeneración de claves en el mensaje original, en cuyo caso tendrá que reparar el campo cuando se la regenerar.</span><span class="sxs-lookup"><span data-stu-id="a539a-121">This is true unless there was a validation error in one of the rekey fields in the original message, in which case you have to repair the field when you rekey it.</span></span>  
  
11. <span data-ttu-id="a539a-122">Haga clic en **validación** en el **rol actual: RekeyVerify** panel y, a continuación, haga clic en **mensaje Validate**.</span><span class="sxs-lookup"><span data-stu-id="a539a-122">Click **Validation** in the **Current Role: RekeyVerify** pane, and then click **Validate Message**.</span></span> <span data-ttu-id="a539a-123">Compruebe que el panel de resultados muestra el mensaje **el mensaje es válido**.</span><span class="sxs-lookup"><span data-stu-id="a539a-123">Verify that the Results pane displays the message **The message is valid**.</span></span>  
  
12. <span data-ttu-id="a539a-124">Haga clic en **enviar** en el [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana.</span><span class="sxs-lookup"><span data-stu-id="a539a-124">Click **Submit** in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a539a-125">Al hacer clic en **enviar**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] realiza la validación XML en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a539a-125">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="a539a-126">Si la validación no se realiza correctamente, debe corregir los errores de validación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a539a-126">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  
  
13. <span data-ttu-id="a539a-127">En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje comprobado con cambios aceptados.</span><span class="sxs-lookup"><span data-stu-id="a539a-127">In the Submit Message dialog box, click **Accept** to submit the verified message with changes accepted.</span></span> <span data-ttu-id="a539a-128">Haga clic en **rechazar** para enviar el mensaje con los cambios rechazados.</span><span class="sxs-lookup"><span data-stu-id="a539a-128">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="a539a-129">Haga clic en **cancelar** cancelar el envío y volver al formulario.</span><span class="sxs-lookup"><span data-stu-id="a539a-129">Click **Cancel** to cancel the submission and return to the form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a539a-130">Si acepta los cambios en el mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] realiza comprobaciones de BRE en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a539a-130">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a539a-131">Si se rechazan los cambios en el mensaje, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] devuelve el mensaje a la primera fase del flujo de trabajo (crear o reparar) y restablece el flujo de trabajo de reparación.</span><span class="sxs-lookup"><span data-stu-id="a539a-131">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  
  
14. <span data-ttu-id="a539a-132">En la página Asistente para firmas digitales para seleccionar el certificado para firmar el formulario, seleccione el certificado que desea utilizar para firmar el formulario (es decir, el certificado que ha creado para el Comprobador) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a539a-132">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the verifier), and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a539a-133">Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que se desea comprobar y, a continuación, haga clic en **Ver formulario firmado**.</span><span class="sxs-lookup"><span data-stu-id="a539a-133">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="a539a-134">Si necesita agregar otra firma para este rol, puede hacerlo en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a539a-134">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  
  
15. <span data-ttu-id="a539a-135">En la página Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a539a-135">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
16. <span data-ttu-id="a539a-136">En la página Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto.</span><span class="sxs-lookup"><span data-stu-id="a539a-136">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="a539a-137">Haga clic en **Ver certificado** si desea comprobar que se usa la firma correcta.</span><span class="sxs-lookup"><span data-stu-id="a539a-137">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="a539a-138">Haga clic en **he comprobado el contenido antes de la firma**y, a continuación, haga clic en **inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="a539a-138">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
17. <span data-ttu-id="a539a-139">En la ventana de comprobar la firma Digital, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a539a-139">In the Verify Digital Signature window, click **Close**.</span></span>  
  
18. <span data-ttu-id="a539a-140">En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a539a-140">In the Submission Success dialog box, click **OK**.</span></span>  
  
19. <span data-ttu-id="a539a-141">Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="a539a-141">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  
  
20. <span data-ttu-id="a539a-142">En el sitio MRSR, haga clic en **documentos y listas**.</span><span class="sxs-lookup"><span data-stu-id="a539a-142">In MRSR site, click **Documents and Lists**.</span></span> <span data-ttu-id="a539a-143">Si hace clic en **Accept** para aceptar los cambios en el paso 13, compruebe que la \<nombre de departamento\>_Approve biblioteca de documentos contiene el mensaje que se ha modificado recientemente.</span><span class="sxs-lookup"><span data-stu-id="a539a-143">If you clicked **Accept** to accept the changes in step 13, verify that the \<Department name\>_Approve document library contains the message that was just modified.</span></span> <span data-ttu-id="a539a-144">Si ya tenía abrir la ventana de documentos y listas, haga clic en **actualizar** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="a539a-144">If you already had the Documents and Lists window open, click **Refresh** on the **View** menu.</span></span> <span data-ttu-id="a539a-145">Si hace clic en **rechazar** para rechazar los cambios en el paso 13, compruebe que la  *\<nombre_equipo\>*_Outbox biblioteca de documentos contiene el mensaje que se ha modificado recientemente.</span><span class="sxs-lookup"><span data-stu-id="a539a-145">If you clicked **Reject** to reject the changes in step 13, verify that the *\<computer name\>*_Outbox document library contains the message that was just modified.</span></span>