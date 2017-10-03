---
title: "Cómo deshabilitar SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c8069ffb291b64d832a1d3ce483e7ab09be655f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-sso"></a><span data-ttu-id="67964-102">Cómo deshabilitar SSO</span><span class="sxs-lookup"><span data-stu-id="67964-102">How to Disable SSO</span></span>
<span data-ttu-id="67964-103">Se puede deshabilitar la totalidad del sistema de inicio de sesión único utilizando el Complemento MMC o la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="67964-103">You can disable the entire Single Sign-On system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="67964-104">Habrá un breve retraso hasta que se deshabiliten todos los servidores de inicio de sesión único, puesto que efectúan un sondeo de la base de datos de SSO para la obtención de la información global más reciente.</span><span class="sxs-lookup"><span data-stu-id="67964-104">There will be a short delay for all Single Sign-On Servers to be disabled, as they poll the SSO database for the latest global information.</span></span>  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a><span data-ttu-id="67964-105">Para deshabilitar el inicio de sesión único empresarial con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="67964-105">To disable Enterprise Single Sign-On using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="67964-106">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="67964-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="67964-107">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="67964-107">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="67964-108">Haga clic en **System**y, a continuación, haga clic en **deshabilitar**.</span><span class="sxs-lookup"><span data-stu-id="67964-108">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a><span data-ttu-id="67964-109">Para deshabilitar el inicio de sesión único empresarial con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="67964-109">To disable Enterprise Single Sign-On using the command line</span></span>  
  
1.  <span data-ttu-id="67964-110">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="67964-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="67964-111">En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="67964-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="67964-112">El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="67964-112">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="67964-113">Tipo de **ssomanage – disablesso**.</span><span class="sxs-lookup"><span data-stu-id="67964-113">Type **ssomanage –disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="67964-114">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="67964-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67964-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="67964-115">See Also</span></span>  
 <span data-ttu-id="67964-116">[Cómo habilitar SSO](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="67964-116">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 [<span data-ttu-id="67964-117">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="67964-117">Using SSO</span></span>](../core/using-sso.md)