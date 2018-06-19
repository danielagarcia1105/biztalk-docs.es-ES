---
title: Cómo borrar la caché de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a897791-d32f-46a4-8c5d-2b2161e92bd9
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 24954e8314bc94d4570eb57acbf1d4b03bebb65b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250944"
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="a2908-102">Cómo borrar la caché de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a2908-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="a2908-103">Use el complemento MMC o la **/purgecache** comando para quitar el contenido de la caché de credenciales (toda la información que está asociada a la aplicación afiliada) para la aplicación especificada en todos los servidores de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="a2908-103">Use the MMC Snap-In or the **purgecache** command to remove the contents of the credential cache (all the information that is associated with the affiliate application) for the specified application on all Single Sign-On (SSO) servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="a2908-104">Para borrar la caché con el Complemento MMC</span><span class="sxs-lookup"><span data-stu-id="a2908-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="a2908-105">Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.</span><span class="sxs-lookup"><span data-stu-id="a2908-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="a2908-106">En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.</span><span class="sxs-lookup"><span data-stu-id="a2908-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="a2908-107">Haga clic en **aplicaciones afiliadas**.</span><span class="sxs-lookup"><span data-stu-id="a2908-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="a2908-108">En el panel de resultados, haga clic en la aplicación afiliada y haga clic en **desactive**.</span><span class="sxs-lookup"><span data-stu-id="a2908-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="a2908-109">Para borrar la caché con la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a2908-109">To clear the cache using the command line</span></span>  
  
1.  <span data-ttu-id="a2908-110">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="a2908-110">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="a2908-111">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a2908-111">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="a2908-112">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="a2908-112">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a2908-113">Tipo de `ssomanage –purgecache <application name>`, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada que desea purgar la caché de.</span><span class="sxs-lookup"><span data-stu-id="a2908-113">Type `ssomanage –purgecache <application name>`, where \<*application name*> is the name of the affiliate application that you want to purge the cache for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2908-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2908-114">See Also</span></span>  
 <span data-ttu-id="a2908-115">[Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a2908-115">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="a2908-116">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="a2908-116">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)