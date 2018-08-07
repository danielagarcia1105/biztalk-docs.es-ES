---
title: Controla un mensaje sin analizar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- messages, unparsed messages
ms.assetid: c6a67ff3-3295-489f-9d5f-fb35b2bf8b19
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b24b7db4013e5e1f8fdb03c1278a19dc070d0e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998669"
---
# <a name="handling-an-unparsed-message"></a><span data-ttu-id="ab6c7-102">Controla un mensaje sin analizar</span><span class="sxs-lookup"><span data-stu-id="ab6c7-102">Handling an Unparsed Message</span></span>
<span data-ttu-id="ab6c7-103">En esta sección se describe cómo controlar un mensaje sin analizar.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-103">This section describes how to handle an unparsed message.</span></span> <span data-ttu-id="ab6c7-104">A diferencia de los mensajes que no superan la validación, no se puede reparar un mensaje que [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no se puede analizar.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-104">Unlike messages that fail validation, you cannot repair a message that [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] cannot parse.</span></span> <span data-ttu-id="ab6c7-105">Reparación de mensajes y nuevo envío muestra el mensaje y la naturaleza del error de análisis y le permite imprimir el mensaje o guardarlo en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-105">Message Repair and New Submission displays the message and the nature of the parsing error, and enables you to print the message or save it to a local file.</span></span> <span data-ttu-id="ab6c7-106">A continuación, puede notificar a la entidad que envió el mensaje a la naturaleza del error de análisis específica.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-106">You can then alert the entity that sent the message to the specific nature of the parsing failure.</span></span>  

### <a name="to-handle-an-unparsed-message"></a><span data-ttu-id="ab6c7-107">Para controlar un mensaje sin analizar</span><span class="sxs-lookup"><span data-stu-id="ab6c7-107">To handle an unparsed message</span></span>  

1. <span data-ttu-id="ab6c7-108">En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-108">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  

2. <span data-ttu-id="ab6c7-109">En la ventana principal, haga clic en **documentos**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-109">In the Home window, click **Documents**.</span></span>  

3. <span data-ttu-id="ab6c7-110">En la ventana de documentos en **las bibliotecas de documentos**, haga clic en **Unparsed**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-110">In the Documents window, under **Document Libraries**, click **Unparsed**.</span></span>  

4. <span data-ttu-id="ab6c7-111">En la ventana sin analizar, haga clic en **Bandeja de entrada**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-111">In the Unparsed window, click **Inbox**.</span></span>  

5. <span data-ttu-id="ab6c7-112">En la ventana de la Bandeja de entrada sin analizar, seleccione el mensaje que no se ha sido analizar, haga clic en la flecha situada a la derecha del mensaje y, a continuación, haga clic en **editar en Microsoft Office InfoPath**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-112">In the Unparsed Inbox window, point to the message that did not parse, click the arrow to the right of the message, and then click **Edit in Microsoft Office InfoPath**.</span></span>  

6. <span data-ttu-id="ab6c7-113">En el panel del Acelerador de SWIFT, haga clic en **errores**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-113">In the SWIFT Accelerator pane, click **Errors**.</span></span>  

7. <span data-ttu-id="ab6c7-114">En el panel de análisis y errores de validación XML, lea el error de análisis.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-114">In the Parse and XML Validation Errors pane, read the parse error.</span></span>  

8. <span data-ttu-id="ab6c7-115">En el panel de mensajes sin analizar, revise el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-115">In the Unparsed Message pane, review the message.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ab6c7-116">Si desea imprimir el mensaje, en el panel de mensajes sin analizar, en el **archivo** menú, haga clic en **imprimir**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-116">If you want to print the message, in the Unparsed Message pane, on the **File** menu, click **Print**.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ab6c7-117">Si desea guardar el mensaje en un archivo local, en el panel de mensajes sin analizar, en el **archivo** menú, haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-117">If you want to save the message to a local file, in the Unparsed Message pane, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="ab6c7-118">En el **Guardar como** cuadro de diálogo el **guardar en** lista desplegable, desplácese a la carpeta que desea guardar el archivo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-118">In the **Save As** dialog box, in the **Save in** drop-down list, move to the folder that you want to save the file in, and then click **OK**.</span></span> [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="ab6c7-119"> guarda el mensaje en formato XML.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-119"> saves the message in XML format.</span></span>  

9. <span data-ttu-id="ab6c7-120">En el panel de mensajes sin analizar, realice los cambios necesarios y, a continuación, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-120">In the Unparsed Message pane, make the necessary changes, and then click **Submit**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ab6c7-121">No se puede validar un mensaje sin analizar que se ha reparado.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-121">You cannot validate an unparsed message that you have repaired.</span></span>  

10. <span data-ttu-id="ab6c7-122">En el cuadro de diálogo Enviar mensaje, haga clic en **Accept** para enviar el mensaje reparado con cambios aceptados, haga clic en **rechazar** rechazar los cambios, o haga clic en **cancelar** Cancelar el envío y volver al formulario.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-122">In the Submit Message dialog box, click **Accept** to submit the repaired message with changes accepted, click **Reject** to reject the changes, or click **Cancel** to cancel the submission and return to the form.</span></span>  

11. <span data-ttu-id="ab6c7-123">Si hizo clic en **Accept** o **rechazar** en el paso 11, en la página del Asistente para la firma Digital, seleccione el certificado que desea utilizar para firmar el formulario (el certificado que ha creado para el taller de reparación) y, a continuación, Haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-123">If you clicked **Accept** or **Reject** in step 11, on the Digital Signature Wizard page, select the certificate that you want to use to sign the form (the certificate that you created for the repairer), and then click **Next**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ab6c7-124">Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que desee comprobar y, a continuación, haga clic en **Ver formulario firmado**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-124">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="ab6c7-125">Cualquier usuario que realiza cualquier rol puede enviar un mensaje sin analizar que ha reparado.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-125">Any user performing any role can submit an unparsed message that they have repaired.</span></span>  

12. <span data-ttu-id="ab6c7-126">En la página del Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-126">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  

13. <span data-ttu-id="ab6c7-127">En la página del Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-127">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="ab6c7-128">Haga clic en **Ver certificado** si desea comprobar que está usando la firma correcta.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-128">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="ab6c7-129">Haga clic en **he comprobado el contenido antes de iniciar sesión**y, a continuación, haga clic en **sesión**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-129">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  

14. <span data-ttu-id="ab6c7-130">En la ventana de comprobar la firma Digital, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-130">In the Verify Digital Signature window, click **Close**.</span></span>  

15. <span data-ttu-id="ab6c7-131">En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-131">In the Submission Success dialog box, click **OK**.</span></span>  

16. <span data-ttu-id="ab6c7-132">Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="ab6c7-132">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>
