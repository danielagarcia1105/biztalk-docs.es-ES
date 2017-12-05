---
title: Administrar directivas | Documentos de Microsoft
description: "Vínculos rápidos a importar, publicar, agregar, implementar, quitar o exportar una directiva en el servidor BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dd482c2f7a226a15fe730d2b75b470a54ff27e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="manage-policies"></a><span data-ttu-id="47b67-103">Administrar directivas</span><span class="sxs-lookup"><span data-stu-id="47b67-103">Manage policies</span></span>

## <a name="overview"></a><span data-ttu-id="47b67-104">Información general</span><span class="sxs-lookup"><span data-stu-id="47b67-104">Overview</span></span>
<span data-ttu-id="47b67-105">Los temas de esta sección proporcionan instrucciones sobre el uso de la consola de administración de BizTalk Server o la herramienta de línea de comandos BTSTask para administrar directivas.</span><span class="sxs-lookup"><span data-stu-id="47b67-105">The topics in this section provide instructions on using the BizTalk Server Administration console or the BTSTask command-line tool to manage policies.</span></span> <span data-ttu-id="47b67-106">Una directiva es una agrupación lógica de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="47b67-106">A policy is a logical grouping of business rules.</span></span> <span data-ttu-id="47b67-107">Para obtener información general sobre las directivas, consulte [directivas](../core/policies.md).</span><span class="sxs-lookup"><span data-stu-id="47b67-107">For background information on policies, see [Policies](../core/policies.md).</span></span>  
  
## <a name="import-publish-deploy-and-remove-policies"></a><span data-ttu-id="47b67-108">Importar, publicar, implementar y quitar directivas</span><span class="sxs-lookup"><span data-stu-id="47b67-108">Import, publish, deploy, and remove policies</span></span>
 <span data-ttu-id="47b67-109">Los programadores de soluciones pueden crear y ver directivas mediante el Compositor de reglas de negocios, como se describe en [crear reglas de negocios mediante el Compositor de reglas de negocios](../core/creating-business-rules-using-the-business-rule-composer.md).</span><span class="sxs-lookup"><span data-stu-id="47b67-109">Solution developers can create and view policies by using the Business Rule Composer, as described in [Creating Business Rules Using the Business Rule Composer](../core/creating-business-rules-using-the-business-rule-composer.md).</span></span> <span data-ttu-id="47b67-110">Posteriormente, los programadores y administradores de TI pueden realizar las tareas que se describen en los temas de esta sección para implementar y administrar las directivas en un grupo y una aplicación de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="47b67-110">Developers and IT administrators can then perform the following tasks, which are described in the topics in this section, to deploy and manage policies in a BizTalk group and application:</span></span>  
  
-   <span data-ttu-id="47b67-111">**Importar la directiva a un grupo de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="47b67-111">**Import the policy into a BizTalk group.**</span></span> <span data-ttu-id="47b67-112">Al hacerlo, la directiva se agrega a la base de datos de motor de reglas para el grupo y se muestra en la consola de administración de BizTalk Server en el \<todos los artefactos\> nodo para el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="47b67-112">When you do this, the policy is added to the Rule Engine database for the group and displays in the BizTalk Server Administration console in the \<All Artifacts\> node for the BizTalk group.</span></span> <span data-ttu-id="47b67-113">Con esta acción, la directiva no se activa para ninguna aplicación concreta.</span><span class="sxs-lookup"><span data-stu-id="47b67-113">This does not put the policy into effect for any particular application.</span></span> <span data-ttu-id="47b67-114">En primer lugar, debe publicar la directiva, luego agregarla a una aplicación y, por último, implementarla, como se describe en otros temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="47b67-114">You must first publish the policy, add it to an application, and then deploy it, as described in other topics in this section.</span></span> <span data-ttu-id="47b67-115">La base de datos del motor de reglas es una base de datos que contiene todas las directivas de un grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="47b67-115">The Rule Engine database is a database that contains all of the policies in a BizTalk group.</span></span>  
  
-   <span data-ttu-id="47b67-116">**Publicar una directiva.**</span><span class="sxs-lookup"><span data-stu-id="47b67-116">**Publish a policy.**</span></span> <span data-ttu-id="47b67-117">al publicarse, la directiva está disponible para su uso en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="47b67-117">This makes it available to use in a BizTalk application.</span></span>  
  
-   <span data-ttu-id="47b67-118">**Agregar una directiva a una aplicación de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="47b67-118">**Add a policy to a BizTalk application.**</span></span> <span data-ttu-id="47b67-119">esto permite a la aplicación usar la directiva, pero la directiva no entra en vigor.</span><span class="sxs-lookup"><span data-stu-id="47b67-119">This allows the application to use the policy, but does not put the policy into effect.</span></span> <span data-ttu-id="47b67-120">La directiva entra en vigor cuando se implementa.</span><span class="sxs-lookup"><span data-stu-id="47b67-120">The policy takes effect when it is deployed.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="47b67-121">Si una directiva se comparte entre dos o más aplicaciones, debe crear una aplicación diferente para que la contenga y, a continuación, crear referencias a la aplicación que contiene la directiva desde las aplicaciones que la usan.</span><span class="sxs-lookup"><span data-stu-id="47b67-121">If a policy is shared across two or more applications, you should create a separate application to contain the policy and then create references from the applications that use the policy to the application containing the policy.</span></span> <span data-ttu-id="47b67-122">Esto es necesario porque al detener una aplicación que contiene una directiva, la implementación de la misma se anula automáticamente y la directiva deja de funcionar para cualquiera de las aplicaciones que la usen.</span><span class="sxs-lookup"><span data-stu-id="47b67-122">This is because if you stop an application that contains a policy, the policy is automatically undeployed and no longer functions for any of the applications that use it.</span></span>  
  
-   <span data-ttu-id="47b67-123">**Implementar una directiva.**</span><span class="sxs-lookup"><span data-stu-id="47b67-123">**Deploy a policy.**</span></span> <span data-ttu-id="47b67-124">con esto, se activa el mecanismo de la directiva.</span><span class="sxs-lookup"><span data-stu-id="47b67-124">Doing this puts it into operation.</span></span> <span data-ttu-id="47b67-125">(Es similar a iniciar a una orquestación). La implementación y anulación de la implementación de una directiva se puede realizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="47b67-125">(This is similar to starting an orchestration.) You can deploy and undeploy a policy manually.</span></span> <span data-ttu-id="47b67-126">Además, al iniciar una aplicación, las directivas correspondientes se implementan automáticamente, y cuando se detiene, se anula de forma automáticamente su implementación.</span><span class="sxs-lookup"><span data-stu-id="47b67-126">In addition, when an application is started, its policies are automatically deployed, and when an application is stopped, its policies are automatically undeployed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47b67-127">Las directivas, una vez implementadas, no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="47b67-127">Once a policy is deployed, it can no longer be modified.</span></span> <span data-ttu-id="47b67-128">Si desea modificar una directiva implementada, debe anular su implementación o volver a crearla con el Compositor de reglas de negocio y asignarle un número de versión nuevo.</span><span class="sxs-lookup"><span data-stu-id="47b67-128">If you want to modify a deployed policy, you must either undeploy it, or recreate it by using the Business Rule Composer and give it a new version number.</span></span>  
  
-   <span data-ttu-id="47b67-129">**Quitar una directiva de una aplicación de BizTalk y el grupo de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="47b67-129">**Remove a policy from a BizTalk application and the BizTalk group.**</span></span> <span data-ttu-id="47b67-130">con esta acción, se anula la implementación de la directiva; asimismo, la directiva se quita de la aplicación y de la base de datos del motor de reglas para el grupo.</span><span class="sxs-lookup"><span data-stu-id="47b67-130">This undeploys the policy and removes it from the application as well as the Rule Engine database for the group.</span></span>  
  
-   <span data-ttu-id="47b67-131">**Exportar la directiva.**</span><span class="sxs-lookup"><span data-stu-id="47b67-131">**Export the policy.**</span></span> <span data-ttu-id="47b67-132">posteriormente, puede importarla a un grupo de BizTalk distinto para usarla allí.</span><span class="sxs-lookup"><span data-stu-id="47b67-132">You can then import it into a different BizTalk group to use there.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47b67-133">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="47b67-133">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="47b67-134">Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="47b67-134">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="47b67-135">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="47b67-135">Next steps</span></span>
  
-   [<span data-ttu-id="47b67-136">Importar una directiva</span><span class="sxs-lookup"><span data-stu-id="47b67-136">Import a Policy</span></span>](../core/how-to-import-a-policy.md)  
  
-   [<span data-ttu-id="47b67-137">Publicar una directiva</span><span class="sxs-lookup"><span data-stu-id="47b67-137">Publish a Policy</span></span>](../core/how-to-publish-a-policy.md)  
  
-   [<span data-ttu-id="47b67-138">Agregar una directiva a una aplicación</span><span class="sxs-lookup"><span data-stu-id="47b67-138">Add a Policy to an Application</span></span>](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [<span data-ttu-id="47b67-139">Implementar o anular la implementación de una directiva</span><span class="sxs-lookup"><span data-stu-id="47b67-139">Deploy or Undeploy a Policy</span></span>](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [<span data-ttu-id="47b67-140">Configurar el seguimiento de una directiva</span><span class="sxs-lookup"><span data-stu-id="47b67-140">Configure Tracking for a Policy</span></span>](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [<span data-ttu-id="47b67-141">Quitar una directiva de una aplicación y del grupo de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47b67-141">Remove a Policy from an Application and the BizTalk Group</span></span>](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [<span data-ttu-id="47b67-142">Exportar una directiva</span><span class="sxs-lookup"><span data-stu-id="47b67-142">Export a Policy</span></span>](../core/how-to-export-a-policy.md)