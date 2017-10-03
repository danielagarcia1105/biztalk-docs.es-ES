---
title: Enviar datos de seguimiento a Azure Application Insights mediante BizTalk Server | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3ff6cb9-44d0-46cd-9b4f-a346365afb7b
caps.latest.revision: "10"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: f587c3049e191505c87ba456b5ddfd41011862c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="send-tracking-data-to-azure-application-insights-using-biztalk-server"></a><span data-ttu-id="44567-102">Enviar datos de seguimiento a Azure Application Insights con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="44567-102">Send tracking data to Azure Application Insights using BizTalk Server</span></span>
<span data-ttu-id="44567-103">Enviar [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] datos de seguimiento para Inisights de aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="44567-103">Send [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] tracking data to Azure Application Inisights.</span></span> 

<span data-ttu-id="44567-104">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** , le permitirán procesar y enviar los datos de seguimiento a Azure Application Insights.</span><span class="sxs-lookup"><span data-stu-id="44567-104">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, you can process and send your tracking data to Azure Application Insights.</span></span> <span data-ttu-id="44567-105">Usar las características de Application Insights para realizar el seguimiento de las instancias de puertos de recepción, puertos de envío y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="44567-105">Use the Application Insights features to track your instances from receive ports, send ports, and orchestrations.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44567-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="44567-106">Prerequisites</span></span>
* <span data-ttu-id="44567-107">Crear una nueva instancia de [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)</span><span class="sxs-lookup"><span data-stu-id="44567-107">Create a new instance of [Application Insights](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)</span></span>
* <span data-ttu-id="44567-108">Instalar [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100) en el[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44567-108">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>

## <a name="enable-analytics-for-your-environment"></a><span data-ttu-id="44567-109">Habilitar el análisis de su entorno</span><span class="sxs-lookup"><span data-stu-id="44567-109">Enable analytics for your environment</span></span>

1. <span data-ttu-id="44567-110">Abra la **administración de BizTalk Server** de la consola, expanda **de administración de BizTalk**, haga clic en el **grupo de BizTalk**y seleccione **configuración**.</span><span class="sxs-lookup"><span data-stu-id="44567-110">Open the **BizTalk Server Administration** console, expand **BizTalk Administration**, right-click the **BizTalk Group**, and select **Settings**.</span></span> 
2. <span data-ttu-id="44567-111">Comprobar **habilitar el análisis de nivel de grupo**.</span><span class="sxs-lookup"><span data-stu-id="44567-111">Check **Enable group-level analytics**.</span></span>
3. <span data-ttu-id="44567-112">Para el **tipo de destino**, seleccione **Application Insight** en la lista.</span><span class="sxs-lookup"><span data-stu-id="44567-112">For the **Target type**, select **Application Insight** from the list.</span></span>
4. <span data-ttu-id="44567-113">Para el **parámetros de conexión**, escriba la información de la aplicación  **[clave de instrumentación](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)**  (disponible en el portal de Azure).</span><span class="sxs-lookup"><span data-stu-id="44567-113">For the **Connection parameters**, enter your Application Insights **[instrumentation key](https://docs.microsoft.com/en-us/azure/application-insights/app-insights-create-new-resource)** (available in the Azure portal).</span></span>

    <span data-ttu-id="44567-114">La configuración del grupo un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44567-114">Your Group settings look similar to the following:</span></span> 

    ![Habilitar el análisis de su entorno](../core/media/environmentsettingapplicationinishgt.PNG)

5. <span data-ttu-id="44567-116">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="44567-116">Select **OK** to save your changes.</span></span> 

<span data-ttu-id="44567-117">Una vez habilitada, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] está listo para transmitir datos a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="44567-117">Once enabled, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] is ready to transmit data to Application Insights.</span></span> <span data-ttu-id="44567-118">A continuación, habilitar el análisis en los puertos y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="44567-118">Next, enable analytics on your ports and orchestrations.</span></span> 

## <a name="enable-analytics-on-your-artifacts"></a><span data-ttu-id="44567-119">Habilitar el análisis en los artefactos</span><span class="sxs-lookup"><span data-stu-id="44567-119">Enable analytics on your artifacts</span></span>

1. <span data-ttu-id="44567-120">En administración de BizTalk Server, haga clic en un **puerto de recepción**, **puerto de envío** o **orquestación**y seleccione **seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="44567-120">In BizTalk Server Administration, right-click a **receive port**, **send port** or **orchestration**, and select **Tracking**.</span></span>
2. <span data-ttu-id="44567-121">En **análisis**, comprobar **Habilitar análisis**.</span><span class="sxs-lookup"><span data-stu-id="44567-121">Under **Analytics**, check **Enable Analytics**.</span></span> <span data-ttu-id="44567-122">Esta opción inicia el seguimiento y transmitir datos desde el artefacto a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="44567-122">This setting starts tracking and transmitting data from the artifact to Application Insights.</span></span>

    <span data-ttu-id="44567-123">La configuración del artefacto un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="44567-123">Your artifact settings look similar to the following:</span></span> 
    
    ![Datos de seguimiento para la orquestación](../core/media/orchestrationsettingsapplicationinsight.PNG)

3. <span data-ttu-id="44567-125">Seleccione **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="44567-125">Select **OK** to save your changes.</span></span>

<span data-ttu-id="44567-126">A continuación, ejecute las consultas en Application Insights para ver los datos.</span><span class="sxs-lookup"><span data-stu-id="44567-126">Next, run queries within Application Insights to see your data.</span></span>  

> [!TIP]
> <span data-ttu-id="44567-127">Conectar los análisis de BizTalk Server con otros sistemas para obtener más información sobre los datos de las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="44567-127">Connect your BizTalk Server Analytics with other systems to gain even more insight into your organizations data.</span></span>

## <a name="run-queries-on-your-data"></a><span data-ttu-id="44567-128">Ejecutar consultas en los datos</span><span class="sxs-lookup"><span data-stu-id="44567-128">Run queries on your data</span></span>
<span data-ttu-id="44567-129">Una vez que los datos se envían a Application Insights, puede usar las herramientas de análisis dentro de Azure para crear consultas avanzadas y analizar los datos.</span><span class="sxs-lookup"><span data-stu-id="44567-129">Once the data is sent to Application Insights, you can use the analytics tools within Azure to create advanced queries, and analyze your data.</span></span>

1. <span data-ttu-id="44567-130">Inicie sesión en el [Portal de Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="44567-130">Sign in to the [Azure Portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="44567-131">Abra el recurso de Application Insights y seleccione **análisis**.</span><span class="sxs-lookup"><span data-stu-id="44567-131">Open your Application Insights resource, and select **Analytics**.</span></span>
3. <span data-ttu-id="44567-132">Seleccione **uso**, y ejecute la consulta proporcionada.</span><span class="sxs-lookup"><span data-stu-id="44567-132">Select **usage**, and run the query provided.</span></span>

    > [!TIP]
    > <span data-ttu-id="44567-133">Obtener más información sobre cómo escribir consultas en Application Insights en [funciones analíticas en Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics).</span><span class="sxs-lookup"><span data-stu-id="44567-133">Learn more about how to write queries in Application Insights at [Analytics in Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-analytics).</span></span>
    
## <a name="see-also"></a><span data-ttu-id="44567-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="44567-134">See also</span></span>
 [<span data-ttu-id="44567-135">Configurar el Feature Pack</span><span class="sxs-lookup"><span data-stu-id="44567-135">Configure the Feature Pack</span></span>](../core/configure-the-feature-pack.md)