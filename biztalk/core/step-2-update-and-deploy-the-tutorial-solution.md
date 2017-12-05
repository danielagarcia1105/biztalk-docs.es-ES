---
title: "Paso 2: Actualizar e implementar la solución del Tutorial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d03adfdd-1160-4e8c-a564-3acb2ecd0476
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67fd3d34f25dd409121a3a21c9eb419b4aadce6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-update-and-deploy-the-tutorial-solution"></a><span data-ttu-id="5b28e-102">Paso 2: Actualizar e implementar la solución del Tutorial</span><span class="sxs-lookup"><span data-stu-id="5b28e-102">Step 2: Update and Deploy the Tutorial Solution</span></span>
<span data-ttu-id="5b28e-103">![Paso 2 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span><span class="sxs-lookup"><span data-stu-id="5b28e-103">![Step 2 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-2of9.gif "Step_2of9")</span></span>  
  
 <span data-ttu-id="5b28e-104">En este paso actualizará la solución propuesta para este tutorial para, a continuación, generar e implementar el ensamblado del tutorial.</span><span class="sxs-lookup"><span data-stu-id="5b28e-104">In this step you update the solution provided for this tutorial, and then build and deploy the tutorial assembly.</span></span> <span data-ttu-id="5b28e-105">Para cumplir los fines de este tutorial, se han creado ya el esquema, la canalización de envío personalizada y la asignación necesarios.</span><span class="sxs-lookup"><span data-stu-id="5b28e-105">For the purposes of this tutorial, the necessary schema, custom send pipeline, and map have already been created.</span></span> <span data-ttu-id="5b28e-106">La asignación se utiliza para convertir los datos de EDI 850 en el formato necesario según el sistema de pedidos.</span><span class="sxs-lookup"><span data-stu-id="5b28e-106">The map is used to convert the 850 EDI data into the format required by your Order System.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5b28e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5b28e-107">Prerequisites</span></span>  
 <span data-ttu-id="5b28e-108">Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b28e-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-enable-the-edi-inbound-processing-solution-to-be-built-in-visual-studio"></a><span data-ttu-id="5b28e-109">Para habilitar la integración de la solución de procesamiento entrante de EDI en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b28e-109">To enable the EDI Inbound Processing solution to be built in Visual Studio</span></span>  
  
1.  <span data-ttu-id="5b28e-110">Iniciar **Microsoft Visual Studio** como administrador.</span><span class="sxs-lookup"><span data-stu-id="5b28e-110">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="5b28e-111">Si no inicia Visual Studio con privilegios de administrador, obtendrá un error cuando implemente la solución para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b28e-111">If you do not start Visual Studio with administrator privileges, you will get an error while deploying the solution to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="5b28e-112">En Visual Studio, haga clic en **archivo**, seleccione **abiertos**y, a continuación, haga clic en **proyecto/solución**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-112">In Visual Studio, click **File**, point to **Open**, and then click **Project/Solution**.</span></span> <span data-ttu-id="5b28e-113">Mover a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial, seleccione **EDI Inbound Processing.sln**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-113">Move to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial, select **EDI Inbound Processing.sln**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b28e-114">Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI.</span><span class="sxs-lookup"><span data-stu-id="5b28e-114">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="5b28e-115">Si no es así, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span><span class="sxs-lookup"><span data-stu-id="5b28e-115">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3.  <span data-ttu-id="5b28e-116">Haga clic en el **Inbound_EDI** del proyecto en el Explorador de soluciones y, a continuación, seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-116">Right-click the **Inbound_EDI** project in the Solution Explorer, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="5b28e-117">En el árbol de consola de la **páginas de propiedades de Inbound_EDI** cuadro de diálogo, seleccione **implementación** y en el **Server** campo asegurarte de que se especifique el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="5b28e-117">In the console tree of the **Inbound_EDI Property Pages** dialog box, select  **Deployment** and in the **Server** field ensure that your computer name is entered.</span></span>  
  
5.  <span data-ttu-id="5b28e-118">En el árbol de consola, haga clic en **firma** y, a continuación, seleccione **firmar el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-118">In the console tree, click **Signing** and then select **Sign the assembly**.</span></span> <span data-ttu-id="5b28e-119">Para **elegir un archivo de nombre de clave seguro**, seleccione \< **nuevo...**  \> y escriba **keyfile.snk** como el **nombre de archivo de clave**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-119">For **Choose a strong key name file**, select \<**New…**\> and enter  **keyfile.snk** as the **Key file name**.</span></span> <span data-ttu-id="5b28e-120">Desactive **proteger mi archivo de clave con una contraseña** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-120">Clear **Protect my key file with a password** and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5b28e-121">Cerrar la **páginas de propiedades de Inbound_EDI** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5b28e-121">Close the **Inbound_EDI Property Pages** dialog box.</span></span>  
  
### <a name="to-deploy-the-project"></a><span data-ttu-id="5b28e-122">Para implementar el proyecto</span><span class="sxs-lookup"><span data-stu-id="5b28e-122">To deploy the project</span></span>  
  
1.  <span data-ttu-id="5b28e-123">En el Explorador de soluciones, haga doble clic en el **X12_00401_850.xsd** esquema.</span><span class="sxs-lookup"><span data-stu-id="5b28e-123">In Solution Explorer, double-click the **X12_00401_850.xsd** schema.</span></span> <span data-ttu-id="5b28e-124">Asegúrese de que se abre.</span><span class="sxs-lookup"><span data-stu-id="5b28e-124">Confirm that it opens.</span></span>  
  
2.  <span data-ttu-id="5b28e-125">En el Explorador de soluciones, haga doble clic en el **Inbound4010850_to_OrderFile.btm** mapa.</span><span class="sxs-lookup"><span data-stu-id="5b28e-125">In Solution Explorer, double-click the **Inbound4010850_to_OrderFile.btm** map.</span></span> <span data-ttu-id="5b28e-126">Asegúrese de que se abre.</span><span class="sxs-lookup"><span data-stu-id="5b28e-126">Confirm that it opens.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b28e-127">La asignación Inbound4010850_to_OrderFile.btm del proyecto asigna los datos del mensaje de prueba de 850 entrante al archivo XML saliente que se ha enviado a la carpeta del sistema de pedidos (\toOrderSystem).</span><span class="sxs-lookup"><span data-stu-id="5b28e-127">The Inbound4010850_to_OrderFile.btm map in the project maps the data in the inbound 850 test message to the outbound XML file delivered to the OrderSystem folder (\toOrderSystem).</span></span>  
  
3.  <span data-ttu-id="5b28e-128">En el Explorador de soluciones, haga clic en el **Inbound_EDI** de proyecto y seleccione **generar** para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5b28e-128">In Solution Explorer, right-click the **Inbound_EDI** project and select **Build** to build the project.</span></span>  
  
4.  <span data-ttu-id="5b28e-129">En el Explorador de soluciones, haga clic en el **Inbound_EDI** de proyecto y seleccione **implementar** para implementar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5b28e-129">In Solution Explorer, right-click the **Inbound_EDI** project and select **Deploy** to deploy the project.</span></span>  
  
5.  <span data-ttu-id="5b28e-130">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, expanda **administración de BizTalk Server**, **grupo de BizTalk**, **aplicaciones**, \<  **Todos los artefactos** \> y, a continuación, seleccione **recursos**.</span><span class="sxs-lookup"><span data-stu-id="5b28e-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, \<**All Artifacts**\> and then select **Resources**.</span></span> <span data-ttu-id="5b28e-131">Compruebe que la **Inbound_EDI** ensamblado.</span><span class="sxs-lookup"><span data-stu-id="5b28e-131">Verify that the **Inbound_EDI** assembly is listed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5b28e-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5b28e-132">Next Steps</span></span>  
 <span data-ttu-id="5b28e-133">Configurar un perfil de entidad y de negocio para su organización (**OrderSystem**), tal y como se describe en [paso 3: configurar una entidad y perfil de negocio para su organización](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span><span class="sxs-lookup"><span data-stu-id="5b28e-133">You configure a party and business profile for your organization (**OrderSystem**), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b28e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b28e-134">See Also</span></span>  
 [<span data-ttu-id="5b28e-135">Paso 1: Prepara el tutorial de programadores de interfaces de EDI</span><span class="sxs-lookup"><span data-stu-id="5b28e-135">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)