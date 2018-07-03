---
title: Reparación de un mensaje | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
ms.assetid: 3a61b73b-5433-4249-b580-6194ccb4aebc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9edb8f9cc3c5db67e75ff47125e0d58891a5173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992045"
---
# <a name="repairing-a-message"></a><span data-ttu-id="fd3ca-102">Reparación de un mensaje</span><span class="sxs-lookup"><span data-stu-id="fd3ca-102">Repairing a Message</span></span>
<span data-ttu-id="fd3ca-103">En esta sección se describe cómo reparar un mensaje que no se pudo validar.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-103">This section describes how to repair a message that has failed validation.</span></span>  

### <a name="to-repair-a-message"></a><span data-ttu-id="fd3ca-104">Para reparar un mensaje</span><span class="sxs-lookup"><span data-stu-id="fd3ca-104">To repair a message</span></span>  

1. <span data-ttu-id="fd3ca-105">En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-105">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="fd3ca-106">En la ventana principal, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-106">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="fd3ca-107">En la ventana de documentos en **las bibliotecas de documentos**, haga clic en  **\< *nombre de departamento*\>**_**reparador**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-107">In the Documents window, under **Document Libraries**, click **\<*Department name*\>**_**Repairer**.</span></span>  

4. <span data-ttu-id="fd3ca-108">En el \< *nombre de departamento*\>_Repair ventana, haga clic en **Bandeja de entrada**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-108">In the \<*Department name*\>_Repair window, click **Inbox**.</span></span>  

5. <span data-ttu-id="fd3ca-109">En la ventana de la Bandeja de entrada, seleccione el título del mensaje, haga clic en la flecha situada a la derecha del título del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-109">In the Inbox window, point to the title of the message, click the arrow to the right of the message title, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="fd3ca-110">En el panel del Acelerador de SWIFT del [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana 2007, asegúrese de que **errores** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-110">In the SWIFT Accelerator pane of the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, ensure that **Errors** is selected.</span></span> <span data-ttu-id="fd3ca-111">Revise los errores que se muestra en el **Parse y errores de validación XML**, **BRE los errores de validación**, y **errores en tiempo de ejecución** cuadros.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-111">Review any errors shown in the **Parse and XML Validation Errors**, **BRE Validation Errors**, and **Runtime Errors** boxes.</span></span>  

7. <span data-ttu-id="fd3ca-112">En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forman, desplácese a la ubicación del error y corrija el error.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-112">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, scroll to the location of the error, and correct the error.</span></span> <span data-ttu-id="fd3ca-113">Si es un error de validación de XML, el error se resaltarán en rojo.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-113">If it is an XML validation error, the error will be highlighted in red.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="fd3ca-114">Errores de validación del BRE no se resaltarán en rojo en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-114">BRE validation errors will not be highlighted in red in the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form.</span></span> <span data-ttu-id="fd3ca-115">Para obtener más información sobre los errores de validación del BRE, consulte [códigos de Error de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ca-115">For more information about BRE validation errors, see [SWIFT Error Codes](../../adapters-and-accelerators/accelerator-swift/swift-error-codes.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="fd3ca-116">Si el error se produce en un campo que está acompañado por una lista desplegable, no podrá ver el valor original que produjo el error.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-116">If the error occurs in a field that is accompanied by a drop-down list, you will not be able to see the original value that caused the error.</span></span> <span data-ttu-id="fd3ca-117">Mostrará el campo "Select" en lugar del valor original.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-117">The field will display "Select" instead of the original value.</span></span> <span data-ttu-id="fd3ca-118">Seleccione el valor adecuado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-118">Select the appropriate value from the drop-down list.</span></span>  

8. <span data-ttu-id="fd3ca-119">Para asegurarse de que se validará el mensaje, haga clic en **validación** en el rol actual: reparar panel y, a continuación, haga clic en **validar mensajes**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-119">To ensure that the message will validate, click **Validation** in the Current Role: Repair pane, and then click **Validate Message**.</span></span> <span data-ttu-id="fd3ca-120">Compruebe que el panel de resultados muestra **el mensaje es válido**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-120">Verify that the Results pane displays **The message is valid**.</span></span>  

9. <span data-ttu-id="fd3ca-121">En el [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 ventana, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-121">In the [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)][!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, click **Submit**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="fd3ca-122">Al hacer clic en **enviar**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] realiza la validación de XML en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-122">When you click **Submit**, [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] performs XML validation on the message.</span></span> <span data-ttu-id="fd3ca-123">Si la validación no se realiza correctamente, debe corregir los errores de validación antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-123">If the validation is not successful, you must fix the validation errors before proceeding.</span></span>  

10. <span data-ttu-id="fd3ca-124">En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje reparado con cambios aceptados, haga clic en **rechazar** rechazar los cambios, o haga clic en **cancelar** Cancelar el envío y volver al formulario.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-124">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fd3ca-125">Si acepta el mensaje cambia [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] realiza validaciones del BRE en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-125">If you accept the message changes, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] performs BRE validations on the message.</span></span>  
    > 
    > [!NOTE]
    >  <span data-ttu-id="fd3ca-126">Si lo rechaza el mensaje cambia en la fase de reparación, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] enruta el mensaje en el cuadro de mensajes y publicaciones en el Visor de eventos un error que dice "no se podrían restablecer a la primera fase del flujo de trabajo.".</span><span class="sxs-lookup"><span data-stu-id="fd3ca-126">If you reject the message changes in the repair stage, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] routes the message to the MessageBox, and posts to the Event Viewer an error that reads "Could not reset to the first stage in the workflow.".</span></span>  

11. <span data-ttu-id="fd3ca-127">Si hizo clic en **Accept** o **rechazar** en el paso 10, en el **Asistente para firmas digitales** , seleccione el certificado que se va a usar para firmar el formulario (el certificado que creado para el reparador) y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-127">If you clicked **Accept** or **Reject** in step 10, on the **Digital Signature Wizard** page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="fd3ca-128">Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que desee comprobar y, a continuación, haga clic en **Ver formulario firmado**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-128">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  

12. <span data-ttu-id="fd3ca-129">En la página del Asistente para firmas digitales para escribir un comentario, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-129">On the Digital Signature Wizard page for entering a comment, click **Finish**.</span></span>  

13. <span data-ttu-id="fd3ca-130">En la página del Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión y la firma son correctos.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-130">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing and your signature are correct.</span></span> <span data-ttu-id="fd3ca-131">Haga clic en **he comprobado el contenido antes de iniciar sesión**y, a continuación, haga clic en **sesión**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-131">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="fd3ca-132">En la ventana de comprobar la firma Digital, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-132">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="fd3ca-133">En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-133">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="fd3ca-134">Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-134">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>  

17. <span data-ttu-id="fd3ca-135">En el sitio MRSR, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-135">In MRSR site, click **Documents**.</span></span> <span data-ttu-id="fd3ca-136">Si hizo clic en **Accept** para aceptar los cambios en el paso 11, compruebe que la  *\<nombre de departamento\>*_ReKeyVerify biblioteca de documentos contiene el mensaje que acaba de reparar.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-136">If you clicked **Accept** to accept the changes in step 11, verify that the *\<Department name\>*_ReKeyVerify document library contains the message that you just repaired.</span></span> <span data-ttu-id="fd3ca-137">Si hizo clic en **rechazar** para rechazar los cambios en el paso 11, compruebe que la biblioteca de documentos A4SWIFT_Outbox contiene el mensaje que se ha modificado recientemente.</span><span class="sxs-lookup"><span data-stu-id="fd3ca-137">If you clicked **Reject** to reject the changes in step 11, verify that the A4SWIFT_Outbox document library contains the message that was just modified.</span></span>
