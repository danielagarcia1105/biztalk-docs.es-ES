---
title: "Agregar certificados al almacén de certificados en el cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 9e2722ee-dd6f-4b14-9796-2f2157e8cad2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a2e01fa60eccc8a6a0f06f4cf1f9fafb3f982b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-certificates-to-the-certificates-store-on-the-client"></a><span data-ttu-id="db4d8-102">Agregar certificados al almacén de certificados en el cliente</span><span class="sxs-lookup"><span data-stu-id="db4d8-102">Adding Certificates to the Certificates Store on the Client</span></span>
<span data-ttu-id="db4d8-103">Siga estos pasos para agregar certificados a la carpeta Personal en el almacén de certificados en cada equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="db4d8-103">Use the following steps to add certificates to the Personal folder in the certificates store on each client computer.</span></span> <span data-ttu-id="db4d8-104">Los certificados deben agregarse a la carpeta Personal de los certificados: almacén del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="db4d8-104">The certificates must be added to the Personal folder in the Certificates - Current User store.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="db4d8-105">Si los certificados no se distribuyen a través de una empresa entidad emisora de certificados de confianza, debe importar el certificado de raíz de la entidad de certificación en los equipos cliente.</span><span class="sxs-lookup"><span data-stu-id="db4d8-105">If your certificates are not distributed via an enterprise trusted Certification Authority, you must import the Certification Authority's root certificate onto the client computer(s).</span></span> <span data-ttu-id="db4d8-106">En caso contrario, los certificados personales no funcionará.</span><span class="sxs-lookup"><span data-stu-id="db4d8-106">Otherwise, your personal certificates will not work.</span></span> <span data-ttu-id="db4d8-107">Importar el certificado de la entidad de certificación en la carpeta entidades emisoras raíz de confianza en el nodo certificados (equipo Local).</span><span class="sxs-lookup"><span data-stu-id="db4d8-107">Import the Certification Authority's certificate into the Trusted Root Certification Authorities folder in the Certificates (Local Computer) node.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="db4d8-108">Para agregar certificados al almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="db4d8-108">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="db4d8-109">Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-109">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="db4d8-110">Escriba **mmc**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-110">Enter **mmc**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="db4d8-111">En el cuadro de diálogo Consola1, haga clic en **archivo**y, a continuación, haga clic en **agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-111">In the Console1 dialog box, click **File**, and then click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="db4d8-112">En el cuadro de diálogo Agregar o quitar complemento, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-112">In the Add/Remove Snap-in dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="db4d8-113">En el cuadro de diálogo Add Standalone Snap-in, haga clic en **certificados**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-113">In the Add Standalone Snap-in dialog box, click **Certificates**, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="db4d8-114">En el cuadro de diálogo del complemento de certificados, haga clic en **mi cuenta de usuario**y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-114">In the Certificates snap-in dialog box, click **My user account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="db4d8-115">En el cuadro de diálogo Add Standalone Snap-in, haga clic en **certificados**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-115">In the Add Standalone Snap-in dialog box, click **Certificates**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="db4d8-116">En el cuadro de diálogo del complemento de certificados, haga clic en **cuenta de equipo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-116">In the Certificates snap-in dialog box, click **Computer account**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="db4d8-117">En el cuadro de diálogo Seleccionar equipo, asegúrese de que **equipo Local** está seleccionada y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-117">In the Select Computer dialog box, make sure **Local computer** is selected, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="db4d8-118">En el cuadro de diálogo Add Standalone Snap-in, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-118">In the Add Standalone Snap-in dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="db4d8-119">En el cuadro de diálogo Agregar o quitar complemento, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-119">In the Add/Remove Snap-in dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="db4d8-120">En el **raíz de consola** panel del cuadro de diálogo Consola1, expanda el **certificados - usuario actual** carpetas.</span><span class="sxs-lookup"><span data-stu-id="db4d8-120">In the **Console Root** pane of the Console1 dialog box, expand the **Certificates - Current User** folders.</span></span>  
  
12. <span data-ttu-id="db4d8-121">En **certificados - usuario actual**, expanda **Personal**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-121">Under **Certificates - Current User**, expand **Personal**.</span></span>  
  
13. <span data-ttu-id="db4d8-122">Haga clic en **certificados**, seleccione **todas las tareas**y, a continuación, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-122">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
14. <span data-ttu-id="db4d8-123">En la página Asistente para la página del Asistente para importación de certificados, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-123">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
15. <span data-ttu-id="db4d8-124">En la página archivo para importar, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-124">On the File to Import page, click **Browse**.</span></span>  
  
16. <span data-ttu-id="db4d8-125">En el cuadro de diálogo Abrir, mover a la ubicación del archivo donde se guardó el certificado, seleccione **todos los archivos** para **archivos es de tipo**, seleccione el certificado que desea importar y, a continuación, haga clic en  **Abra**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-125">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
17. <span data-ttu-id="db4d8-126">En la página archivo para importar, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-126">On the File to Import page, click **Next**.</span></span>  
  
18. <span data-ttu-id="db4d8-127">En la página almacén de certificados, compruebe que **colocar todos los certificados en el siguiente almacén** está seleccionado, compruebe que **Personal** se muestra en el **almacén de certificados** cuadro y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-127">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Personal** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
19. <span data-ttu-id="db4d8-128">En la página Finalización la página del Asistente para importación de certificados, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-128">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
20. <span data-ttu-id="db4d8-129">En el cuadro de diálogo del Asistente para importar certificados que indica una importación correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db4d8-129">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
21. <span data-ttu-id="db4d8-130">Repita los pasos 13 al 20 para todos los demás certificados que se va a utilizar en la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="db4d8-130">Repeat steps 13 through 20 for all other certificates that you will use in message repair and new submission.</span></span>