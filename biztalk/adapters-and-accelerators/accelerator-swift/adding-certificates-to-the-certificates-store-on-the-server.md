---
title: "Agregar certificados al almacén de certificados en el servidor | Documentos de Microsoft"
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
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94661568108e5a1cc05140a97c933fb8d00e3c67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a><span data-ttu-id="b8e46-102">Agregar certificados al almacén de certificados en el servidor</span><span class="sxs-lookup"><span data-stu-id="b8e46-102">Adding Certificates to the Certificates Store on the Server</span></span>
<span data-ttu-id="b8e46-103">Siga estos pasos para agregar certificados a la carpeta de otras personas en el almacén de certificados (equipo Local) en el equipo del servidor.</span><span class="sxs-lookup"><span data-stu-id="b8e46-103">Use the following steps to add certificates to the Other People folder in the Certificates (Local Computer) store on the server computer.</span></span>  
  
### <a name="to-add-certificates-to-the-certificate-store"></a><span data-ttu-id="b8e46-104">Para agregar certificados al almacén de certificados</span><span class="sxs-lookup"><span data-stu-id="b8e46-104">To add certificates to the certificate store</span></span>  
  
1.  <span data-ttu-id="b8e46-105">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Acelerador de Microsoft BizTalk para SWIFT**y, a continuación, haga clic en **Acelerador de BizTalk para SWIFT administración Consola**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BizTalk Accelerator for SWIFT Management Console**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8e46-106">Si sigue teniendo la ventana MMC abrir desde el procedimiento anterior (agregar certificados al almacén de certificados en el cliente), puede utilizarlo para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b8e46-106">If you still have the MMC window open from the previous procedure (Adding Certificates to the Certificates Store on the Client), you can use it for this procedure.</span></span>  
  
2.  <span data-ttu-id="b8e46-107">En la ventana de consola de administración, expanda la **certificados (equipo Local)** carpeta y, a continuación, expanda **otras personas**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-107">In the Administration Console window, expand the **Certificates (Local Computer)** folder, and then expand **Other People**.</span></span>  
  
3.  <span data-ttu-id="b8e46-108">Haga clic en **certificados**, seleccione **todas las tareas**y, a continuación, haga clic en **importación**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-108">Right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
4.  <span data-ttu-id="b8e46-109">En la página Asistente para la página del Asistente para importación de certificados, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-109">On the Welcome to the Certificate Import Wizard page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="b8e46-110">En la página archivo para importar, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-110">On the File to Import page, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="b8e46-111">En el cuadro de diálogo Abrir, mover a la ubicación del archivo donde se guardó el certificado, seleccione **todos los archivos** para **archivos es de tipo**, seleccione el certificado que desea importar y, a continuación, haga clic en  **Abra**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-111">In the Open dialog box, move to the file location where you have saved your certificate, select **All Files** for **Files of Type**, select the certificate that you want to import, and then click **Open**.</span></span>  
  
7.  <span data-ttu-id="b8e46-112">En la página archivo para importar, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-112">On the File to Import page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="b8e46-113">En la página almacén de certificados, compruebe que **colocar todos los certificados en el siguiente almacén** está seleccionado, compruebe que **otras personas** se muestra en el **el almacén de certificados**cuadro y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-113">On the Certificate Store page, verify that **Place all certificates in the following store** is selected, verify that **Other People** is displayed in the **Certificate Store** box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="b8e46-114">En la página Finalización la página del Asistente para importación de certificados, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-114">On the Completing the Certificate Import Wizard page, click **Finish**.</span></span>  
  
10. <span data-ttu-id="b8e46-115">En el cuadro de diálogo del Asistente para importar certificados que indica una importación correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b8e46-115">In the Certificate Import Wizard dialog box indicating a successful import, click **OK**.</span></span>  
  
11. <span data-ttu-id="b8e46-116">Repita los pasos del 3 al 10 para el resto de los certificados que se va a utilizar en la reparación de mensajes y nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="b8e46-116">Repeat steps 3 through 10 for all other certificates that you will use in message repair and new submission.</span></span>