---
title: Enviar datos de seguimiento a Azure Application Insights | Documentos de Microsoft
description: "Instalar feature pack para habilitar el análisis de datos de seguimiento con Azure Application Insights en BizTalk Server"
ms.custom: fp1
ms.date: 11/06/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a65ffd2c5ee76d857effde6ab82dddf17b3de4b
ms.sourcegitcommit: 30189176c44873e3de42cc5f2b8951da51ffd251
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a><span data-ttu-id="19c64-103">Enviar datos de seguimiento a Azure Application Insights con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="19c64-103">Send tracking data to Azure Application Insights using BizTalk Server</span></span>

<span data-ttu-id="19c64-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , le permitirán procesar y enviar los datos de seguimiento a Azure Application Insights.</span><span class="sxs-lookup"><span data-stu-id="19c64-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> <span data-ttu-id="19c64-105">Usar las características de Application Insights para realizar el seguimiento de las instancias de puertos de recepción, puertos de envío y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="19c64-105">Use the Application Insights features to track your instances from receive ports, send ports, and orchestrations.</span></span>
          
> [!IMPORTANT]
> <span data-ttu-id="19c64-106">Actualmente esta característica no funciona con las instancias con nombre de SQL.</span><span class="sxs-lookup"><span data-stu-id="19c64-106">This feature currently does not work with SQL Named Instances.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19c64-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="19c64-107">Prerequisites</span></span>
* <span data-ttu-id="19c64-108">Crear una nueva instancia de [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span><span class="sxs-lookup"><span data-stu-id="19c64-108">Create a new instance of [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-create-new-resource).</span></span> <span data-ttu-id="19c64-109">En sus propiedades, copie el **clave de instrumentación**.</span><span class="sxs-lookup"><span data-stu-id="19c64-109">In its properties, copy the **Instrumentation Key**.</span></span> <span data-ttu-id="19c64-110">Péguelo en otro archivo, por lo que tiene listo.</span><span class="sxs-lookup"><span data-stu-id="19c64-110">Paste it in another file so you have it ready.</span></span> <span data-ttu-id="19c64-111">Usamos esta clave en BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="19c64-111">We use this key within BizTalk Server.</span></span> 
* <span data-ttu-id="19c64-112">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c64-112">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="19c64-113">Habilitar el análisis de su entorno</span><span class="sxs-lookup"><span data-stu-id="19c64-113">Enable analytics for your environment</span></span>

1. <span data-ttu-id="19c64-114">Abra la **administración de BizTalk Server** de la consola, haga clic en el **grupo de BizTalk**y seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="19c64-114">Open the **BizTalk Server Administration** console, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="19c64-115">Comprobar **habilitar el análisis de nivel de grupo**.</span><span class="sxs-lookup"><span data-stu-id="19c64-115">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="19c64-116">Para el **tipo de destino**, seleccione **Application Insight** en la lista.</span><span class="sxs-lookup"><span data-stu-id="19c64-116">For the **Target type**, select **Application Insight** from the list.</span></span>
4. <span data-ttu-id="19c64-117">Para el **parámetros de conexión**, escriba la información de la aplicación  **[clave de instrumentación](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (disponible en el portal de Azure).</span><span class="sxs-lookup"><span data-stu-id="19c64-117">For the **Connection parameters**, enter your Application Insights **[instrumentation key](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** (available in the Azure portal).</span></span> <span data-ttu-id="19c64-118">La configuración del grupo un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="19c64-118">Your Group settings look similar to the following:</span></span> 

    ![Habilitar el análisis de su entorno](../core/media/environmentsettingapplicationinishgt.PNG)

5. <span data-ttu-id="19c64-120">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="19c64-120">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="19c64-121">Una vez habilitada, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] está listo para transmitir datos a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="19c64-121">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to Application Insights.</span></span> <span data-ttu-id="19c64-122">A continuación, habilitar el análisis en los puertos y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="19c64-122">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="19c64-123">Habilitar el análisis en los artefactos</span><span class="sxs-lookup"><span data-stu-id="19c64-123">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="19c64-124">En administración de BizTalk Server, haga clic en un **puerto de recepción**, **puerto de envío** o **orquestación**y seleccione **seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="19c64-124">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="19c64-125">En **análisis**, comprobar **Habilitar análisis**, de forma similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="19c64-125">Under **Analytics**, check **Enable Analytics**, similar to the following.</span></span> <span data-ttu-id="19c64-126">Esta opción inicia el seguimiento y transmitir datos desde el artefacto a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="19c64-126">This setting starts tracking and transmitting data from the artifact to Application Insights.</span></span>
    
    ![Datos de seguimiento para la orquestación](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="19c64-128">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="19c64-128">Select **OK** to save your changes.</span></span>
4. <span data-ttu-id="19c64-129">Reinicie la instancia de host de seguimiento y confirme que se inicia la aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="19c64-129">Restart the tracking host Instance, and confirm the BizTalk Application is started.</span></span>

<span data-ttu-id="19c64-130">A continuación, ejecute las consultas en Application Insights para ver los datos.</span><span class="sxs-lookup"><span data-stu-id="19c64-130">Next, run queries within Application Insights to see your data.</span></span>  

> [!TIP]
> <span data-ttu-id="19c64-131">Conectar los análisis de BizTalk Server con otros sistemas para obtener más información sobre los datos de las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="19c64-131">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="view-your-data"></a><span data-ttu-id="19c64-132">Ver los datos</span><span class="sxs-lookup"><span data-stu-id="19c64-132">View your data</span></span>
<span data-ttu-id="19c64-133">Una vez que los datos se envían a Application Insights, puede usar las herramientas de análisis dentro de Azure para crear consultas avanzadas y analizar los datos.</span><span class="sxs-lookup"><span data-stu-id="19c64-133">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="19c64-134">Inicie sesión en el [Portal de Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="19c64-134">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="19c64-135">Abra el recurso de Application Insights y seleccione **métricas explorador**.</span><span class="sxs-lookup"><span data-stu-id="19c64-135">Open your Application Insights resource, and select **Metrics Explorer**.</span></span>
3. <span data-ttu-id="19c64-136">Pueden mostrar gráficos vacíos.</span><span class="sxs-lookup"><span data-stu-id="19c64-136">Empty charts may display.</span></span> <span data-ttu-id="19c64-137">En un gráfico, seleccione **editar**.</span><span class="sxs-lookup"><span data-stu-id="19c64-137">In a chart, select **Edit**.</span></span> <span data-ttu-id="19c64-138">En **métricas**, seleccione **personalizado** para ver las propiedades de seguimiento disponibles.</span><span class="sxs-lookup"><span data-stu-id="19c64-138">Under **Metrics**, select **Custom** to see the available tracked properties.</span></span> <span data-ttu-id="19c64-139">Seleccione algunas de las distintas opciones para ver los cambios en el gráfico:</span><span class="sxs-lookup"><span data-stu-id="19c64-139">Select some of the different options to see the changes on your chart:</span></span> 

    ![Análisis de Azure](../core/media/azure-stream-metrics-custom.png)

4. <span data-ttu-id="19c64-141">Volver al recurso de Application Insights y seleccione **análisis**.</span><span class="sxs-lookup"><span data-stu-id="19c64-141">Go back to your Application Insights resource, and select **Analytics**.</span></span> <span data-ttu-id="19c64-142">En **uso**, seleccione **ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="19c64-142">In **Usage**, select **Run**.</span></span> <span data-ttu-id="19c64-143">Se ejecuta una consulta de ejemplo y los resultados se muestran en un gráfico.</span><span class="sxs-lookup"><span data-stu-id="19c64-143">A sample query is executed, and the results are displayed in a chart.</span></span>  

> [!TIP]
> <span data-ttu-id="19c64-144">Azure Application Insights es una herramienta eficaz.</span><span class="sxs-lookup"><span data-stu-id="19c64-144">Azure Application Insights is a powerful tool.</span></span> <span data-ttu-id="19c64-145">No hay recursos para ayudarle a escribir consultas en Application Insights en [funciones analíticas en Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics)e incluso para empezar a trabajar en [¿qué es Application Insights?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview).</span><span class="sxs-lookup"><span data-stu-id="19c64-145">There are resources to help you write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics), and even to get started at [What is Application Insights?](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-overview).</span></span>

## <a name="where-the-data-is-stored"></a><span data-ttu-id="19c64-146">Donde se almacenan los datos</span><span class="sxs-lookup"><span data-stu-id="19c64-146">Where the data is stored</span></span>

<span data-ttu-id="19c64-147">Los datos de seguimiento deben mostrarse con bastante rapidez (dentro de unos minutos) en Application Insights.</span><span class="sxs-lookup"><span data-stu-id="19c64-147">Your tracking data should display fairly quickly (within a few minutes) within Application Insights.</span></span> <span data-ttu-id="19c64-148">Si no es así, puede haber un problema con el host de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="19c64-148">If it doesn't, then there may be an issue with the tracking host.</span></span> <span data-ttu-id="19c64-149">En SQL Server, los datos de análisis se almacenan en la base de datos BizTalkMsgBoxDb en la TrackingData_2_*x* tablas.</span><span class="sxs-lookup"><span data-stu-id="19c64-149">In SQL Server, the Analytics data is stored in the BizTalkMsgBoxDb database, in the TrackingData_2_*x* tables.</span></span> <span data-ttu-id="19c64-150">En SQL Server Management Studio, devuelve las 1000 filas superiores en estos cuatro tablas.</span><span class="sxs-lookup"><span data-stu-id="19c64-150">In SQL Server Management Studio, return the top 1000 rows on these four tables.</span></span> <span data-ttu-id="19c64-151">Si los datos existe, el host de seguimiento no es mover los datos de la base de datos de BizTalkDTADb.</span><span class="sxs-lookup"><span data-stu-id="19c64-151">If the data is there, then the tracking host is not moving the data to the BizTalkDTADb database.</span></span> 

<span data-ttu-id="19c64-152">Algunas soluciones posibles:</span><span class="sxs-lookup"><span data-stu-id="19c64-152">Some possible resolutions:</span></span>

1. <span data-ttu-id="19c64-153">Reinicie el host de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="19c64-153">Restart the tracking host.</span></span>
2. <span data-ttu-id="19c64-154">Crear un host de seguimiento dedicado.</span><span class="sxs-lookup"><span data-stu-id="19c64-154">Create a dedicated tracking host.</span></span> <span data-ttu-id="19c64-155">Cuando se instala BizTalk Server, el seguimiento puede habilitarse en el **BizTalk Server Application 1** host.</span><span class="sxs-lookup"><span data-stu-id="19c64-155">When BizTalk Server is installed, tracking may be enabled on the **BizTalk Server Application 1** host.</span></span> <span data-ttu-id="19c64-156">Normalmente, esta aplicación también se usa para procesar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="19c64-156">Typically, this application is also used to process messages.</span></span> <span data-ttu-id="19c64-157">Crear un host de seguimiento dedicado siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="19c64-157">Create a dedicated tracking host using the following steps:</span></span> 

    1. <span data-ttu-id="19c64-158">En administración de BizTalk Server, abra las propiedades del host de BizTalk Server Application 1 y desactive la opción **Permitir seguimiento de Host**.</span><span class="sxs-lookup"><span data-stu-id="19c64-158">In BizTalk Server Administration, open the properties of the BizTalk Server Application 1 host, and uncheck **Allow Host Tracking**.</span></span> <span data-ttu-id="19c64-159">Reinicie la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="19c64-159">Restart this host instance.</span></span>

    2. <span data-ttu-id="19c64-160">Cree un nuevo host denominado **seguimiento**y compruebe **Permitir seguimiento de Host**.</span><span class="sxs-lookup"><span data-stu-id="19c64-160">Create a new host named **Tracking**, and check **Allow Host Tracking**.</span></span> <span data-ttu-id="19c64-161">Crear una instancia de host e inícielo.</span><span class="sxs-lookup"><span data-stu-id="19c64-161">Create a host instance, and start it.</span></span>

<span data-ttu-id="19c64-162">A continuación, volver a consultar las tablas de BizTalkMsgBoxDb TrackingData_2_x.</span><span class="sxs-lookup"><span data-stu-id="19c64-162">Now, query the BizTalkMsgBoxDb TrackingData_2_x tables again.</span></span> <span data-ttu-id="19c64-163">Si las tablas están vacías, a continuación, los datos se ha movido y deben comenzar a mostrar en Application Insights.</span><span class="sxs-lookup"><span data-stu-id="19c64-163">If the tables are empty, then the data was moved, and should start displaying in Application Insights.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19c64-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="19c64-164">See also</span></span>
 [<span data-ttu-id="19c64-165">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="19c64-165">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)