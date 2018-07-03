---
title: Personalizar un proceso privado para trabajar con un PIP específico | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77abdf870f0813bb5b9e1dd7a039b99ef0726c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001509"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="55159-102">Personalizar un proceso privado para trabajar con un PIP específico</span><span class="sxs-lookup"><span data-stu-id="55159-102">Customizing a Private Process to Work with a Specific PIP</span></span>
<span data-ttu-id="55159-103">Puede crear una expresión de filtro que hará que a un contestador de orquestación de procesos de privados para procesar o no las instancias de proceso de un proceso de interfaz de socio (PIP) específico.</span><span class="sxs-lookup"><span data-stu-id="55159-103">You can create a filter expression that will cause a responder private-process orchestration to process or not process instances of a specific Partner Interface Process (PIP).</span></span> <span data-ttu-id="55159-104">Esto ofrece la flexibilidad de crear un proceso privado personalizado para recibir y procesar algunas instancias PIP y el uso privado predeterminado procesos todas las demás instancias PIP.</span><span class="sxs-lookup"><span data-stu-id="55159-104">This gives you the flexibility of creating a custom private process to receive and process some PIP instances, and using the default private process to process all other PIP instances.</span></span>  
  
 <span data-ttu-id="55159-105">Para crear un proceso privado personalizado para trabajar con un determinado PIP o múltiples PIP específico, cree una expresión de filtro para la forma recepción de la orquestación de procesos privado.</span><span class="sxs-lookup"><span data-stu-id="55159-105">To create a custom private process to work with a specific PIP or multiple specific PIPs, you create a filter expression for the receive shape of the private-process orchestration.</span></span> <span data-ttu-id="55159-106">Un ejemplo es la orquestación PIP3A4PrivateResponder.odx en el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="55159-106">An example is the PIP3A4PrivateResponder.odx orchestration in the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="55159-107">Se encuentra en \< *unidad*\>: \Program Files\BizTalk \<versión\> Acelerador para RosettaNet\SDK\PIP3A4Process Rules\PIP3A4PrivateResponder de negocios utilizando.</span><span class="sxs-lookup"><span data-stu-id="55159-107">It is located at \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PIP3A4Process Using Business Rules\PIP3A4PrivateResponder.</span></span>  
  
 <span data-ttu-id="55159-108">Además de crear un proceso privado que procesan solo las instancias de un PIP específico, debe personalizar el proceso privado de BTARN predeterminado para que no procesará las instancias de ese PIP.</span><span class="sxs-lookup"><span data-stu-id="55159-108">Besides creating a private process that process only instances of a specific PIP, you must customize the default BTARN private process so that it will not process instances for that PIP.</span></span>  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a><span data-ttu-id="55159-109">Para personalizar un proceso privado del Respondedor para trabajar con un PIP específico</span><span class="sxs-lookup"><span data-stu-id="55159-109">To customize a responder private process to work with a specific PIP</span></span>  
  
1. <span data-ttu-id="55159-110">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], crear una orquestación de procesos de privados de servicio de respuesta personalizado para trabajar con un PIP específico.</span><span class="sxs-lookup"><span data-stu-id="55159-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], create a custom responder private-process orchestration for working with a specific PIP.</span></span> <span data-ttu-id="55159-111">Puede basar la orquestación en la orquestación de proceso privado predeterminado Respondedor BTARN.</span><span class="sxs-lookup"><span data-stu-id="55159-111">You can base the orchestration on the default BTARN responder private-process orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="55159-112">Puede encontrar el valor predeterminado orquestación del Respondedor del proceso de privado, denominado PrivateResponder.odx en el SDK de BTARN.</span><span class="sxs-lookup"><span data-stu-id="55159-112">You can find the default responder private-process orchestration, named PrivateResponder.odx, in the BTARN SDK.</span></span> <span data-ttu-id="55159-113">Se encuentra en  *\<unidad\>*: \Program Files\BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateResponder.</span><span class="sxs-lookup"><span data-stu-id="55159-113">It is located at *\<drive\>*:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
2. <span data-ttu-id="55159-114">Agregue la orquestación personalizada al proyecto de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="55159-114">Add the custom orchestration to your BizTalk project.</span></span> <span data-ttu-id="55159-115">Asegúrese de que el proyecto tiene una referencia al archivo Microsoft.Solutions.BTARN.GlobalSchemas.dll.</span><span class="sxs-lookup"><span data-stu-id="55159-115">Make sure that your project has a reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
3. <span data-ttu-id="55159-116">Abra la orquestación personalizada en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="55159-116">Open the custom orchestration in Orchestration Designer.</span></span>  
  
4. <span data-ttu-id="55159-117">Haga clic en la primera **recepción** forma que activa la orquestación y, a continuación, haga clic en **Editar expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="55159-117">Right-click the first **Receive** shape that activates the orchestration, and then click **Edit Filter Expression**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="55159-118">La forma de recepción para la orquestación de proceso privado predeterminado Respondedor BTARN tiene dos condiciones de filtro: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" o Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction".</span><span class="sxs-lookup"><span data-stu-id="55159-118">The receive shape for the default BTARN responder private-process orchestration has two filter conditions: Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" or Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction".</span></span> <span data-ttu-id="55159-119">Esta expresión se asegura de que la orquestación procesa los mensajes de RosettaNet.</span><span class="sxs-lookup"><span data-stu-id="55159-119">This expression makes sure that the orchestration processes RosettaNet messages.</span></span> <span data-ttu-id="55159-120">Conservar esta expresión de filtro en la orquestación personalizada.</span><span class="sxs-lookup"><span data-stu-id="55159-120">Retain this filter expression in your custom orchestration.</span></span>  
  
5. <span data-ttu-id="55159-121">En el **expresión de filtro** cuadro de diálogo, en la columna de la propiedad en la primera fila abierta, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable, en la columna de operador Seleccione **==** en la lista desplegable, en la columna valor, escriba el código PIP de tres dígitos, por ejemplo, escriba **3A4**.</span><span class="sxs-lookup"><span data-stu-id="55159-121">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list, in the Operator column, select **==** from the drop-down list, in the Value column, type the three-digit PIP code, for example, type **3A4**.</span></span>  
  
6. <span data-ttu-id="55159-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55159-122">Click **OK**.</span></span>  
  
7. <span data-ttu-id="55159-123">Abra el proyecto de orquestación de procesos de privados del servicio de respuesta predeterminado (PrivateResponder.btproj) en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="55159-123">Open the default responder private-process orchestration project (PrivateResponder.btproj) in Orchestration Designer.</span></span> <span data-ttu-id="55159-124">Asegúrese de que el proyecto tiene una referencia de trabajo en el archivo Microsoft.Solutions.BTARN.GlobalSchemas.dll.</span><span class="sxs-lookup"><span data-stu-id="55159-124">Make sure that the project has a working reference to the Microsoft.Solutions.BTARN.GlobalSchemas.dll file.</span></span>  
  
8. <span data-ttu-id="55159-125">Haga doble clic en **PrivateResponder.odx**.</span><span class="sxs-lookup"><span data-stu-id="55159-125">Double-click **PrivateResponder.odx**.</span></span>  
  
9. <span data-ttu-id="55159-126">Haga clic en el **ReceiveFromPublicProcessResponder** forma recepción y, a continuación, haga clic en **Editar expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="55159-126">Right-click the **ReceiveFromPublicProcessResponder** receive shape, and then click **Edit Filter Expression**.</span></span>  
  
10. <span data-ttu-id="55159-127">En el **expresión de filtro** cuadro de diálogo, en la columna de la propiedad en la primera fila abierta, seleccione **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="55159-127">In the **Filter Expression** dialog box, in the Property column in the first open row, select **Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode** from the drop-down list.</span></span> <span data-ttu-id="55159-128">En la columna de operador, seleccione **! =** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="55159-128">In the Operator column, select **!=** from the drop-down list.</span></span> <span data-ttu-id="55159-129">En la columna valor, escriba el código PIP de tres dígitos, por ejemplo, escriba "**3A4"**.</span><span class="sxs-lookup"><span data-stu-id="55159-129">In the Value column, type the three-digit PIP code, for example, type "**3A4"**.</span></span>  
  
11. <span data-ttu-id="55159-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55159-130">Click **OK**.</span></span>  
  
12. <span data-ttu-id="55159-131">En el Explorador de soluciones, haga clic en el proyecto que contiene la orquestación y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="55159-131">In Solution Explorer, right-click the project that contains the orchestration and then click **Build**.</span></span>  
  
13. <span data-ttu-id="55159-132">Una vez que se ha compilado correctamente el proyecto, haga clic en el proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="55159-132">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
14. <span data-ttu-id="55159-133">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="55159-133">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="55159-134">Mover a \< *unidad*\>: \Program Files\BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateResponder, seleccione **PrivateResponder.odx**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="55159-134">Move to \<*drive*\>:\Program Files\BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateResponder, select **PrivateResponder.odx**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="55159-135">En el Explorador de soluciones, haga clic con el botón derecho en el proyecto y, después, haga clic en **Generar**.</span><span class="sxs-lookup"><span data-stu-id="55159-135">In Solution Explorer, right-click the project, and then click **Build**.</span></span>  
  
17. <span data-ttu-id="55159-136">Una vez que se ha compilado correctamente el proyecto, haga clic en el proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="55159-136">After the project has been successfully built, right-click the project, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55159-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="55159-137">See Also</span></span>  
 [<span data-ttu-id="55159-138">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="55159-138">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)