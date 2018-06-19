---
title: Cómo mantener versiones de directivas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c73b3575ec484ab611fccac920cef6d96d3800
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254500"
---
# <a name="how-to-maintain-policy-versions"></a><span data-ttu-id="237a0-102">Cómo mantener versiones de directivas</span><span class="sxs-lookup"><span data-stu-id="237a0-102">How to Maintain Policy Versions</span></span>
<span data-ttu-id="237a0-103">Después de agregar reglas a una versión de la directiva, puede guardar la versión en el almacén de reglas para su posterior desarrollo, o puede publicarla para crear un conjunto de reglas bien definido e inmutable que pueda ser implementado para su utilización en una aplicación basada en reglas.</span><span class="sxs-lookup"><span data-stu-id="237a0-103">After you add rules to a version of your policy, you can save the version to the rule store for further development, or you can publish it to create a well-defined, immutable set of rules that can be deployed for use in a rule-based application.</span></span>  
  
 <span data-ttu-id="237a0-104">Este tema contiene procedimientos para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="237a0-104">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="237a0-105">Para crear una nueva versión vacía de una directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-105">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="237a0-106">Para guardar una versión de directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-106">To save a policy version</span></span>  
  
-   <span data-ttu-id="237a0-107">Para publicar una versión de directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-107">To publish a policy version</span></span>  
  
-   <span data-ttu-id="237a0-108">Para crear una versión actualizada de una directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-108">To create an updated version of a policy</span></span>  
  
-   <span data-ttu-id="237a0-109">Para actualizar una directiva de modo que use un ensamblado actualizado</span><span class="sxs-lookup"><span data-stu-id="237a0-109">To update a policy to use an updated assembly</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a><span data-ttu-id="237a0-110">Para crear una nueva versión vacía de una directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-110">To create an empty new version of a policy</span></span>  
  
-   <span data-ttu-id="237a0-111">Haga clic en la carpeta de directiva y, a continuación, haga clic en **agregar nueva versión**.</span><span class="sxs-lookup"><span data-stu-id="237a0-111">Right-click the policy folder, and then click **Add New Version**.</span></span>  
  
### <a name="to-save-a-policy-version"></a><span data-ttu-id="237a0-112">Para guardar una versión de directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-112">To save a policy version</span></span>  
  
-   <span data-ttu-id="237a0-113">Haga clic en la versión de directiva y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="237a0-113">Right-click the policy version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-policy-version"></a><span data-ttu-id="237a0-114">Para publicar una versión de directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-114">To publish a policy version</span></span>  
  
-   <span data-ttu-id="237a0-115">Haga clic en la versión de directiva y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="237a0-115">Right-click the policy version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-policy"></a><span data-ttu-id="237a0-116">Para crear una versión actualizada de una directiva</span><span class="sxs-lookup"><span data-stu-id="237a0-116">To create an updated version of a policy</span></span>  
  
1.  <span data-ttu-id="237a0-117">Haga clic en una versión de directiva existente y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="237a0-117">Right-click an existing policy version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="237a0-118">Haga clic en la carpeta de directiva y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="237a0-118">Right-click the policy folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="237a0-119">Se crea una nueva versión, con los mismos elementos que la versión copiada.</span><span class="sxs-lookup"><span data-stu-id="237a0-119">A new version is created, with the same elements as the copied version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="237a0-120">Si la directiva utiliza un ensamblado .NET y éste se actualiza, debe enlazar la directiva con la nueva versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="237a0-120">If your policy uses a .NET assembly, and the assembly is updated, you should bind your policy to the newer version of the assembly.</span></span>  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a><span data-ttu-id="237a0-121">Para actualizar una directiva de modo que use un ensamblado actualizado</span><span class="sxs-lookup"><span data-stu-id="237a0-121">To update a policy to use an updated assembly</span></span>  
  
1.  <span data-ttu-id="237a0-122">Haga clic en **iniciar**, seleccione **herramientas administrativas**, seleccione **configuración de .NET Framework**y, a continuación, haga clic en **ensamblados configurados** .</span><span class="sxs-lookup"><span data-stu-id="237a0-122">Click **Start**, point to **Administrative Tools**, point to **.NET Framework Configuration**, and then click **Configured Assemblies**.</span></span>  
  
2.  <span data-ttu-id="237a0-123">Vaya a propiedades del ensamblado de destino y haga clic en el **directiva de enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="237a0-123">Go to properties for the target assembly and click the **Binding Policy** tab.</span></span>  
  
3.  <span data-ttu-id="237a0-124">En la caché de ensamblados global, cambie el número de versión a una versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="237a0-124">In the global assembly cache, change the version number to the newer version.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="237a0-125">Todos los ensamblados que utilizan las directivas deben agregarse a la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="237a0-125">All assemblies used by policies should be added to the global assembly cache.</span></span>