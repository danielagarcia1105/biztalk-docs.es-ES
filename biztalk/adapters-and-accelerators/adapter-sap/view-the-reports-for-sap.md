---
title: Ver los informes de SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0932ffc5-cde0-4d14-822f-713b760c3f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d446a24ca9432842d52062acb494f92060bbaaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218220"
---
# <a name="view-the-reports-for-sap"></a><span data-ttu-id="ade61-102">Ver los informes de SAP</span><span class="sxs-lookup"><span data-stu-id="ade61-102">View the Reports for SAP</span></span>
<span data-ttu-id="ade61-103">Una vez haya creado el informe, puede verlo si se usa Visual Studio o host del servidor de informes en Internet Information Services (IIS) y el acceso a través de la red.</span><span class="sxs-lookup"><span data-stu-id="ade61-103">After you have created the report, you can view it either using Visual Studio or host it on the Report Server on Internet Information Services (IIS) and access over the network.</span></span> <span data-ttu-id="ade61-104">Este tema proporciona instrucciones sobre cómo ver informes tanto en Visual Studio y el uso de IIS.</span><span class="sxs-lookup"><span data-stu-id="ade61-104">This topic provides instructions on how to view reports both in Visual Studio and using IIS.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ade61-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ade61-105">Prerequisites</span></span>  
 <span data-ttu-id="ade61-106">Antes de realizar los procedimientos proporcionados en este tema, debe ha generado un informe tal y como se describe en [usar el proveedor de datos de SAP para crear un proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md).</span><span class="sxs-lookup"><span data-stu-id="ade61-106">Before performing the procedures provided in this topic, you must have generated a report as described in [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md).</span></span>  
  
### <a name="to-view-the-reports-in-visual-studio"></a><span data-ttu-id="ade61-107">Para ver los informes en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ade61-107">To view the reports in Visual Studio</span></span>  
  
1.  <span data-ttu-id="ade61-108">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade61-108">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], right-click the project name in the Solution Explorer, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ade61-109">En el cuadro de diálogo páginas de propiedades de informe, haga clic en **Configuration Manager**y desactive la casilla situada bajo la **implementar** columna.</span><span class="sxs-lookup"><span data-stu-id="ade61-109">In the report property pages dialog box, click **Configuration Manager**, and clear the check box under the **Deploy** column.</span></span> <span data-ttu-id="ade61-110">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-110">Click **Close**.</span></span>  
  
3.  <span data-ttu-id="ade61-111">En el cuadro de diálogo páginas de propiedades de informe, para la **StartItem** propiedad, seleccione el nombre del informe y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-111">In the report property pages dialog box, for the **StartItem** property, select the name of the report, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ade61-112">![Especificar propiedades para el proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")</span><span class="sxs-lookup"><span data-stu-id="ade61-112">![Specify properties for the Report Server project](../../adapters-and-accelerators/adapter-sap/media/b3c500f7-840d-461f-945c-66db239d81b9.gif "b3c500f7-840d-461f-945c-66db239d81b9")</span></span>  
  
4.  <span data-ttu-id="ade61-113">Haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-113">Right-click the project name in the Solution Explorer, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="ade61-114">Presione `F5` para ejecutar el proyecto para generar el informe.</span><span class="sxs-lookup"><span data-stu-id="ade61-114">Press `F5` to run the project to generate the report.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ade61-115">En [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], puede ver el informe, haga clic en el **vista previa** ficha. En tal caso, los cuadros de diálogo siguientes se abrirán en la ficha Vista previa.</span><span class="sxs-lookup"><span data-stu-id="ade61-115">In [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)], you can see the report by clicking the **Preview** tab. In such a case, the subsequent dialog boxes will open within the preview tab.</span></span>  
  
6.  <span data-ttu-id="ade61-116">Abre un cuadro de diálogo con el mismo nombre que ha especificado para el informe.</span><span class="sxs-lookup"><span data-stu-id="ade61-116">A dialog box with the same name as you specified for the report opens up.</span></span> <span data-ttu-id="ade61-117">Al crear el origen de datos, si ha elegido el **pedir credenciales** opción, escriba el nombre de usuario y la contraseña para el sistema SAP y, a continuación, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="ade61-117">While creating the data source, if you chose the **Prompt for credentials** option, enter the user name and password for the SAP system, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="ade61-118">![Especifique las credenciales SAP para generar un informe](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")</span><span class="sxs-lookup"><span data-stu-id="ade61-118">![Specify SAP credentials to generate a report](../../adapters-and-accelerators/adapter-sap/media/fa831aae-b2d1-4ba2-a23f-f7beeb8f898e.gif "fa831aae-b2d1-4ba2-a23f-f7beeb8f898e")</span></span>  
  
7.  <span data-ttu-id="ade61-119">Si la consulta especifica al crear el proyecto de servidor de informes requiere un parámetro, debe escribir el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ade61-119">If the query you specified while creating the Report Server project requires a parameter, you must enter the value of the parameter.</span></span> <span data-ttu-id="ade61-120">Por ejemplo, para la consulta especifica en el [usar el proveedor de datos de SAP para crear un proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) tema, requiere que especifique un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="ade61-120">For example, for the query you specified in the [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) topic, requires you to specify a value for the parameter, PARAM.</span></span>  
  
     <span data-ttu-id="ade61-121">Especifique el valor del parámetro, si es necesario y haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="ade61-121">Specify the value of the parameter, if required, and click **View Report**.</span></span>  
  
     <span data-ttu-id="ade61-122">![Especificar parámetros para generar un informe](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")</span><span class="sxs-lookup"><span data-stu-id="ade61-122">![Specify parameters to generate a report](../../adapters-and-accelerators/adapter-sap/media/5deec152-771b-46b4-84da-dd176193d7f3.gif "5deec152-771b-46b4-84da-dd176193d7f3")</span></span>  
  
### <a name="to-host-the-reports-on-report-server"></a><span data-ttu-id="ade61-123">Para hospedar los informes en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="ade61-123">To host the reports on Report Server</span></span>  
  
1.  <span data-ttu-id="ade61-124">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ade61-124">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], right-click the project name in the Solution Explorer, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ade61-125">En el cuadro de diálogo páginas de propiedades de informe, haga clic en **Configuration Manager**y seleccione la casilla situada bajo la **implementar** columna.</span><span class="sxs-lookup"><span data-stu-id="ade61-125">In the report property pages dialog box, click **Configuration Manager**, and select the check box under the **Deploy** column.</span></span> <span data-ttu-id="ade61-126">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-126">Click **Close**.</span></span>  
  
3.  <span data-ttu-id="ade61-127">En el cuadro de diálogo páginas de propiedades de informe, para la **StartItem** propiedad, seleccione el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="ade61-127">In the report property pages dialog box, for the **StartItem** property, select the name of the report.</span></span>  
  
4.  <span data-ttu-id="ade61-128">En el cuadro de diálogo páginas de propiedades de informe, para la **TargetServerURL** propiedad, especifique una dirección URL del servidor de informes y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-128">In the report property pages dialog box, for the **TargetServerURL** property, specify a URL for the Report Server, and then click **OK**.</span></span> <span data-ttu-id="ade61-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ade61-129">For example:</span></span>  
  
    ```  
    http://localhost/reportserver  
    ```  
  
     <span data-ttu-id="ade61-130">![Especifique la dirección URL del servidor de informes](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")</span><span class="sxs-lookup"><span data-stu-id="ade61-130">![Specify URL for the Report Server](../../adapters-and-accelerators/adapter-sap/media/397ddfd6-f3d2-4327-9bc3-1efa22dc2249.gif "397ddfd6-f3d2-4327-9bc3-1efa22dc2249")</span></span>  
  
5.  <span data-ttu-id="ade61-131">Haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-131">Right-click the project name in the Solution Explorer, and then click **Build**.</span></span>  
  
6.  <span data-ttu-id="ade61-132">Haga clic en el nombre del proyecto en el Explorador de soluciones y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-132">Right-click the project name in the Solution Explorer, and then click **Deploy**.</span></span>  
  
7.  <span data-ttu-id="ade61-133">Inicie IIS.</span><span class="sxs-lookup"><span data-stu-id="ade61-133">Start IIS.</span></span> <span data-ttu-id="ade61-134">Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `inetmgr`y presione `Enter`.</span><span class="sxs-lookup"><span data-stu-id="ade61-134">Click **Start**, click **Run**, type `inetmgr`, and press `Enter`.</span></span>  
  
8.  <span data-ttu-id="ade61-135">En el **Internet Information Services (IIS) Manager** complemento, expanda el nombre del equipo, expanda **sitios Web**, expanda **sitio Web predeterminado**, haga clic en  **ReportServer**y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="ade61-135">In the **Internet Information Services (IIS) Manager** snap-in, expand the computer name, expand **Web Sites**, expand **Default Web Site**, right-click **ReportServer**, and then click **Browse**.</span></span>  
  
9. <span data-ttu-id="ade61-136">En el panel derecho, haga clic en el nombre del proyecto y, a continuación, haga clic en el nombre del informe.</span><span class="sxs-lookup"><span data-stu-id="ade61-136">In the right pane, click the name of the project, and then click on the name of the report.</span></span>  
  
10. <span data-ttu-id="ade61-137">Al crear el origen de datos, si ha elegido el **pedir credenciales** opción, escriba el nombre de usuario y la contraseña para el sistema SAP y haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="ade61-137">While creating the data source, if you chose the **Prompt for credentials** option, enter the user name and password for the SAP system and click **View Report**.</span></span>  
  
11. <span data-ttu-id="ade61-138">Si la consulta especifica al crear el proyecto de servidor de informes requiere un parámetro, debe escribir el valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="ade61-138">If the query you specified while creating the Report Server project requires a parameter, you must enter the value of the parameter.</span></span> <span data-ttu-id="ade61-139">Por ejemplo, para la consulta especifica en el [usar el proveedor de datos de SAP para crear un proyecto de servidor de informes](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) tema, requiere que especifique un valor para el parámetro.</span><span class="sxs-lookup"><span data-stu-id="ade61-139">For example, for the query you specified in the [Use the Data Provider for SAP to Create a Report Server Project](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-to-create-a-report-server-project.md) topic, requires you to specify a value for the parameter, PARAM.</span></span>  
  
     <span data-ttu-id="ade61-140">Especifique el valor del parámetro, si es necesario y haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="ade61-140">Specify the value of the parameter, if required, and click **View Report**.</span></span>  
  
     <span data-ttu-id="ade61-141">![Especificar parámetros para generar un informe](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")</span><span class="sxs-lookup"><span data-stu-id="ade61-141">![Specify parameters to generate a report](../../adapters-and-accelerators/adapter-sap/media/221c8c12-4e4f-47f5-9289-9e9212cf6e25.gif "221c8c12-4e4f-47f5-9289-9e9212cf6e25")</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="ade61-142">También puede ver directamente desde el explorador web proporcionando la dirección URL para el informe.</span><span class="sxs-lookup"><span data-stu-id="ade61-142">You can also view directly from the web browser by giving the URL for the report.</span></span> <span data-ttu-id="ade61-143">Una dirección URL típica para el informe `is http://localhohost/reportserver/<report_name>`.</span><span class="sxs-lookup"><span data-stu-id="ade61-143">A typical URL for the report `is http://localhohost/reportserver/<report_name>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade61-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ade61-144">See Also</span></span>  
 [<span data-ttu-id="ade61-145">Usar el proveedor de datos para SAP con SSRS</span><span class="sxs-lookup"><span data-stu-id="ade61-145">Use the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)