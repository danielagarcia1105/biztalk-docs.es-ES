---
title: "Cómo registrar y quitar el Visor de ensamblado de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f80b906-0a9e-4bcd-984d-db4550f2e51f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ad3628f61fec11f135bf2235f5e0d25f52992d3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-register-and-remove-the-biztalk-assembly-viewer"></a><span data-ttu-id="33040-102">Cómo registrar y quitar el Visor de ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="33040-102">How to Register and Remove the BizTalk Assembly Viewer</span></span>
<span data-ttu-id="33040-103">El Visor de ensamblado de BizTalk no se registra automáticamente durante la instalación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="33040-103">The BizTalk Assembly Viewer is not registered automatically during BizTalk Server setup.</span></span> <span data-ttu-id="33040-104">Para registrar y quitar el Visor de ensamblado de BizTalk, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="33040-104">To register or remove the BizTalk Assembly Viewer, follow these steps.</span></span>  
  
### <a name="to-add-assembly-viewer-to-the-windows-registry"></a><span data-ttu-id="33040-105">Para agregar el Visor de ensamblado al Registro de Windows</span><span class="sxs-lookup"><span data-stu-id="33040-105">To add Assembly Viewer to the Windows registry</span></span>  
  
1.  <span data-ttu-id="33040-106">Desde el **iniciar** menú, haga clic en **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="33040-106">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="33040-107">En el cuadro de diálogo Ejecutar, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="33040-107">In the Run dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="33040-108">Desde la línea de comandos, vaya a \< *carpeta de instalación de BizTalk Server*\>\Developer Tools\ donde se encuentra BTSAsmExt.dll.</span><span class="sxs-lookup"><span data-stu-id="33040-108">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="33040-109">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="33040-109">At the command line, type:</span></span>  
  
     <span data-ttu-id="33040-110">regsvr32 BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="33040-110">regsvr32 BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="33040-111">Para comenzar a usar la vista Ensamblado, cierre sesión y, a continuación, vuelva a iniciarla en el equipo.</span><span class="sxs-lookup"><span data-stu-id="33040-111">To begin using Assembly View, log off and then log back onto the computer.</span></span>  
  
### <a name="to-remove-assembly-viewer-from-the-windows-registry"></a><span data-ttu-id="33040-112">Para quitar el Visor de ensamblado del Registro de Windows</span><span class="sxs-lookup"><span data-stu-id="33040-112">To remove Assembly Viewer from the Windows registry</span></span>  
  
1.  <span data-ttu-id="33040-113">Desde el **iniciar** menú, haga clic en **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="33040-113">From the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="33040-114">En el **ejecutar** cuadro de diálogo, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="33040-114">In the **Run** dialog box, type **cmd**.</span></span>  
  
3.  <span data-ttu-id="33040-115">Desde la línea de comandos, vaya a \< *carpeta de instalación de BizTalk Server*\>\Developer Tools\ donde se encuentra BTSAsmExt.dll.</span><span class="sxs-lookup"><span data-stu-id="33040-115">From the command line, navigate to \<*BizTalk Server Installation Folder*\>\Developer Tools\ where BTSAsmExt.dll resides.</span></span>  
  
4.  <span data-ttu-id="33040-116">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="33040-116">At the command line, type:</span></span>  
  
     <span data-ttu-id="33040-117">regsvr32/u BTSAsmExt.dll</span><span class="sxs-lookup"><span data-stu-id="33040-117">regsvr32/u BTSAsmExt.dll</span></span>  
  
5.  <span data-ttu-id="33040-118">Para completar la eliminación, cierre sesión y, a continuación, vuelva a iniciarla en el equipo.</span><span class="sxs-lookup"><span data-stu-id="33040-118">To complete the removal, log off and then log back onto the computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33040-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="33040-119">See Also</span></span>  
 [<span data-ttu-id="33040-120">Visualización de ensamblados con el Visor de ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="33040-120">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)