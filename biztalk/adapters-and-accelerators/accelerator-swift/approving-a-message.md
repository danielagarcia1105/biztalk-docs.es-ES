---
title: Aprobación de un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, approving
- approving messages
ms.assetid: e6abfef3-aab2-470e-a7a7-a6d091ffba53
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c565f40c6c455456101521414edf0c377411014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967109"
---
# <a name="approving-a-message"></a><span data-ttu-id="a6a34-102">Aprobación de un mensaje</span><span class="sxs-lookup"><span data-stu-id="a6a34-102">Approving a Message</span></span>
<span data-ttu-id="a6a34-103">En esta sección se describe cómo aprobar un mensaje que se ha reparado y comprobado.</span><span class="sxs-lookup"><span data-stu-id="a6a34-103">This section describes how to approve a message that has been repaired and verified.</span></span>  

### <a name="to-approve-a-message"></a><span data-ttu-id="a6a34-104">Para aprobar un mensaje</span><span class="sxs-lookup"><span data-stu-id="a6a34-104">To approve a message</span></span>  

1. <span data-ttu-id="a6a34-105">En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.</span><span class="sxs-lookup"><span data-stu-id="a6a34-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="a6a34-106">En la ventana principal, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="a6a34-107">En la ventana de documentos en **las bibliotecas de documentos**, haga clic en  **\< *nombre de departamento*\>_Approver**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>_Approver**.</span></span>  

4. <span data-ttu-id="a6a34-108">En el \<nombre de departamento\>_Approver ventana, haga clic en **Bandeja de entrada**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-108">In the \<Department name\>_Approver window, click **Inbox**.</span></span>  

5. <span data-ttu-id="a6a34-109">En la ventana de la Bandeja de entrada, seleccione el título del mensaje, haga clic en la flecha situada a la derecha del título del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="a6a34-110">En el panel del Acelerador de SWIFT del [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **errores**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Errors**.</span></span> <span data-ttu-id="a6a34-111">Revise cualquier error que se muestra en el **Parse y errores de validación XML** cuadro, el **BRE los errores de validación** cuadro y el **errores en tiempo de ejecución** cuadro.</span><span class="sxs-lookup"><span data-stu-id="a6a34-111">Review any errors shown in the **Parse and XML Validation Errors** box, the **BRE Validation Errors** box, and the **Runtime Errors** box.</span></span>  

7. <span data-ttu-id="a6a34-112">En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, desplácese a la ubicación del error y compruebe que se ha corregido el error.</span><span class="sxs-lookup"><span data-stu-id="a6a34-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error and verify that the error has been corrected.</span></span> <span data-ttu-id="a6a34-113">Puede ver qué error original haciendo **errores** en el rol actual: aprobar panel y ver el error en uno de los paneles de error.</span><span class="sxs-lookup"><span data-stu-id="a6a34-113">You can see what the original error was by clicking **Errors** in the Current Role: Approve pane, and viewing the error in one of the error panes.</span></span> <span data-ttu-id="a6a34-114">También puede comparar las versiones sin reparar y reparadas del mensaje, haga clic en **detalles del mensaje** en el rol actual: aprobar el panel.</span><span class="sxs-lookup"><span data-stu-id="a6a34-114">You can also compare the unrepaired and repaired versions of the message by clicking **Message Details** in the Current Role: Approve pane.</span></span>  

8. <span data-ttu-id="a6a34-115">Para asegurarse de que se validará el mensaje, haga clic en **validación** en el rol actual: aprobar el panel y, a continuación, haga clic en **validar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-115">To ensure that the message will validate, click **Validation** in the Current Role: Approve pane, and then click **Validate Message**.</span></span> <span data-ttu-id="a6a34-116">Compruebe que el panel de resultados muestra el mensaje **el mensaje es válido**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-116">Verify that the Results pane displays the message **The message is valid**.</span></span>  

9. <span data-ttu-id="a6a34-117">Si aprueba los cambios que se realizaron en el documento, en el [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-117">If you approve of the changes that have been made to the document, in the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a6a34-118">Al hacer clic en **enviar**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] realiza la validación de XML en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a6a34-118">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="a6a34-119">Si la validación no se realiza correctamente, debe corregir los errores de validación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a6a34-119">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

10. <span data-ttu-id="a6a34-120">En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje aprobado con cambios aceptados.</span><span class="sxs-lookup"><span data-stu-id="a6a34-120">In the Submit Message dialog box, click **Accept** to submit the approved message with changes accepted.</span></span> <span data-ttu-id="a6a34-121">Haga clic en **rechazar** para enviar el mensaje con los cambios que se rechazó.</span><span class="sxs-lookup"><span data-stu-id="a6a34-121">Click **Reject** to submit the message with changes rejected.</span></span> <span data-ttu-id="a6a34-122">Haga clic en **cancelar** para cancelar el envío y volver al formulario.</span><span class="sxs-lookup"><span data-stu-id="a6a34-122">Click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6a34-123">Si acepta el mensaje cambia [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] realiza validaciones del BRE en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a6a34-123">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="a6a34-124">Si lo rechaza el mensaje cambia [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] devuelve el mensaje a la primera fase del flujo de trabajo (crear o reparar) y restablece el flujo de trabajo de reparación.</span><span class="sxs-lookup"><span data-stu-id="a6a34-124">If you reject the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] returns the message to the first stage of the workflow (create or repair) and resets the repair workflow.</span></span>  

11. <span data-ttu-id="a6a34-125">En la página del Asistente para firmas digitales para seleccionar el certificado para firmar el formulario, seleccione el certificado que se va a usar para firmar el formulario (es decir, el certificado que ha creado para el aprobador).</span><span class="sxs-lookup"><span data-stu-id="a6a34-125">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the approver).</span></span> <span data-ttu-id="a6a34-126">Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta.</span><span class="sxs-lookup"><span data-stu-id="a6a34-126">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="a6a34-127">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-127">Click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="a6a34-128">Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que desee comprobar y, a continuación, haga clic en **Ver formulario firmado**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span> <span data-ttu-id="a6a34-129">También puede ver qué roles han registrado previamente el formulario (solo se puede firmar un formulario por una persona una vez por cada flujo de trabajo), haga clic en **firmas digitales** en el **herramientas** menú.</span><span class="sxs-lookup"><span data-stu-id="a6a34-129">You can also see which roles have signed the form previously (a form can only be signed by a person once per workflow) by clicking **Digital Signatures** on the **Tools** menu.</span></span> <span data-ttu-id="a6a34-130">Si necesita agregar otra firma de este rol, puede hacerlo en el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a6a34-130">If you need to add another signature for this role, do so in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Management Console.</span></span>  

12. <span data-ttu-id="a6a34-131">En la página del Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-131">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

13. <span data-ttu-id="a6a34-132">En la página del Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto.</span><span class="sxs-lookup"><span data-stu-id="a6a34-132">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="a6a34-133">Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta.</span><span class="sxs-lookup"><span data-stu-id="a6a34-133">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="a6a34-134">Haga clic en **he comprobado el contenido antes de iniciar sesión**y, a continuación, haga clic en **sesión**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-134">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="a6a34-135">En la ventana de comprobar la firma Digital, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-135">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="a6a34-136">En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a6a34-136">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="a6a34-137">Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="a6a34-137">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

17. <span data-ttu-id="a6a34-138">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, abra la carpeta que configuró para recibir los mensajes enviados.</span><span class="sxs-lookup"><span data-stu-id="a6a34-138">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, open the folder that you set up to receive sent messages.</span></span> <span data-ttu-id="a6a34-139">Compruebe que la carpeta contiene el mensaje aprobado.</span><span class="sxs-lookup"><span data-stu-id="a6a34-139">Verify that the folder contains the approved message.</span></span> <span data-ttu-id="a6a34-140">Abra el mensaje en un editor de texto para comprobar que se ha corregido el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a6a34-140">Open the message in a text editor to verify that the message has been repaired.</span></span>
