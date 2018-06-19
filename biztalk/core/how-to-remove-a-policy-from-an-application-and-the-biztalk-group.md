---
title: Cómo quitar una directiva de una aplicación y el grupo de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, policies
- managing [policies], applications
- managing [policies], deleting
- groups, policies
- managing [policies], groups
- applications, policies
ms.assetid: e9882cb3-8808-4258-a107-a24905290288
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4bb4b162d90811a4eddaa513556ecb1f6c6cd8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254516"
---
# <a name="how-to-remove-a-policy-from-an-application-and-the-biztalk-group"></a><span data-ttu-id="92f60-102">Cómo quitar una directiva de una aplicación y del grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="92f60-102">How to Remove a Policy from an Application and the BizTalk Group</span></span>
<span data-ttu-id="92f60-103">En este tema se describe cómo usar la consola de administración de BizTalk Server o la línea de comandos para quitar una directiva de una aplicación y la base de datos del motor de reglas del grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="92f60-103">This topic describes how to use the BizTalk Server Administration console or the command-line to remove a policy from an application and the Rule Engine database for the BizTalk group.</span></span>  
  
 <span data-ttu-id="92f60-104">Al quitar una directiva, tenga en cuenta los siguientes puntos importantes:</span><span class="sxs-lookup"><span data-stu-id="92f60-104">Before removing a policy, bear in mind the following important points:</span></span>  
  
-   <span data-ttu-id="92f60-105">No puede quitar una directiva implementada.</span><span class="sxs-lookup"><span data-stu-id="92f60-105">You cannot remove a deployed policy.</span></span> <span data-ttu-id="92f60-106">Debe anular la implementación de la directiva, como se describe en [cómo implementar o anular la implementación de una directiva](../core/how-to-deploy-or-undeploy-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="92f60-106">You must first undeploy the policy, as described in [How to Deploy or Undeploy a Policy](../core/how-to-deploy-or-undeploy-a-policy.md).</span></span> <span data-ttu-id="92f60-107">Al anular la implementación de una directiva, se desactiva de modo que deja de funcionar en cualquier aplicación del grupo de BizTalk que la use.</span><span class="sxs-lookup"><span data-stu-id="92f60-107">Undeploying a policy makes it inactive so that it no longer functions in any application that uses it in the BizTalk group.</span></span>  
  
-   <span data-ttu-id="92f60-108">Al quitar una directiva, se elimina de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="92f60-108">Removing a policy deletes it from the Rule Engine database.</span></span> <span data-ttu-id="92f60-109">Si desea volver a usar esta directiva, deberá exportarla a un archivo .xml antes de quitarla.</span><span class="sxs-lookup"><span data-stu-id="92f60-109">If you want to use this policy again, you should export it to an .xml file before removing it.</span></span> <span data-ttu-id="92f60-110">Para obtener instrucciones, consulte [cómo exportar una directiva](../core/how-to-export-a-policy.md).</span><span class="sxs-lookup"><span data-stu-id="92f60-110">For instructions, see [How to Export a Policy](../core/how-to-export-a-policy.md).</span></span>  
  
-   <span data-ttu-id="92f60-111">Si otras aplicaciones usan la directiva, la directiva dejará de estar activa en ellas.</span><span class="sxs-lookup"><span data-stu-id="92f60-111">If the policy is used by other applications, it will no longer be in effect for the other applications.</span></span> <span data-ttu-id="92f60-112">Antes de quitar la directiva, compruebe que no desea usarla en otras aplicaciones que hagan referencia a ella.</span><span class="sxs-lookup"><span data-stu-id="92f60-112">Verify that you no longer want to use the policy for any other applications that reference it before you remove it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="92f60-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="92f60-113">Prerequisites</span></span>  
 <span data-ttu-id="92f60-114">Para realizar el procedimiento descrito en este tema, deberá iniciar sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="92f60-114">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="92f60-115">Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="92f60-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-policy"></a><span data-ttu-id="92f60-116">Para quitar una directiva</span><span class="sxs-lookup"><span data-stu-id="92f60-116">To remove a policy</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="92f60-117">Mediante la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="92f60-117">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="92f60-118">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="92f60-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="92f60-119">En el árbol de consola, expanda **administración de BizTalk Server**, expanda el grupo de BizTalk que contiene la directiva para quitar y, a continuación, expanda la aplicación que contiene la directiva</span><span class="sxs-lookup"><span data-stu-id="92f60-119">In the console tree, expand  **BizTalk Server Administration**, expand the BizTalk group containing the policy to remove, and then expand the application containing the policy</span></span>  
  
3.  <span data-ttu-id="92f60-120">Haga clic en **directivas**, haga clic en la directiva y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="92f60-120">Click **Policies**, right-click the policy, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="92f60-121">Utilizar la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="92f60-121">Using the command line</span></span>  
  
1.  <span data-ttu-id="92f60-122">Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="92f60-122">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="92f60-123">Escriba el siguiente comando, sustituyendo los valores según corresponda, como se describe en la tabla que se presenta a continuación:</span><span class="sxs-lookup"><span data-stu-id="92f60-123">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="92f60-124">**BTSTask RemoveResource** [**/ApplicationName:***valor*] **/Luid:***valor* [  **/Server:**  *valor*] [**/Database:***valor*]</span><span class="sxs-lookup"><span data-stu-id="92f60-124">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="92f60-125">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="92f60-125">Example:</span></span>  
  
     <span data-ttu-id="92f60-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**</span><span class="sxs-lookup"><span data-stu-id="92f60-126">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"Rule/Policy1/1.0"**</span></span>  
  
    |<span data-ttu-id="92f60-127">Parámetro</span><span class="sxs-lookup"><span data-stu-id="92f60-127">Parameter</span></span>|<span data-ttu-id="92f60-128">Description</span><span class="sxs-lookup"><span data-stu-id="92f60-128">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="92f60-129">**/ ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="92f60-129">**/ApplicationName**</span></span>|<span data-ttu-id="92f60-130">Nombre de la aplicación de BizTalk que contiene la directiva que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="92f60-130">Name of the BizTalk application containing the policy to delete.</span></span> <span data-ttu-id="92f60-131">Si no se especifica este parámetro, se utiliza la aplicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="92f60-131">If this parameter is not specified, the default application is used.</span></span>|  
    |<span data-ttu-id="92f60-132">**/ Luid**</span><span class="sxs-lookup"><span data-stu-id="92f60-132">**/Luid**</span></span>|<span data-ttu-id="92f60-133">Identificador local único (LUID) de la directiva.</span><span class="sxs-lookup"><span data-stu-id="92f60-133">Locally unique identifier (LUID) of the policy.</span></span> <span data-ttu-id="92f60-134">Puede obtener el LUID mediante el **ListApp** de comandos, como se describe en [comando ListApp](../core/listapp-command.md).</span><span class="sxs-lookup"><span data-stu-id="92f60-134">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="92f60-135">**/ Servidor**</span><span class="sxs-lookup"><span data-stu-id="92f60-135">**/Server**</span></span>|<span data-ttu-id="92f60-136">Nombre de la instancia de servidor SQL Server que aloja la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="92f60-136">Name of the SQL Server instance hosting the BizTalk Management database.</span></span> <span data-ttu-id="92f60-137">Resulta necesario si se especifica el parámetro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="92f60-137">Required if you specify the Database parameter.</span></span> <span data-ttu-id="92f60-138">Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.</span><span class="sxs-lookup"><span data-stu-id="92f60-138">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
    |<span data-ttu-id="92f60-139">**/ Base de datos**</span><span class="sxs-lookup"><span data-stu-id="92f60-139">**/Database**</span></span>|<span data-ttu-id="92f60-140">Nombre de la base de datos de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="92f60-140">Name of the BizTalk Management database.</span></span> <span data-ttu-id="92f60-141">Resulta necesario si se especifica el parámetro de servidor.</span><span class="sxs-lookup"><span data-stu-id="92f60-141">Required if you specify the Server parameter.</span></span> <span data-ttu-id="92f60-142">Si no se especifican los parámetros de base de datos y servidor, se utiliza la base de datos de administración de BizTalk predeterminada para el grupo.</span><span class="sxs-lookup"><span data-stu-id="92f60-142">If Server and Database parameters are not specified, the default BizTalk Management database for the group is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="92f60-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="92f60-143">See Also</span></span>  
 [<span data-ttu-id="92f60-144">Administración de directivas</span><span class="sxs-lookup"><span data-stu-id="92f60-144">Managing Policies</span></span>](../core/managing-policies.md)