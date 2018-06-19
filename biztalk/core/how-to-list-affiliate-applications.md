---
title: Cómo enumerar aplicaciones afiliadas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6c4d4e4118bfe5f5cab7a9c44e770dd12656c7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974154"
---
# <a name="how-to-list-affiliate-applications"></a><span data-ttu-id="0796e-102">Cómo enumerar aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="0796e-102">How to List Affiliate Applications</span></span>
<span data-ttu-id="0796e-103">Utilice este comando para enumerar todas las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="0796e-103">Use this command to list all the affiliate applications.</span></span> <span data-ttu-id="0796e-104">Si el usuario es miembro de la cuenta de administradores de aplicación, este comando sólo mostrará la aplicación para la que el usuario es administrador.</span><span class="sxs-lookup"><span data-stu-id="0796e-104">If the user is a member of the Application Administrators account, this command will only display the application for which the user is an administrator.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a><span data-ttu-id="0796e-105">Para enumerar las aplicaciones afiliadas con la utilidad de administración</span><span class="sxs-lookup"><span data-stu-id="0796e-105">To list affiliate applications using the administration utility</span></span>  
  
1.  <span data-ttu-id="0796e-106">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="0796e-106">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="0796e-107">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="0796e-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0796e-108">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="0796e-108">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="0796e-109">Tipo de **ssomanage - listapps [all]** donde **todos los** es un parámetro opcional que se mostrará también las aplicaciones que usan la característica de almacén de configuración.</span><span class="sxs-lookup"><span data-stu-id="0796e-109">Type **ssomanage -listapps [all]** where **all** is an optional parameter that will also display applications using the Configuration Store feature.</span></span> <span data-ttu-id="0796e-110">Si el usuario que ejecuta este comando es un administrador de aplicaciones, sólo se enumerarán las aplicaciones para las que es administrador.</span><span class="sxs-lookup"><span data-stu-id="0796e-110">If the user running this command is an Application administrator, it will only list the applications for which they are an administrator.</span></span> <span data-ttu-id="0796e-111">Si el usuario que ejecuta este comando es un administrador afiliado o un administrador de SSO, se enumerarán todas las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="0796e-111">If the user running this command is an Affiliate Administrator or an SSO Administrator, it will list all the affiliate applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0796e-112">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="0796e-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a><span data-ttu-id="0796e-113">Para enumerar las aplicaciones afiliadas con la utilidad de cliente</span><span class="sxs-lookup"><span data-stu-id="0796e-113">To list affiliate applications using the client utility</span></span>  
  
1.  <span data-ttu-id="0796e-114">En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="0796e-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="0796e-115">En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial.</span><span class="sxs-lookup"><span data-stu-id="0796e-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0796e-116">El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.</span><span class="sxs-lookup"><span data-stu-id="0796e-116">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="0796e-117">Tipo de **ssoclient – listapps** para enumerar las aplicaciones afiliadas.</span><span class="sxs-lookup"><span data-stu-id="0796e-117">Type **ssoclient –listapps** to list the affiliate applications.</span></span> <span data-ttu-id="0796e-118">Se enumerarán sólo las aplicaciones afiliadas de las que el usuario que realiza esta tarea es miembro, por ejemplo, será necesario que pertenezcan a la cuenta de grupo de usuarios de la aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="0796e-118">This will list only the affiliate applications that the user performing this task is a member of, i.e., they need to belong the application user group account for that affiliate application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0796e-119">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="0796e-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0796e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0796e-120">See Also</span></span>  
 <span data-ttu-id="0796e-121">[Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0796e-121">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="0796e-122">[Cómo crear una aplicación afiliada](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="0796e-122">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="0796e-123">[Administrar asignaciones de usuario](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="0796e-123">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="0796e-124">Administración de aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="0796e-124">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)