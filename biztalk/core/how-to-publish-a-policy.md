---
title: Cómo publicar una directiva | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- managing [policies], publishing
- publishing, policies
ms.assetid: 730c57a7-526f-40ca-8610-88216558e375
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a4c272dfa76c8604224a9fc83ae888ce9b2c186
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996029"
---
# <a name="how-to-publish-a-policy"></a><span data-ttu-id="0ff19-102">Cómo publicar una directiva</span><span class="sxs-lookup"><span data-stu-id="0ff19-102">How to Publish a Policy</span></span>
<span data-ttu-id="0ff19-103">En este tema se describe cómo usar la consola de administración de BizTalk Server para publicar una directiva en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0ff19-103">This topic describes how to use the BizTalk Server Administration console to publish a policy in a BizTalk group.</span></span> <span data-ttu-id="0ff19-104">Publicar una directiva hace que esté disponible para agregar a una aplicación de BizTalk, como se describe en [cómo agregar una directiva a una aplicación](../core/how-to-add-a-policy-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="0ff19-104">Publishing a policy makes it available to add to a BizTalk application, as described in [How to Add a Policy to an Application](../core/how-to-add-a-policy-to-an-application.md).</span></span>  
  
 <span data-ttu-id="0ff19-105">Para poder publicar una directiva, ésta debe existir en la base de datos del motor de reglas del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0ff19-105">Before you can publish a policy, it must exist in the Rule Engine database for the BizTalk group.</span></span> <span data-ttu-id="0ff19-106">Existen tres formas de importar una directiva a la base de datos del motor de reglas:</span><span class="sxs-lookup"><span data-stu-id="0ff19-106">There are three ways to import a policy into the Rule Engine database:</span></span>  
  
-   <span data-ttu-id="0ff19-107">Puede importar una aplicación que contenga una directiva.</span><span class="sxs-lookup"><span data-stu-id="0ff19-107">You can import an application that contains a policy.</span></span> <span data-ttu-id="0ff19-108">Al hacerlo, la directiva se importa de forma automática a la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="0ff19-108">When you do this, the policy is automatically imported into the Rule Engine database.</span></span>  
  
-   <span data-ttu-id="0ff19-109">Puede importar explícitamente de una directiva en la base de datos de motor de reglas mediante la consola de administración o BTSTask, como se describe en [cómo importar una directiva](../core/how-to-import-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="0ff19-109">You can explicitly import a policy into the Rule Engine database by using the administration console or BTSTask, as described in [How to Import a Policy](../core/how-to-import-a-policy.md).</span></span>  
  
-   <span data-ttu-id="0ff19-110">Puede agregar una directiva a la base de datos de motor de reglas mediante el Asistente para la implementación del motor de reglas, como se describe en [cómo implementar y anular la implementación de directivas y vocabularios](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span><span class="sxs-lookup"><span data-stu-id="0ff19-110">You can add a policy to the Rule Engine database by using the Rule Engine Deployment Wizard, as described in [How to Deploy and Undeploy Policies and Vocabularies](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ff19-111">Mientras que una directiva publicada puede sobrescribirse con otra directiva importada (si especifica esta opción), un vocabulario publicado nunca puede sobrescribirse.</span><span class="sxs-lookup"><span data-stu-id="0ff19-111">While a published policy can be overwritten by another policy that you import, should you specify this option, a published vocabulary can never be overwritten.</span></span> <span data-ttu-id="0ff19-112">Para actualizar un vocabulario publicado, debe quitarlo de la base de datos del motor de reglas y, a continuación, importar la versión nueva.</span><span class="sxs-lookup"><span data-stu-id="0ff19-112">To update a published vocabulary, you must remove it from the Rule Engine database and then import the new version.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ff19-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0ff19-113">Prerequisites</span></span>  
 <span data-ttu-id="0ff19-114">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0ff19-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="0ff19-115">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="0ff19-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-publish-a-policy"></a><span data-ttu-id="0ff19-116">Para publicar una directiva</span><span class="sxs-lookup"><span data-stu-id="0ff19-116">To publish a policy</span></span>  
  
1. <span data-ttu-id="0ff19-117">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0ff19-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="0ff19-118">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk que contiene la directiva para publicar, expanda **aplicaciones**y, a continuación, expanda  **\<todos los artefactos\>**.</span><span class="sxs-lookup"><span data-stu-id="0ff19-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group containing the policy to publish, expand **Applications**, and then expand **\<All Artifacts\>**.</span></span>  
  
3. <span data-ttu-id="0ff19-119">Haga clic en **directivas**, haga clic en la directiva y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="0ff19-119">Click **Policies**, right-click the policy, and then click **Publish**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0ff19-120">Para publicar una directiva, los ensamblados que se hace referencia a la Directiva deben instalarse en la caché de ensamblados Global (GAC) de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo antes de abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="0ff19-120">In order to publish a policy, any assemblies that are referenced by the policy must be installed in the Global Assembly Cache (GAC) of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer before you open **BizTalk Server Administration**.</span></span> <span data-ttu-id="0ff19-121">Cuando **administración de BizTalk Server** está abierto, mantiene una caché de los ensamblados que se instalan en la GAC.</span><span class="sxs-lookup"><span data-stu-id="0ff19-121">When **BizTalk Server Administration** is opened, it maintains a cache of the assemblies that are installed into the GAC.</span></span> <span data-ttu-id="0ff19-122">Esta caché no se actualiza hasta que **administración de BizTalk Server** se cierra y vuelve a abrir.</span><span class="sxs-lookup"><span data-stu-id="0ff19-122">This cache is not updated until **BizTalk Server Administration** is closed and reopened.</span></span> <span data-ttu-id="0ff19-123">Si intenta publicar una directiva y se produce un error porque un ensamblado de referencia no está instalado en la GAC, debe cerrar **administración de BizTalk Server**, instale el ensamblado que se hace referencia en la GAC, abra  **Administración de BizTalk Server**y, a continuación, publica la directiva.</span><span class="sxs-lookup"><span data-stu-id="0ff19-123">If you attempt to publish a policy and publication fails because a referenced assembly is not installed in the GAC you must close **BizTalk Server Administration**, install the referenced assembly into the GAC, open **BizTalk Server Administration**, and then publish the policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ff19-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ff19-124">See Also</span></span>  
 [<span data-ttu-id="0ff19-125">Administración de directivas</span><span class="sxs-lookup"><span data-stu-id="0ff19-125">Managing Policies</span></span>](../core/managing-policies.md)