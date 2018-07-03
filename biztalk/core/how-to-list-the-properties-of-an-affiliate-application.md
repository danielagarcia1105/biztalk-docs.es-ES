---
title: Cómo enumerar las propiedades de una aplicación afiliada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], listing properties
- managing [SSO applications], listing properties
ms.assetid: a120acd7-2f0b-4c72-8a8a-f8e500a773c8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5920263006a9188da83f82dcf65dad8fb8faada
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002725"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="aaf0b-102">Cómo enumerar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="aaf0b-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="aaf0b-103">Este comando muestra la siguiente información acerca de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-103">This command shows the following information about the affiliate application.</span></span> <span data-ttu-id="aaf0b-104">Para obtener más información acerca de las propiedades de una aplicación afiliada, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="aaf0b-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="aaf0b-105">El sistema de SSO obtiene esta información a partir del archivo .xml empleado para actualizar la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-105">The SSO system obtains this information from the xml file that you used to update the affiliate application.</span></span> <span data-ttu-id="aaf0b-106">Para obtener más información, consulte [cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span><span class="sxs-lookup"><span data-stu-id="aaf0b-106">For more information, see [How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="aaf0b-107">Para mostrar las propiedades de una aplicación afiliada con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="aaf0b-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1. <span data-ttu-id="aaf0b-108">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="aaf0b-109">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aaf0b-110">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-110">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="aaf0b-111">Tipo ** ssomanage-displayapp *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea mostrar el propiedades de.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-111">Type **ssomanage –displayapp *\<application name\>**<em>, where *\<application name\></em> is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aaf0b-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="aaf0b-113">Para mostrar las propiedades de una aplicación afiliada con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="aaf0b-113">To display the properties of an affiliate application using the client utility</span></span>  
  
1. <span data-ttu-id="aaf0b-114">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="aaf0b-115">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aaf0b-116">El directorio de instalación predeterminado es \< *unidad de instalación*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-116">The default installation directory is \<*install drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="aaf0b-117">Tipo ** ssoclient – displayapp *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea mostrar el propiedades de.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-117">Type **ssoclient –displayapp *\<application name\>**<em>, where *\<application name\></em> is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aaf0b-118">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="aaf0b-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaf0b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aaf0b-119">See Also</span></span>  
 <span data-ttu-id="aaf0b-120">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="aaf0b-120">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="aaf0b-121">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="aaf0b-121">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)