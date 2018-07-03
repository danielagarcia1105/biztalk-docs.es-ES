---
title: Publicar puntos de conexión SOAP API Management | Microsoft Docs
description: Utilice Feature Pack 1 y Feature Pack 2 para exponer un HTTP de WCF-Basic BizTalk ubicación de recepción como un extremo SOAP en API management. Puede hacerlo mediante la consola de administración de BizTalk, o pegar el punto de conexión directamente en API Management en Azure portal.
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: 2
author: MandiOhlinger
ms.author: valrobb
manager: anneta
ms.openlocfilehash: c8bdb3cb3f2d0fc247ea607a1b34623006315754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993717"
---
# <a name="publish-biztalk-soap-endpoints-in-api-management"></a><span data-ttu-id="e15ca-104">Publicar puntos de conexión de SOAP de BizTalk en API Management</span><span class="sxs-lookup"><span data-stu-id="e15ca-104">Publish BizTalk SOAP endpoints in API Management</span></span>

<span data-ttu-id="e15ca-105">Exponer los extremos de SOAP de BizTalk como servicios en Azure API Management.</span><span class="sxs-lookup"><span data-stu-id="e15ca-105">Expose your BizTalk SOAP endpoints as services within Azure API Management.</span></span> 

<span data-ttu-id="e15ca-106">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, puede exponer un extremo SOAP a través de la API de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e15ca-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 1**, you can expose a SOAP endpoint through API Management from BizTalk.</span></span> <span data-ttu-id="e15ca-107">Puede hacerlo mediante la API de administración en el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="e15ca-107">You can do this using  API Management in the Azure portal.</span></span> 

<span data-ttu-id="e15ca-108">**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, puede exponer un WCF-BasicHTTP ubicación de recepción como un punto de conexión en Azure API Management mediante la administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e15ca-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, you can expose a WCF-BasicHTTP receive location as an endpoint within Azure API Management using BizTalk Administration.</span></span> 

> [!TIP]
> <span data-ttu-id="e15ca-109">[¿Qué es API Management? ](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) es un excelente recurso para comprender y obtener más información sobre este servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="e15ca-109">[What is API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) is a great resource to understand and learn more about this Azure service.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e15ca-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e15ca-110">Prerequisites</span></span>
* <span data-ttu-id="e15ca-111">Configurar e instalar [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="e15ca-111">Configure and set up [Azure API Management](https://docs.microsoft.com/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="e15ca-112">Crear un [red virtual](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) entre el equipo de BizTalk y la instancia de API Management</span><span class="sxs-lookup"><span data-stu-id="e15ca-112">Create a [virtual network](https://docs.microsoft.com/azure/api-management/api-management-using-with-vnet) between your BizTalk computer and the API Management instance</span></span>
* <span data-ttu-id="e15ca-113">Instalar [Feature Pack 2 de](https://aka.ms/bts2016fp2) en BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e15ca-113">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on the BizTalk Server</span></span>

## <a name="create-using-api-management-in-azure-portal"></a><span data-ttu-id="e15ca-114">Crear con API Management en Azure portal</span><span class="sxs-lookup"><span data-stu-id="e15ca-114">Create using API Management in Azure portal</span></span> 
1. <span data-ttu-id="e15ca-115">En el [portal Azure](https://portal.azure.com), abra la administración de API y seleccione **API**:</span><span class="sxs-lookup"><span data-stu-id="e15ca-115">In the [Azure portal](https://portal.azure.com), open up your API management, and select **APIs**:</span></span>

    ![Seleccione la API de BizTalk](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="e15ca-117">Seleccione **WSDL**:</span><span class="sxs-lookup"><span data-stu-id="e15ca-117">Select **WSDL**:</span></span>

    ![Seleccione wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="e15ca-119">Configure las propiedades de WSDL:</span><span class="sxs-lookup"><span data-stu-id="e15ca-119">Configure your WSDL properties:</span></span> 

   1. <span data-ttu-id="e15ca-120">**Especificación WSDL** : escriba el URI completo a su extremo de SOAP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e15ca-120">**WSDL specification** : Enter the full URI to your BizTalk SOAP endpoint.</span></span> <span data-ttu-id="e15ca-121">Por ejemplo, escriba algo parecido a `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` o `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="e15ca-121">For example, enter something like `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl` or `http://biztalkfp1.westus.cloudapp.azure.com/RestEndPoint/OrderIncome.svc?wsdl`.</span></span>  

   2. <span data-ttu-id="e15ca-122">**Paso a través SOAP** o **SOAP a REST** : seleccione la preferencia:</span><span class="sxs-lookup"><span data-stu-id="e15ca-122">**SOAP pass-through** or **SOAP to REST** : Select your preference:</span></span> 
       * <span data-ttu-id="e15ca-123">**SOAP a REST**: crear REST APIs basadas en HTTP desde un servicio web basado en SOAP existente</span><span class="sxs-lookup"><span data-stu-id="e15ca-123">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web service</span></span>
       * <span data-ttu-id="e15ca-124">**Paso a través SOAP**: actúa como un proxy para la API de SOAP</span><span class="sxs-lookup"><span data-stu-id="e15ca-124">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

   3. <span data-ttu-id="e15ca-125">Escriba su preferido **nombre para mostrar**, **nombre**, **descripción**, **sufijo Url de API**, **productos**, y **versión**.</span><span class="sxs-lookup"><span data-stu-id="e15ca-125">Enter your preferred **Display Name**, **Name**, **Description**, **API Url suffix**, **Products**, and **Version**.</span></span>

      <span data-ttu-id="e15ca-126">Cuando termine, la configuración de WSDL tiene un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e15ca-126">When finished, your WSDL configuration looks something like the following:</span></span> 

      ![creación de API de WSDL de BizTalk](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="e15ca-128">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="e15ca-128">Select **Create**.</span></span>

## <a name="create-using-the-biztalk-administration"></a><span data-ttu-id="e15ca-129">Crear mediante la administración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e15ca-129">Create using the BizTalk Administration</span></span>

> [!NOTE] 
> <span data-ttu-id="e15ca-130">Esta característica es compatible con WCF-BasicHTTP las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="e15ca-130">This feature is supported with WCF-BasicHTTP receive locations.</span></span> 

1. <span data-ttu-id="e15ca-131">En la consola de administración de BizTalk, haga el WCF-BasicHTTP ubicación de recepción y seleccione **publicar en API Management**:</span><span class="sxs-lookup"><span data-stu-id="e15ca-131">In the BizTalk Administration Console, right-click your WCF-BasicHTTP receive location, and select **Publish to API Management**:</span></span>  

    ![opción de menú de publicación](../core/media/publish-to-api-management-option.png)
 
2. <span data-ttu-id="e15ca-133">Configurar las propiedades de administración de API:</span><span class="sxs-lookup"><span data-stu-id="e15ca-133">Configure your API management properties:</span></span> 

   1. <span data-ttu-id="e15ca-134">**Inicio de sesión** a su suscripción de Azure, seleccione el **suscripción** y **grupo de recursos** que tiene la administración de API de servicio y, a continuación, seleccione el servicio.</span><span class="sxs-lookup"><span data-stu-id="e15ca-134">**Sign-in** to your Azure subscription, select the **Subscription** and **Resource Group** that has your API management service, and then select your service.</span></span>

   2. <span data-ttu-id="e15ca-135">El **vínculo de especificación WSDL** se rellena automáticamente con el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="e15ca-135">The **WSDL specification link** is automatically populated with your WSDL file.</span></span> <span data-ttu-id="e15ca-136">Reemplace **localhost** con el nombre DNS o dirección IP del servidor de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e15ca-136">Replace **localhost** with the DNS name or IP address of the BizTalk Server.</span></span> 

   3. <span data-ttu-id="e15ca-137">Seleccione **paso a través SOAP** o **SOAP a REST**:</span><span class="sxs-lookup"><span data-stu-id="e15ca-137">Select **SOAP pass-through** or **SOAP to REST**:</span></span>  
      * <span data-ttu-id="e15ca-138">**SOAP a REST**: crear REST APIs basadas en HTTP desde un servicios web basados en SOAP existentes</span><span class="sxs-lookup"><span data-stu-id="e15ca-138">**SOAP to REST**: Create REST-based HTTP APIs from an existing SOAP-based web services</span></span>
      * <span data-ttu-id="e15ca-139">**Paso a través SOAP**: actúa como un proxy para la API de SOAP</span><span class="sxs-lookup"><span data-stu-id="e15ca-139">**SOAP pass-through**: Acts as a proxy for the SOAP API</span></span> 

        <span data-ttu-id="e15ca-140">La API se puede publicar ambas formas cambiando el **sufijo URL de API**y, a continuación, publicar de nuevo con un tipo diferente de la API.</span><span class="sxs-lookup"><span data-stu-id="e15ca-140">The API can be published both ways by changing the **API URL suffix**, and then publishing again using a different API type.</span></span>

   4. <span data-ttu-id="e15ca-141">El **nombre de la API** se rellena automáticamente con el nombre de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="e15ca-141">The **API name** is automatically populated with the receive location name.</span></span>

   5. <span data-ttu-id="e15ca-142">Seleccione un **sufijo URL de API** que va a ser utilizado por los consumidores de la API.</span><span class="sxs-lookup"><span data-stu-id="e15ca-142">Select an **API URL suffix** that is to be used by consumers of the API.</span></span> 

      <span data-ttu-id="e15ca-143">Cuando termine, las propiedades de aspecto similares al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e15ca-143">When finished, your properties look similar to the following:</span></span>  
      ![publicar en la ventana de la API](../core/media/api-management-publish-window.png)


3. <span data-ttu-id="e15ca-145">Seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="e15ca-145">Select **Publish**.</span></span> <span data-ttu-id="e15ca-146">Cuando se realiza correctamente, se muestra la ubicación de recepción como un servicio de API Management en el [portal Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="e15ca-146">When successful, the receive location is displayed as a service in API Management in the [Azure portal](https://portal.azure.com).</span></span> 

## <a name="do-more"></a><span data-ttu-id="e15ca-147">Hacer más cosas</span><span class="sxs-lookup"><span data-stu-id="e15ca-147">Do more</span></span>
<span data-ttu-id="e15ca-148">Azure API Management es un servicio eficaz que se usa una buena cantidad de servicios de Azure, incluidas las aplicaciones lógicas.</span><span class="sxs-lookup"><span data-stu-id="e15ca-148">Azure API Management is a powerful service that is used by a lot of Azure services, including Logic Apps.</span></span> <span data-ttu-id="e15ca-149">API Management incluye muchas características, incluidos los límites de velocidad y cuotas, quién tiene acceso a las API, almacenamiento en caché y mucho más.</span><span class="sxs-lookup"><span data-stu-id="e15ca-149">API Management includes many features, including rate limits and quotas, who has access to your APIs, caching, and more.</span></span> <span data-ttu-id="e15ca-150">Consulte [¿qué es API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) para empezar a trabajar.</span><span class="sxs-lookup"><span data-stu-id="e15ca-150">See [What is API Management?](https://docs.microsoft.com/azure/api-management/api-management-key-concepts) to get started.</span></span>

## <a name="see-also"></a><span data-ttu-id="e15ca-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="e15ca-151">See also</span></span>
[<span data-ttu-id="e15ca-152">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="e15ca-152">Configure the feature pack</span></span>](configure-the-feature-pack.md)
