---
title: Requisitos previos para el tutorial de RosettaNet Loopback en BizTalk Server | Documentos de Microsoft
description: Requisitos previos para recorrer el tutorial de bucle invertido para el Acelerador para RosettaNet (BTARN) en BizTalk Server
caps.latest.revision: 9
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e26696c-86c5-448b-9cd6-bfd4a279151a
ms.author: mandia
ms.openlocfilehash: 9767f7823e80d4de67345ba0fbf59c1435adb8e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206964"
---
# <a name="prepare-for-the-tutorial"></a><span data-ttu-id="5a2b6-103">Prepararse para el tutorial</span><span class="sxs-lookup"><span data-stu-id="5a2b6-103">Prepare for the tutorial</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a2b6-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5a2b6-104">Prerequisites</span></span>
<span data-ttu-id="5a2b6-105">Antes de iniciar el tutorial de bucle invertido:</span><span class="sxs-lookup"><span data-stu-id="5a2b6-105">Before starting the Loopback tutorial:</span></span>
  
-   <span data-ttu-id="5a2b6-106">[Instalar y configurar](install-configure-biztalk-accelerator-for-rosettanet.md) el acelerador.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-106">[Install and configure](install-configure-biztalk-accelerator-for-rosettanet.md) the accelerator.</span></span> <span data-ttu-id="5a2b6-107">Tendrá que agregar el directorio virtual btarnhttpreceive a la lista de exclusión de la ruta de acceso administrada de Windows SharePoint en Administración Central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-107">You may have to add the btarnhttpreceive virtual directory to the Windows SharePoint managed path exclusion list in SharePoint Central Administration.</span></span>  
  
-   <span data-ttu-id="5a2b6-108">Asegúrese de que los hosts BizTalkServerIsolatedHost y AplicaciónBizTalkServer tienen la **autenticación de confianza** opción habilitada.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-108">Be sure the BizTalkServerIsolatedHost and BizTalkServerApplication hosts have the **Authentication trusted** option enabled.</span></span> <span data-ttu-id="5a2b6-109">Para comprobar, abra la consola de administración de BizTalk Server y expanda **Hosts**.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-109">To verify, open the BizTalk Server Administration console, and expand **Hosts**.</span></span> <span data-ttu-id="5a2b6-110">Haga clic en el host, seleccione **propiedades**y compruebe **autenticación de confianza** si no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-110">Right-click the host, select **Properties**, and check **Authentication Trusted** if it's not enabled.</span></span>  

    <span data-ttu-id="5a2b6-111">Si tiene más de una instancia de host, a continuación, elimine todo menos una instancia de host.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-111">If you have more than one host instance, then delete all but one host instance.</span></span> <span data-ttu-id="5a2b6-112">Por ejemplo, elimine la instancia de Host aislado de BizTalk Server y mantener la instancia de host BizTalkServerApplication).</span><span class="sxs-lookup"><span data-stu-id="5a2b6-112">For example, delete the BizTalk Server Isolated Host instance, and keep the BizTalkServerApplication host instance).</span></span> <span data-ttu-id="5a2b6-113">Este permite seleccionar **autenticación de confianza** en el host asociado a la instancia y, a continuación, volver a crear las instancias de host adicionales.</span><span class="sxs-lookup"><span data-stu-id="5a2b6-113">This lets you select **Authentication Trusted** on the host associated with that instance, and then re-create the additional host instances.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="5a2b6-114">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="5a2b6-114">Next step</span></span>
 [<span data-ttu-id="5a2b6-115">Paso 1: Crear la organización principal</span><span class="sxs-lookup"><span data-stu-id="5a2b6-115">Step 1: Create the Home Organization</span></span>](step-1-create-the-home-organization.md)