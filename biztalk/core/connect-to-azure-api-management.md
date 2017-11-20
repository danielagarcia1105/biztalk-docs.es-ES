---
title: "Conectarse a la administración de API de Azure mediante BizTalk Server | Documentos de Microsoft"
description: "Usar BizTalk Feature Pack 1 para conectarse a la administración de API de servidor BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a87bfb40-7e6f-46aa-8ac7-db6d13ce7eb2
caps.latest.revision: "2"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: d0c5e4cd2a0ebbd7108845ea15de468d0e0a5a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-azure-api-management"></a><span data-ttu-id="138a7-103">Conectarse a la administración de API de Azure</span><span class="sxs-lookup"><span data-stu-id="138a7-103">Connect to Azure API Management</span></span>
<span data-ttu-id="138a7-104">Ahora puede exponer fácilmente su extremo SOAP a través de la API de administración de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="138a7-104">You can now easily expose your SOAP endpoint through API Management from BizTalk.</span></span>

## <a name="what-is-azure-api-management"></a><span data-ttu-id="138a7-105">¿Qué es la administración de API de Azure</span><span class="sxs-lookup"><span data-stu-id="138a7-105">What is Azure API Management</span></span>
<span data-ttu-id="138a7-106">Use Administración de API de Azure como una solución integrada para la publicación de API a los clientes internos y externos.</span><span class="sxs-lookup"><span data-stu-id="138a7-106">Use Azure API Management as a turnkey solution for publishing APIs to external and internal customers.</span></span> <span data-ttu-id="138a7-107">Crear rápidamente coherente y modernas puertas de enlace de API para los servicios back-end existentes hospedados en cualquier lugar, proteger y protegerlos de abuso y uso excesivo y obtendrá información sobre el uso y estado.</span><span class="sxs-lookup"><span data-stu-id="138a7-107">Quickly create consistent and modern API gateways for existing back-end services hosted anywhere, secure and protect them from abuse and overuse, and get insights into usage and health.</span></span> <span data-ttu-id="138a7-108">Además, automatizar y escalar la incorporación de desarrollador para ayudar a conseguir que un programa API activos y en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="138a7-108">Plus, automate and scale developer onboarding to help get your API program up and running.</span></span> 

<span data-ttu-id="138a7-109">Vea [administración de API](https://azure.microsoft.com/en-us/services/api-management/) para obtener más información sobre la administración de API.</span><span class="sxs-lookup"><span data-stu-id="138a7-109">See [API Management](https://azure.microsoft.com/en-us/services/api-management/) to learn more about API Management.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="138a7-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="138a7-110">Prerequisites</span></span>
* <span data-ttu-id="138a7-111">Configurar y establecer [administración de API de Azure](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span><span class="sxs-lookup"><span data-stu-id="138a7-111">Configure and set up [Azure API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-get-started)</span></span>
* <span data-ttu-id="138a7-112">Crear un [red virtual](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet) entre el equipo de BizTalk y la instancia de la administración de API</span><span class="sxs-lookup"><span data-stu-id="138a7-112">Create a [virtual network](https://docs.microsoft.com/en-us/azure/api-management/api-management-using-with-vnet) between your BizTalk Machine and the API Managemenet instance</span></span>


1. <span data-ttu-id="138a7-113">En el portal de Azure, abra la administración de API y seleccione **API** en el menú:</span><span class="sxs-lookup"><span data-stu-id="138a7-113">In the Azure portal, open up your API management, and select **APIs** from the menu:</span></span>

    ![Seleccione la API de BizTalk](../core/media/select-api-for-biztalk.png)
    
2. <span data-ttu-id="138a7-115">Seleccione la opción de **WSDL** en la sección de la nueva API:</span><span class="sxs-lookup"><span data-stu-id="138a7-115">Select the option for **WSDL** in the New API section:</span></span>

    ![Seleccione wsdl biztalk api](../core/media/select-wsdl-biztalk-api.png)
    
3. <span data-ttu-id="138a7-117">Para conectarse a la administración de API a su WSDL de BizTalk, copie la dirección URL en el equipo de BizTalk con el URI completo al extremo de SOAP.</span><span class="sxs-lookup"><span data-stu-id="138a7-117">To connect to API Management to your BizTalk WSDL, copy the URL to your BizTalk computer with the full URI to your SOAP endpoint.</span></span> <span data-ttu-id="138a7-118">Por ejemplo, copie `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:</span><span class="sxs-lookup"><span data-stu-id="138a7-118">For example, copy `http://10.0.31.22/RestEndPoint/OrderIncome.svc?wsdl`:</span></span>

    ![crear API de BizTalk de WSDL](../core/media/create-api-from-wsdl-biztalk.png)

4. <span data-ttu-id="138a7-120">Seleccione si desea usar un **paso a través SOAP**, o configuraré un **SOAP al resto** servicio.</span><span class="sxs-lookup"><span data-stu-id="138a7-120">Select if you want to use a **SOAP pass-through**, or set up a **SOAP to REST** service.</span></span>
5. <span data-ttu-id="138a7-121">Escriba el **nombre** de la API, el **descripción**y el **sufijo de Url de la API** para el servicio.</span><span class="sxs-lookup"><span data-stu-id="138a7-121">Enter the **name** of your API, the **Description**, and the **API Url suffix** for your service.</span></span>
6. <span data-ttu-id="138a7-122">Seleccione **crear** para crear la comunicación con su punto de conexión SOAP de back-end.</span><span class="sxs-lookup"><span data-stu-id="138a7-122">Select **Create** to create the communication to your backend SOAP endpoint.</span></span>

## <a name="see-also"></a><span data-ttu-id="138a7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="138a7-123">See also</span></span>
[<span data-ttu-id="138a7-124">Configuración del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="138a7-124">Configure the feature pack</span></span>](configure-the-feature-pack.md)