---
title: Cómo quitar SSO | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, deleting
- SSO, deleting
- deleting, SSO
- deleting, Master Secret server
ms.assetid: 0e1ad8e3-0938-4f36-b85b-4631d0eeb8c9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb712972c0fd7ba8975f30ee6519812dd863e442
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004109"
---
# <a name="how-to-remove-sso"></a><span data-ttu-id="a1eaa-102">Cómo quitar el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="a1eaa-102">How to Remove SSO</span></span>
<span data-ttu-id="a1eaa-103">Si se quita BizTalk Server, el inicio de sesión único (SSO) empresarial deja de estar configurado a menos que haya un programa dependiente que lo utilice.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-103">If you remove BizTalk Server, Enterprise Single Sign-On (SSO) is no longer configured unless a dependent product is using it.</span></span> <span data-ttu-id="a1eaa-104">No obstante, no se quita.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-104">However, it is not removed.</span></span> <span data-ttu-id="a1eaa-105">Debe quitar SSO por separado.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-105">You must remove SSO separately.</span></span> <span data-ttu-id="a1eaa-106">Asimismo, se puede restaurar la información de configuración, incluido el secreto principal, para reutilizar los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-106">You can also restore configuration information including the master secret to reuse existing data.</span></span> <span data-ttu-id="a1eaa-107">Para obtener más información, consulte [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="a1eaa-107">For more information, see [How to Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="to-remove-enterprise-single-sign-on"></a><span data-ttu-id="a1eaa-108">Para quitar el inicio de sesión único empresarial</span><span class="sxs-lookup"><span data-stu-id="a1eaa-108">To remove Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="a1eaa-109">Haga una copia de seguridad de la clave secreta principal.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-109">Back up the master secret key.</span></span> <span data-ttu-id="a1eaa-110">Para obtener más información, consulte [cómo volver seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).</span><span class="sxs-lookup"><span data-stu-id="a1eaa-110">For more information, see [How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2. <span data-ttu-id="a1eaa-111">Desinstale [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1eaa-111">Uninstall [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3. <span data-ttu-id="a1eaa-112">En el menú **Inicio** , haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
4. <span data-ttu-id="a1eaa-113">Haga clic en **agregar o quitar programas**.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-113">Click **Add/Remove Programs**.</span></span>  
  
5. <span data-ttu-id="a1eaa-114">En el **agregar o quitar programas** cuadro de diálogo, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-114">In the **Add/Remove Programs** dialog box, click **Microsoft Enterprise Single Sign-On**, and then click **Remove**.</span></span>  
  
6. <span data-ttu-id="a1eaa-115">Haga clic en **Sí** cuando se le pida que confirme la eliminación de Microsoft Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-115">Click **Yes** when prompted to confirm the removal of Microsoft Enterprise Single Sign-On.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a1eaa-116">Si tiene instaladas las características Administración, Desarrollo y Tiempo de ejecución de BizTalk Server, o las características de administración de Host Integration Server, no será posible desinstalar los componentes Administración y Tiempo de ejecución de SSO hasta que se quiten todas las dependencias.</span><span class="sxs-lookup"><span data-stu-id="a1eaa-116">If you have BizTalk Server Runtime, Development, or Administration features installed, or Host Integration Server Administration features installed, you will not be able to uninstall the SSO Runtime or Administration components until all dependencies are removed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1eaa-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1eaa-117">See Also</span></span>  
 [<span data-ttu-id="a1eaa-118">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="a1eaa-118">Installing SSO</span></span>](../core/installing-sso.md)