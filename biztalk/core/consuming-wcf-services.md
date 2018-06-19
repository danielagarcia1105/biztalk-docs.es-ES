---
title: Consumir servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- consuming, WCF services
- WCF services, consuming
ms.assetid: ca6c0514-c1df-43ad-8f02-df117271b0b5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3fc0764295cbbc793b07757691e1f0c730a4049
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237868"
---
# <a name="consuming-wcf-services"></a><span data-ttu-id="0d9db-102">Consumir servicios WCF</span><span class="sxs-lookup"><span data-stu-id="0d9db-102">Consuming WCF Services</span></span>
<span data-ttu-id="0d9db-103">El consumo de servicios WCF le habilita para agregar servicios WCF existentes al proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="0d9db-103">Consuming WCF services enables you to add existing WCF services to your business process.</span></span> <span data-ttu-id="0d9db-104">Es posible agregar varios servicios WCF a una única orquestación.</span><span class="sxs-lookup"><span data-stu-id="0d9db-104">You can aggregate several WCF services into a single orchestration.</span></span>  
  
 <span data-ttu-id="0d9db-105">Por medio del Asistente para consumición del Servicio WCF de BizTalk, puede consumir (llamar) a un Servicio WCF desde la orquestación.</span><span class="sxs-lookup"><span data-stu-id="0d9db-105">You can consume (call) a WCF service from your orchestration by using the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="0d9db-106">Este Asistente crea los tipos de mensaje y de puerto necesarios para consumir servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="0d9db-106">The BizTalk WCF Service Consuming Wizard creates port types and message types necessary for consuming WCF services.</span></span> <span data-ttu-id="0d9db-107">Además, el Asistente para consumición del Servicio WCF de BizTalk crea dos archivos de enlace que se pueden importar utilizando el asistente o la herramienta de línea de comandos de desarrollo con el fin de configurar puertos de envío con el adaptador personalizado de WCF y los adaptadores de WCF proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="0d9db-107">The BizTalk WCF Service Consuming Wizard also creates two binding files that can be imported by the development command-line tool or wizard to configure the send ports with the system-provided binding WCF adapters and the WCF-Custom adapter.</span></span> <span data-ttu-id="0d9db-108">El asistente permite usar encabezados SOAP con un servicio WCF consumido, cambiar el URI de un servicio WCF consumido y establecer de forma dinámica el WCF para un servicio web consumido.</span><span class="sxs-lookup"><span data-stu-id="0d9db-108">The wizard allows you to use SOAP headers with a consumed WCF service, change the URI of a consumed WCF service, and dynamically set the WCF for a consumed Web service.</span></span> <span data-ttu-id="0d9db-109">Los adaptadores de envío WCF consumen servicios WCF y las publicaciones de recepción WCF publican servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="0d9db-109">WCF send adapters consume WCF services and WCF receive locations publish WCF services.</span></span>  
  
 <span data-ttu-id="0d9db-110">Los adaptadores de envío de WCF de BizTalk incluyen cinco adaptadores de envío físicos que representan los enlaces predefinidos de WCF **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, y **NetMsmqBinding**.</span><span class="sxs-lookup"><span data-stu-id="0d9db-110">The BizTalk WCF send adapters include five physical send adapters that represent the WCF predefined bindings **BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="0d9db-111">Asimismo, los adaptadores de WCF de BizTalk incorporan los adaptadores personalizados que permiten configurar libremente la información de comportamiento y enlace de WCF en un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="0d9db-111">The BizTalk WCF adapters also include the custom adapters that enable you to freely configure WCF binding and behavior information for a send port.</span></span> <span data-ttu-id="0d9db-112">Para obtener más información acerca de cómo configurar un controlador de envío WCF y el puerto de envío, vea los temas "Cómo..." para cada adaptador WCF en [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="0d9db-112">For more information about how to configure a WCF send handler and send port, see how-to topics for each WCF adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d9db-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0d9db-113">In This Section</span></span>  
  
-   [<span data-ttu-id="0d9db-114">Adaptadores de envío de consideraciones al consumir servicios WCF con WCF</span><span class="sxs-lookup"><span data-stu-id="0d9db-114">Considerations When Consuming WCF Services with the WCF Send Adapters</span></span>](../core/considerations-when-consuming-wcf-services-with-the-wcf-send-adapters.md)  
  
-   [<span data-ttu-id="0d9db-115">Encabezados SOAP con servicios WCF consumidos</span><span class="sxs-lookup"><span data-stu-id="0d9db-115">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)  
  
-   [<span data-ttu-id="0d9db-116">Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="0d9db-116">Configuring Dynamic Send Ports Using WCF Adapters Context Properties</span></span>](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)  
  
-   [<span data-ttu-id="0d9db-117">Cómo usar el servicio de WCF de BizTalk consumiendo Asistente para consumir un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="0d9db-117">How to Use the BizTalk WCF Service Consuming Wizard to Consume a WCF Service</span></span>](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md)  
  
-   [<span data-ttu-id="0d9db-118">Cómo controlar los contratos con tipos erróneos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="0d9db-118">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)  
  
-   [<span data-ttu-id="0d9db-119">Especificar acciones SOAP para WCF adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="0d9db-119">Specifying SOAP Actions for WCF Send Adapters</span></span>](../core/specifying-soap-actions-for-wcf-send-adapters.md)