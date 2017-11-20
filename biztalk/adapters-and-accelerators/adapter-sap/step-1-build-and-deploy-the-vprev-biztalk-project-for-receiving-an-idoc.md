---
title: 'Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, building and deploying previous version of BizTalk project for receiving an IDOC
- migrating, building and deploying previous version of BizTalk project for receiving an IDOC
- migration
ms.assetid: ab6bdf9a-dca5-4acd-97b2-a9afe9792978
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad9654f295f0f43b720b7ac77aec4ac6315f78ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc"></a><span data-ttu-id="bb871-102">Paso 1: Compilar e implementar el proyecto de BizTalk vPrev para recibir un IDOC</span><span class="sxs-lookup"><span data-stu-id="bb871-102">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>
<span data-ttu-id="bb871-103">![Paso 1 de 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="bb871-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="bb871-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="bb871-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="bb871-105">**Objetivo:** en este paso, generará e implementará el proyecto de BizTalk vPrev existente para recibir un IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="bb871-105">**Objective:** In this step, you build and deploy your existing vPrev BizTalk project to receive an IDOC from an SAP system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb871-106">No es necesario realizar ningún cambio en el proyecto de BizTalk vPrev.</span><span class="sxs-lookup"><span data-stu-id="bb871-106">You do not need to make any change to the vPrev BizTalk project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bb871-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bb871-107">Prerequisites</span></span>  
 <span data-ttu-id="bb871-108">Debe tener un proyecto de BizTalk vPrev para recibir un IDOC ORDERS03 desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="bb871-108">You must have a vPrev BizTalk project to receive an ORDERS03 IDOC from an SAP system.</span></span>  
  
### <a name="to-build-and-deploy-the-vprev-biztalk-project"></a><span data-ttu-id="bb871-109">Para compilar e implementar el proyecto de BizTalk vPrev</span><span class="sxs-lookup"><span data-stu-id="bb871-109">To build and deploy the vPrev BizTalk project</span></span>  
  
1.  <span data-ttu-id="bb871-110">Crear un archivo de clave de nombre seguro necesario para compilar e implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="bb871-110">Create a strong-name key file required to build and deploy the solution.</span></span> <span data-ttu-id="bb871-111">Para crear un archivo de clave de nombre seguro, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb871-111">To create a strong-name key file, do the following:</span></span>  
  
    1.  <span data-ttu-id="bb871-112">Inicie el símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bb871-112">Start Visual Studio Command Prompt.</span></span>  
  
    2.  <span data-ttu-id="bb871-113">En el símbolo del sistema navegue hasta la carpeta donde desea crear el archivo de clave.</span><span class="sxs-lookup"><span data-stu-id="bb871-113">At the command prompt navigate to the folder where you want to create the key file.</span></span> <span data-ttu-id="bb871-114">Por ejemplo, escriba **cd C:\Sample**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="bb871-114">For example, type **cd C:\Sample**, and then press ENTER.</span></span>  
  
    3.  <span data-ttu-id="bb871-115">En el símbolo del sistema, escriba **sn -k \<nombre de archivo de clave > .snk**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="bb871-115">At the command prompt, type **sn -k \<key file name>.snk**, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="bb871-116">Haga clic en el nombre de la solución de BizTalk en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb871-116">Right-click the BizTalk solution name in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="bb871-117">En el **páginas de propiedades** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb871-117">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="bb871-118">Haga clic en **propiedades de configuración** en el panel izquierdo y asegúrese de que las casillas de verificación la **generar** y **implementar** se seleccionan las columnas.</span><span class="sxs-lookup"><span data-stu-id="bb871-118">Click **Configuration Properties** from the left pane, and make sure the check boxes in the **Build** and **Deploy** columns are selected.</span></span>  
  
    2.  <span data-ttu-id="bb871-119">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb871-119">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="bb871-120">Haga clic en el proyecto de BizTalk en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bb871-120">Right-click the BizTalk project in Solution Explorer, and then click **Properties**.</span></span> <span data-ttu-id="bb871-121">En el **páginas de propiedades** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb871-121">In the **Property Pages** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="bb871-122">En el panel izquierdo, expanda **propiedades comunes**y, a continuación, haga clic en ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb871-122">In the left pane, expand **Common Properties**, and then click Assembly.</span></span>  
  
    2.  <span data-ttu-id="bb871-123">En el panel derecho, en la **nombre seguro** categoría, para el **archivo de clave de ensamblado** propiedad, proporcione la ruta de acceso al archivo de clave de ensamblado que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bb871-123">In the right pane, under the **Strong name** category, for the **Assembly Key File** property, provide the path to the assembly key file you created earlier.</span></span>  
  
    3.  <span data-ttu-id="bb871-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb871-124">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="bb871-125">En el Explorador de soluciones, haga clic en el nombre de la solución y, a continuación, haga clic en **generar solución**.</span><span class="sxs-lookup"><span data-stu-id="bb871-125">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="bb871-126">Después de que la solución se compila correctamente, haga clic en el nombre de la solución y, a continuación, haga clic en **implementar solución**.</span><span class="sxs-lookup"><span data-stu-id="bb871-126">After the solution successfully builds, right-click the solution name, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bb871-127">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bb871-127">Next Steps</span></span>  
 <span data-ttu-id="bb871-128">Crear y configurar un WCF-Custom puerto de recepción y configúrelo para recibir IDOC desde un sistema SAP mediante basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], tal y como se describe en [paso 2: configurar un puerto de recepción unidireccional de WCF-Custom](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md).</span><span class="sxs-lookup"><span data-stu-id="bb871-128">Create and configure a WCF-Custom receive port and configure it to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], as described in [Step 2: Configure a WCF-Custom One-way Receive Port](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb871-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb871-129">See Also</span></span>  
 [<span data-ttu-id="bb871-130">Tutorial 4: Migrar una SAP recibir IDOC proyecto de BizTalk</span><span class="sxs-lookup"><span data-stu-id="bb871-130">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)