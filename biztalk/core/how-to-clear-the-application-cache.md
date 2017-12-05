---
title: "Cómo borrar la caché de aplicaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184569a3eed693a7b699b2ad14cfb8461cc496e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="591a0-102">Cómo borrar la caché de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="591a0-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="591a0-103">Puede utilizar el Complemento MMC o la línea de comandos para quitar el contenido de la caché de credenciales (toda la información asociada a la aplicación afiliada) para una aplicación determinada en los servidores de inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="591a0-103">You can use the MMC Snap-In or the command line to remove the contents of the credential cache (all the information associated with the affiliate application) for the specified application on all of the Single Sign-On Servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="591a0-104">Para borrar la caché con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="591a0-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="591a0-105">En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="591a0-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="591a0-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="591a0-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="591a0-107">Haga clic en **aplicaciones afiliadas**.</span><span class="sxs-lookup"><span data-stu-id="591a0-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="591a0-108">En el panel de resultados, haga clic en la aplicación afiliada y haga clic en **desactive**.</span><span class="sxs-lookup"><span data-stu-id="591a0-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="591a0-109">Para borrar la caché con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="591a0-109">To clear the cache using the command line</span></span>  
  
1.  <span data-ttu-id="591a0-110">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="591a0-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="591a0-111">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="591a0-111">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="591a0-112">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="591a0-112">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="591a0-113">Tipo de **ssomanage – /purgecache  *\<nombre de la aplicación\>***, donde \< *nombre de la aplicación* \> es el nombre de la aplicación afiliada que desea purgar la memoria caché.</span><span class="sxs-lookup"><span data-stu-id="591a0-113">Type **ssomanage –purgecache *\<application name\>***, where \<*application name*\> is the name of the affiliate application you want to purge the cache for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="591a0-114">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="591a0-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591a0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="591a0-115">See Also</span></span>  
 <span data-ttu-id="591a0-116">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="591a0-116">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="591a0-117">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="591a0-117">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)