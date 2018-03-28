---
title: Cómo mostrar las propiedades de una aplicación afiliada | Documentos de Microsoft
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3ac0c77dbaad27012f104486797c4e47d1e46be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="ea870-102">Cómo mostrar las propiedades de una aplicación afiliada</span><span class="sxs-lookup"><span data-stu-id="ea870-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="ea870-103">Este comando muestra la siguiente información acerca de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ea870-103">This command shows the following information about the affiliate application.</span></span> <span data-ttu-id="ea870-104">Para obtener más información acerca de las propiedades para una aplicación afiliada, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ea870-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="ea870-105">El sistema de SSO obtiene esta información a partir del archivo .xml empleado para actualizar la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="ea870-105">The SSO system obtains this information from the xml file that you used to update the affiliate application.</span></span> <span data-ttu-id="ea870-106">Para obtener más información, consulte [cómo actualizar las propiedades de una aplicación afiliada](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span><span class="sxs-lookup"><span data-stu-id="ea870-106">For more information, see [How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="ea870-107">Para mostrar las propiedades de una aplicación afiliada con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="ea870-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1.  <span data-ttu-id="ea870-108">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="ea870-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ea870-109">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea870-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ea870-110">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="ea870-110">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="ea870-111">Tipo ** ssomanage-displayapp *\<nombre de la aplicación\>***, donde *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea mostrar las propiedades de.</span><span class="sxs-lookup"><span data-stu-id="ea870-111">Type **ssomanage –displayapp *\<application name\>***, where *\<application name\>* is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea870-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="ea870-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="ea870-113">Para mostrar las propiedades de una aplicación afiliada con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="ea870-113">To display the properties of an affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="ea870-114">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="ea870-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ea870-115">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="ea870-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ea870-116">El directorio de instalación predeterminado es \< *unidad de instalación*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="ea870-116">The default installation directory is \<*install drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="ea870-117">Tipo ** ssoclient – displayapp *\<nombre de la aplicación\>***, donde *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea mostrar las propiedades de.</span><span class="sxs-lookup"><span data-stu-id="ea870-117">Type **ssoclient –displayapp *\<application name\>***, where *\<application name\>* is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea870-118">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="ea870-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea870-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea870-119">See Also</span></span>  
 <span data-ttu-id="ea870-120">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="ea870-120">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="ea870-121">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="ea870-121">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)