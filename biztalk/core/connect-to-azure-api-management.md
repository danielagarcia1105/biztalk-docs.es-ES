---
title: "Publicar extremos SOAP administración de API | Documentos de Microsoft"
description: "Utilice Feature Pack 1 y Feature Pack 2 para exponer un HTTP de WCF-Basic BizTalk ubicación de recepción como un extremo SOAP en administración de API. Puede hacerlo mediante la consola de administración de BizTalk o pegue el punto de conexión directamente dentro de la API de administración en el portal de Azure."
ms.custom: 
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: 8ac1e824ad11ef18eac6deb1252101bbd1ec187a
ms.sourcegitcommit: f65e8ed2b8c18cded26b9d60868fb6a56bcc1205
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a><span data-ttu-id="e1077-104">Publicar extremos de SOAP de BizTalk en administración de API</span><span class="sxs-lookup"><span data-stu-id="e1077-104">Publish BizTalk SOAP endpoints in API Management</span></span>

<span data-ttu-id="e1077-105">Exponer los extremos de SOAP de BizTalk como servicios de administración de API de Azure.</span><span class="sxs-lookup"><span data-stu-id="e1077-105">Expose your BizTalk SOAP endpoints as services within Azure API Management.</span></span> 

<span data-ttu-id="e1077-106">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, puede exponer un extremo SOAP a través de la API de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1077-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, you can expose a SOAP endpoint through API Management from BizTalk.</span></span> <span data-ttu-id="e1077-107">Puede hacerlo mediante la API de administración en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="e1077-107">You can do this using  API Management in the Azure portal.</span></span> 

<span data-ttu-id="e1077-108">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede exponer un WCF-BasicHTTP ubicación de recepción como un punto de conexión en administración de API de Azure mediante la administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1077-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can expose a WCF-BasicHTTP receive location as an endpoint within Azure API Management using BizTalk Administration.</span></span> 

> [!TIP]
> <span data-ttu-id="e1077-109">[¿Qué es la administración de API? ](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts) es un excelente recurso para comprender y obtener más información sobre este servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="e1077-109">[What is API Management?](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts) is a great resource to understand and learn more about this Azure service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1077-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e1077-110">Prerequisites</span></span>
* <span data-ttu-id="e1077-111">Configurar y establecer [administración de API de Azure](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="e1077-111">Configure and set up [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="e1077-112">Crear un [red virtual](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) entre el equipo de BizTalk y la instancia de la administración de API</span><span class="sxs-lookup"><span data-stu-id="e1077-112">Create a [virtual network](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) between your BizTalk computer and the API Management instance</span></span>
* <span data-ttu-id="e1077-113">Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en el servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e1077-113">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on the BizTalk Server</span></span>

## <a name="create-using-api-management-in-azure-portal"></a><span data-ttu-id="e1077-114">Crear mediante administración de API en el portal de Azure</span><span class="sxs-lookup"><span data-stu-id="e1077-114">Create using API Management in Azure portal</span></span> 
1. <span data-ttu-id="e1077-115">En el [portal de Azure](https://portal.azure.com), abra la administración de API y seleccione **API**:</span><span class="sxs-lookup"><span data-stu-id="e1077-115">In the [Azure portal](https://portal.azure.com), open up your API management, and select **APIs**:</span></span>

    ![Seleccione la API de BizTalk](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="e1077-117">Seleccione **WSDL**:</span><span class="sxs-lookup"><span data-stu-id="e1077-117">Select **WSDL**:</span></span>

    ![Seleccione wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="e1077-119">Configurar las propiedades WSDL:</span><span class="sxs-lookup"><span data-stu-id="e1077-119">Configure your WSDL properties:</span></span> 

    1. <span data-ttu-id="e1077-120">**Especificación de WSDL** : escriba el URI completo al extremo SOAP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e1077-120">**WSDL specification** : Enter the full URI to your BizTalk SOAP endpoint.</span></span> <span data-ttu-id="e1077-121">Por ejemplo, escriba algo parecido a `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` o `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="e1077-121">For example, enter something like `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` or `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span></span>  

    2. <span data-ttu-id="e1077-122">**Paso a través SOAP** o **SOAP al resto** : seleccione sus preferencias:</span><span class="sxs-lookup"><span data-stu-id="e1077-122">**SOAP pass-through** or **SOAP to REST** : Select your preference:</span></span> 
        * <span data-ttu-id="e1077-123">**SOAP al resto**: crear REST APIs basadas en HTTP desde un servicio web basado en SOAP existente</span><span class="sxs-lookup"><span data-stu-id="e1077-123">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web service</span></span>
        * <span data-ttu-id="e1077-124">**Paso a través SOAP**: actúa como un proxy para la API de SOAP</span><span class="sxs-lookup"><span data-stu-id="e1077-124">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

    3. <span data-ttu-id="e1077-125">Escriba su preferido **nombre para mostrar**, **nombre**, **descripción**, **sufijo de Url de la API**, **productos**, y **versión**.</span><span class="sxs-lookup"><span data-stu-id="e1077-125">Enter your preferred **Display Name**, **Name**, **Description**, **API Url suffix**, **Products**, and **Version**.</span></span>

    <span data-ttu-id="e1077-126">Cuando termine, la configuración de WSDL tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1077-126">When finished, your WSDL configuration looks something like the following:</span></span> 

    ![crear API de BizTalk de WSDL](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="e1077-128">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e1077-128">Select **Create**.</span></span>

## <a name="create-using-the-biztalk-administration"></a><span data-ttu-id="e1077-129">Crear mediante la administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e1077-129">Create using the BizTalk Administration</span></span>

> [!NOTE] 
> <span data-ttu-id="e1077-130">Esta característica es compatible con WCF-BasicHTTP ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e1077-130">This feature is supported with WCF-BasicHTTP receive locations.</span></span> 

1. <span data-ttu-id="e1077-131">En la consola de administración de BizTalk, haga el WCF-BasicHTTP ubicación de recepción y seleccione **publicar en administración de API**:</span><span class="sxs-lookup"><span data-stu-id="e1077-131">In the BizTalk Administration Console, right-click your WCF-BasicHTTP receive location, and select **Publish to API Management**:</span></span>  

    ![publicar la opción de menú](../core/media/publish-to-api-management-option.png)
 
2. <span data-ttu-id="e1077-133">Configurar las propiedades de administración de API:</span><span class="sxs-lookup"><span data-stu-id="e1077-133">Configure your API management properties:</span></span> 

    1. <span data-ttu-id="e1077-134">**Inicio de sesión** a su suscripción de Azure, seleccione la **suscripción** y **grupo de recursos** con la administración de API de servicio y, a continuación, seleccione su servicio.</span><span class="sxs-lookup"><span data-stu-id="e1077-134">**Sign-in** to your Azure subscription, select the **Subscription** and **Resource Group** that has your API management service, and then select your service.</span></span>

    2. <span data-ttu-id="e1077-135">El **vínculo de la especificación de WSDL** se rellena automáticamente con el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="e1077-135">The **WSDL specification link** is automatically populated with your WSDL file.</span></span> <span data-ttu-id="e1077-136">Reemplace **localhost** con el nombre DNS o dirección IP del servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e1077-136">Replace **localhost** with the DNS name or IP address of the BizTalk Server.</span></span> 

    3. <span data-ttu-id="e1077-137">Seleccione **paso a través SOAP** o **SOAP al resto**:</span><span class="sxs-lookup"><span data-stu-id="e1077-137">Select **SOAP pass-through** or **SOAP to REST**:</span></span>  
        * <span data-ttu-id="e1077-138">**SOAP al resto**: crear REST APIs basadas en HTTP desde un servicios web basados en SOAP existentes</span><span class="sxs-lookup"><span data-stu-id="e1077-138">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web services</span></span>
        * <span data-ttu-id="e1077-139">**Paso a través SOAP**: actúa como un proxy para la API de SOAP</span><span class="sxs-lookup"><span data-stu-id="e1077-139">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

        <span data-ttu-id="e1077-140">La API se puede publicar ambas formas cambiando el **sufijo de URL de la API**y, a continuación, publicar utilizando un tipo diferente de la API de nuevo.</span><span class="sxs-lookup"><span data-stu-id="e1077-140">The API can be published both ways by changing the **API URL suffix**, and then publishing again using a different API type.</span></span>

    4. <span data-ttu-id="e1077-141">El **nombre de la API** se rellena automáticamente con el nombre de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e1077-141">The **API name** is automatically populated with the receive location name.</span></span>

    5. <span data-ttu-id="e1077-142">Seleccione un **sufijo de URL de la API** que va a ser utilizado por los consumidores de la API.</span><span class="sxs-lookup"><span data-stu-id="e1077-142">Select an **API URL suffix** that is to be used by consumers of the API.</span></span> 

    <span data-ttu-id="e1077-143">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1077-143">When finished, your properties look similar to the following:</span></span>  
    ![publicar en la ventana de API](../core/media/api-management-publish-window.png)


3. <span data-ttu-id="e1077-145">Seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="e1077-145">Select **Publish**.</span></span> <span data-ttu-id="e1077-146">Cuando se realiza correctamente, la ubicación de recepción se muestra como un servicio de administración de API en el [portal de Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="e1077-146">When successful, the receive location is displayed as a service in API Management in the [Azure portal](https://portal.azure.com).</span></span> 

## <a name="do-more"></a><span data-ttu-id="e1077-147">Llevar a cabo más</span><span class="sxs-lookup"><span data-stu-id="e1077-147">Do more</span></span>
<span data-ttu-id="e1077-148">Administración de API de Azure es un servicio eficaz que se utiliza una gran cantidad de servicios de Azure, incluidas las aplicaciones de lógica.</span><span class="sxs-lookup"><span data-stu-id="e1077-148">Azure API Management is a powerful service that is used by a lot of Azure services, including Logic Apps.</span></span> <span data-ttu-id="e1077-149">Administración de API incluye muchas características, incluidos los límites de velocidad y las cuotas, quién tiene acceso a las API, almacenar en caché y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e1077-149">API Management includes many features, including rate limits and quotas, who has access to your APIs, caching, and more.</span></span> <span data-ttu-id="e1077-150">Vea [¿qué es la administración de API?](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts) para empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="e1077-150">See [What is API Management?](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts) to get started.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1077-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1077-151">See also</span></span>
[<span data-ttu-id="e1077-152">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="e1077-152">Configure the feature pack</span></span>](configure-the-feature-pack.md)
