---
title: Cómo actualizar un ensamblado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f456c8f-247a-4d5c-b5af-41e88968779c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 163b06706652b1f65b9a76e3feea8911a2ca4c88
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "22298332"
---
# <a name="how-to-update-an-assembly"></a><span data-ttu-id="ab25f-102">Cómo actualizar un ensamblado</span><span class="sxs-lookup"><span data-stu-id="ab25f-102">How to Update an Assembly</span></span>
<span data-ttu-id="ab25f-103">En este tema se describe cómo actualizar la versión de un ensamblado y la aplicación que se implementa un ensamblado al uso de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="ab25f-103">This topic describes how to update the version of an assembly and the application that an assembly is deployed to using Visual Studio 2010.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab25f-104">Si va a actualizar un ensamblado con una nueva versión, no es preciso reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ab25f-104">If you are updating an assembly with a new version, you do not need to restart the application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ab25f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ab25f-105">Prerequisites</span></span>  
 <span data-ttu-id="ab25f-106">Para realizar los procedimientos descritos en este tema, deberá iniciar la sesión con una cuenta que sea miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ab25f-106">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="updating-an-assembly"></a><span data-ttu-id="ab25f-107">Actualizar un ensamblado</span><span class="sxs-lookup"><span data-stu-id="ab25f-107">Updating an Assembly</span></span>  
  
#### <a name="to-increment-the-version-number-of-an-assembly"></a><span data-ttu-id="ab25f-108">Para incrementar el número de versión de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="ab25f-108">To increment the version number of an assembly</span></span>  
  
1.  <span data-ttu-id="ab25f-109">En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ab25f-109">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ab25f-110">En el **Diseñador de proyectos**, haga clic en el **aplicación** ficha.</span><span class="sxs-lookup"><span data-stu-id="ab25f-110">In the **Project Designer**, click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="ab25f-111">En el panel derecho, haga clic en **información de ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="ab25f-111">In the right pane, click **Assembly Information**.</span></span>  
  
4.  <span data-ttu-id="ab25f-112">En el **información de ensamblado** diálogo cuadro, especifique valores para la **versión del ensamblado** campo para aumentar el número de versión de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ab25f-112">In the **Assembly Information** dialog box, specify values for the **Assembly Version** field to increase the assembly version number.</span></span> <span data-ttu-id="ab25f-113">Incremente únicamente el número principal o secundario de la versión.</span><span class="sxs-lookup"><span data-stu-id="ab25f-113">You should increase only the major or minor version number.</span></span> <span data-ttu-id="ab25f-114">El número de versión principal es el primer dígito en la secuencia (***n***. 0.0.0); el número de versión secundaria es el segundo dígito en la secuencia (0. ***n*** . 0.0).</span><span class="sxs-lookup"><span data-stu-id="ab25f-114">The major version number is the first digit in the sequence (***n***.0.0.0); the minor version number is the second digit in the sequence (0.***n***.0.0).</span></span> <span data-ttu-id="ab25f-115">BizTalk Server no reconocerá un cambio de número de versión que está más adelante en la secuencia, como 0,0.  ***n*** .0 ó 0.0.0. ***n***.</span><span class="sxs-lookup"><span data-stu-id="ab25f-115">BizTalk Server will not recognize a version number change that is later in the sequence, such as 0.0.***n***.0 or 0.0.0.***n***.</span></span>  
  
5.  <span data-ttu-id="ab25f-116">Haga clic en **Aceptar** para cerrar el **información de ensamblado** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ab25f-116">Click **OK** to close the **Assembly Information** dialog box.</span></span>  
  
6.  <span data-ttu-id="ab25f-117">Guarde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ab25f-117">Save the project.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab25f-118">Utilice el Diseñador de canalizaciones y el Modelo de objetos para el explorador de BizTalk para evitar conflictos entre los esquemas al incrementar las versiones de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="ab25f-118">Use the Pipeline Designer and BizTalk Explorer Object Model to avoid schema collisions when incrementing assembly versions.</span></span>  
  
#### <a name="to-change-the-application-that-an-assembly-is-deployed-to"></a><span data-ttu-id="ab25f-119">Para cambiar la aplicación que se implementa un ensamblado</span><span class="sxs-lookup"><span data-stu-id="ab25f-119">To change the application that an assembly is deployed to</span></span>  
  
1.  <span data-ttu-id="ab25f-120">En el Explorador de soluciones, haga clic en el proyecto de BizTalk y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ab25f-120">In Solution Explorer, right-click the BizTalk project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ab25f-121">En el **Diseñador de proyectos**, haga clic en el **implementación** ficha.</span><span class="sxs-lookup"><span data-stu-id="ab25f-121">In the **Project Designer**, click the **Deployment** tab.</span></span>  
  
3.  <span data-ttu-id="ab25f-122">En el panel derecho, especifique el nombre de aplicación en el **nombre de la aplicación** campo.</span><span class="sxs-lookup"><span data-stu-id="ab25f-122">In the right pane, specify the application name in the **Application Name** field.</span></span>  
  
4.  <span data-ttu-id="ab25f-123">Asegúrese de que el **instalar en la caché Global de ensamblados** propiedad está establecida en **True**.</span><span class="sxs-lookup"><span data-stu-id="ab25f-123">Ensure that the **Install to Global Assembly Cache** property is set to **True**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab25f-124">Al implementar la solución, los ensamblados se implementarán en la nueva aplicación y se instalarán en la GAC.</span><span class="sxs-lookup"><span data-stu-id="ab25f-124">When you deploy the solution, the assemblies will be deployed into the new application and installed in the GAC.</span></span>