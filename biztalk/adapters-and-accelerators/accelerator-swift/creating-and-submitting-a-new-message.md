---
title: Crear y enviar un nuevo mensaje | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- submitting, messages
- messages, submitting
- messages, creating
ms.assetid: 88b7a2d3-44a4-44e4-ba8c-527c10290925
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42cd2a82fe0ecde75446e68f9f58e17f103e5efa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-submitting-a-new-message"></a><span data-ttu-id="2dcf5-102">Crear y enviar un mensaje nuevo</span><span class="sxs-lookup"><span data-stu-id="2dcf5-102">Creating and Submitting a New Message</span></span>
<span data-ttu-id="2dcf5-103">Esta sección describe cómo enviar un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-103">This section describes how to submit a new message.</span></span> <span data-ttu-id="2dcf5-104">Como con un mensaje reparado, un nuevo mensaje debe ser verificado y aprobado por personas que no sean el creador del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-104">As with a repaired message, a new message must be verified and approved by people other than the message creator.</span></span>  
  
 <span data-ttu-id="2dcf5-105">Para enviar un mensaje nuevo, debe cargar en la biblioteca de documentos de nuevos mensajes de SWIFT un archivo de plantilla de mensaje para el tipo de mensaje que desea enviar.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-105">To submit a new message, you must upload into the New SWIFT Messages document library a message template file for the type of message that you want to submit.</span></span> <span data-ttu-id="2dcf5-106">Puede cargar una plantilla de mensaje único manualmente, o puede cargar todas las plantillas de mensaje mediante la herramienta FormPublish.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-106">You can upload a single message template manually, or you can upload all message templates using the FormPublish tool.</span></span>  
  
### <a name="to-upload-a-single-message-template-into-the-new-document-library"></a><span data-ttu-id="2dcf5-107">Para cargar una plantilla de mensaje único en la nueva biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="2dcf5-107">To upload a single message template into the new document library</span></span>  
  
1.  <span data-ttu-id="2dcf5-108">Consulte la sección [formulario Generador de utilidad para generar los formularios de InfoPath MT/MX](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-108">Refer to the section [Form Generator Utility to Generate MT/MX InfoPath Forms](../../adapters-and-accelerators/accelerator-swift/form-generator-utility-to-generate-mt-mx-infopath-forms.md) for instructions.</span></span>  
  
### <a name="to-create-and-submit-a-new-message"></a><span data-ttu-id="2dcf5-109">Para crear y enviar un mensaje nuevo</span><span class="sxs-lookup"><span data-stu-id="2dcf5-109">To create and submit a new message</span></span>  
  
1.  <span data-ttu-id="2dcf5-110">En Internet Explorer, abra el sitio MRSR en http://localhost/sites/bassite.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-110">In Internet Explorer, open your MRSR site at http://localhost/sites/bassite.</span></span>  
  
2.  <span data-ttu-id="2dcf5-111">Haga clic en **documentos**y, a continuación, haga clic en **nuevos mensajes de SWIFT**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-111">Click **Documents**, and then click **New SWIFT Messages**.</span></span>  
  
3.  <span data-ttu-id="2dcf5-112">En la página nuevos mensajes de SWIFT, haga doble clic en el nombre de la categoría que contiene el tipo del mensaje que le gustaría crear.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-112">On the New SWIFT Messages page, double-click the name of the category containing the type of the message that you would like to create.</span></span>  
  
4.  <span data-ttu-id="2dcf5-113">Haga clic en la plantilla de formulario para el mensaje que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-113">Click the form template for the message that you want to create.</span></span>  
  
5.  <span data-ttu-id="2dcf5-114">En el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formar de ventana de 2007, en el mensaje, datos de mensajes de tipo para todos los campos necesarios (como se indican con un asterisco) y los campos opcionales que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-114">In the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 2007 window, in the message form, type message data for all required fields (as denoted by an asterisk) and any optional fields you want to use.</span></span>  
  
6.  <span data-ttu-id="2dcf5-115">Para buscar un BIC, en la función actual: crear el panel, haga clic en **búsqueda BIC**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-115">To look up a BIC, in the Current Role: Create pane, click **BIC Lookup**.</span></span>  
  
7.  <span data-ttu-id="2dcf5-116">Escriba el nombre de la institución financiera, el código del banco y el país o región y, a continuación, haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-116">Type the name of the financial institution, the bank code, and the country/region, and then click **Search**.</span></span>  
  
8.  <span data-ttu-id="2dcf5-117">En el panel de búsqueda BIC, copie el BIC en el campo de código bancaria apropiado en el formulario del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-117">From the BIC Lookup pane, copy the BIC into the appropriate bank code field in the message form.</span></span>  
  
9. <span data-ttu-id="2dcf5-118">En la función actual: crear el panel, haga clic en **validación**y, a continuación, haga clic en **mensaje Validate**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-118">In the Current Role: Create pane, click **Validation**, and then click **Validate Message**.</span></span>  
  
10. <span data-ttu-id="2dcf5-119">En el panel de resultados de la función actual: crear panel, determinar los errores que deba solucionar en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-119">In the Results pane of the Current Role: Create pane, determine the errors that you need to fix in the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2dcf5-120">Sólo puede enviar un nuevo mensaje si haya corregido todos los errores de validación en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-120">You can only submit a new message if you have fixed all validation errors in the message.</span></span>  
  
11. <span data-ttu-id="2dcf5-121">En la barra de herramientas estándar en la parte superior de la ventana, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-121">From the Standard toolbar at the top of the window, click **Submit**.</span></span>  
  
12. <span data-ttu-id="2dcf5-122">En la página Asistente para firmas digitales para seleccionar el certificado para firmar el formulario, seleccione el certificado que desea utilizar para firmar el formulario (es decir, el certificado que ha creado para el creador).</span><span class="sxs-lookup"><span data-stu-id="2dcf5-122">On the Digital Signature Wizard page for selecting the certificate to sign the form, select the certificate that you want to use to sign the form (the certificate that you created for the creator).</span></span> <span data-ttu-id="2dcf5-123">Haga clic en **Ver certificado** si desea comprobar que se usa la firma correcta.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-123">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="2dcf5-124">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-124">Click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2dcf5-125">Para comprobar la validez de una firma digital, haga clic en **firmas digitales** en el **herramientas** menú, haga clic en la firma digital que se desea comprobar y, a continuación, haga clic en **Ver formulario firmado**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-125">To verify the validity of a digital signature, click **Digital Signatures** on the **Tools** menu, click the digital signature that you want to verify, and then click **View Signed Form**.</span></span>  
  
13. <span data-ttu-id="2dcf5-126">En la página Asistente para firmas digitales para escribir comentarios, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-126">On the Digital Signature Wizard page for entering comments, click **Finish**.</span></span>  
  
14. <span data-ttu-id="2dcf5-127">En la página Asistente para firmas digitales para comprobar el formulario, compruebe que el mensaje que se va a iniciar sesión es correcto.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-127">On the Digital Signature Wizard page for verifying the form, verify that the message that you are signing is correct.</span></span> <span data-ttu-id="2dcf5-128">Haga clic en **Ver certificado** si desea comprobar que se usa la firma correcta.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-128">Click **View Certificate** if you want to verify that you are using the correct signature.</span></span> <span data-ttu-id="2dcf5-129">Haga clic en **he comprobado el contenido antes de la firma**y, a continuación, haga clic en **inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-129">Click **I have verified this content before signing**, and then click **Sign**.</span></span>  
  
15. <span data-ttu-id="2dcf5-130">En la ventana de comprobar la firma Digital, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-130">In the Verify Digital Signature window, click **Close**.</span></span>  
  
16. <span data-ttu-id="2dcf5-131">En el cuadro de diálogo de éxito de envío, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-131">In the Submission Success dialog box, click **OK**.</span></span>  
  
17. <span data-ttu-id="2dcf5-132">Cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] ventana.</span><span class="sxs-lookup"><span data-stu-id="2dcf5-132">Close the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] window.</span></span>