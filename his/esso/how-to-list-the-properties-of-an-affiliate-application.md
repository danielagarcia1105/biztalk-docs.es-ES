---
title: Cómo mostrar las propiedades de una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac15775-39d0-470e-b9d2-21b2d02e1de7
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: e35f1f068f63d4db9738733bcada55047e81a19a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="df5a1-102">Cómo mostrar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="df5a1-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="df5a1-103">El **displayapp** comando muestra la siguiente información acerca de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="df5a1-103">The **displayapp** command shows the following information about the affiliate application.</span></span> <span data-ttu-id="df5a1-104">Para obtener más información acerca de las propiedades para una aplicación afiliada, vea [aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="df5a1-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../esso/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="df5a1-105">El sistema de inicio de sesión único (SSO) obtiene esta información desde el archivo XML que utiliza para actualizar la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="df5a1-105">The Single Sign-On (SSO) system obtains this information from the XML file that you used to update the affiliate application.</span></span> <span data-ttu-id="df5a1-106">Para obtener más información, consulte [cómo actualizar las propiedades de una aplicación afiliada](../esso/how-to-update-the-properties-of-an-affiliate-application.md).</span><span class="sxs-lookup"><span data-stu-id="df5a1-106">For more information, see [How to Update the Properties of an Affiliate Application](../esso/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="df5a1-107">Para mostrar las propiedades de una aplicación afiliada con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="df5a1-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1.  <span data-ttu-id="df5a1-108">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="df5a1-108">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="df5a1-109">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="df5a1-109">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="df5a1-110">El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="df5a1-110">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="df5a1-111">Tipo de `ssomanage –displayapp <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea mostrar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="df5a1-111">Type `ssomanage –displayapp <application name>`, where *\<application name>* is the name of the affiliate application that you want to display the properties for.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="df5a1-112">Para mostrar las propiedades de una aplicación afiliada con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="df5a1-112">To display the properties of an affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="df5a1-113">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="df5a1-113">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="df5a1-114">En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="df5a1-114">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="df5a1-115">El directorio de instalación predeterminado es \< *unidad de instalación*>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="df5a1-115">The default installation directory is \<*install drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="df5a1-116">Tipo de `ssoclient –displayapp <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea mostrar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="df5a1-116">Type `ssoclient –displayapp <application name>`, where *\<application name>* is the name of the affiliate application that you want to display the properties for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df5a1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="df5a1-117">See Also</span></span>  
 <span data-ttu-id="df5a1-118">[Administrar asignaciones de usuario](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="df5a1-118">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="df5a1-119">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="df5a1-119">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)