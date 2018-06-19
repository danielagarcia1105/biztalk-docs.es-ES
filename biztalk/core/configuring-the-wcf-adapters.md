---
title: Configurar los adaptadores de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NetTcpBinding [WCF adapters]
- configuring [WCF adapters]
- WCF adapters, pre-defined bindings
- configuring [WCF adapters], about configuring WCF adapters
- WsHttpBinding [WCF adapters]
- BasicHttpBinding [WCF adapters]
- NetNamedPipeBinding [WCF adapters]
- NetMsmqBinding [WCF adapters]
- bindings, pre-defined [WCF adapters]
- WCF adapters, configuring
ms.assetid: af01e2d4-303d-407a-b853-dd90b0246a8a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dde69bb5b2014a20509778e27230840e47c0b36d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233164"
---
# <a name="configuring-the-wcf-adapters"></a><span data-ttu-id="74d16-102">Configurar adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-102">Configuring the WCF Adapters</span></span>
<span data-ttu-id="74d16-103">Los adaptadores de BizTalk para Windows Communication Foundation (WFC) permiten que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se comunique con aplicaciones basadas en WCF.</span><span class="sxs-lookup"><span data-stu-id="74d16-103">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="74d16-104">Los adaptadores de WCF de BizTalk incluyen cinco adaptadores físicos que representan los enlaces predefinidos de WCF:**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**,  **NetNamedPipeBinding**, y **NetMsmqBinding**.</span><span class="sxs-lookup"><span data-stu-id="74d16-104">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="74d16-105">Se proporcionan adaptadores de WCF para los enlaces predefinidos para permitir configurar de forma sencilla la información necesaria para la mayoría de los requisitos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="74d16-105">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="74d16-106">Asimismo, los adaptadores de WCF de BizTalk incorporan dos adaptadores que permiten configurar libremente la información de comportamiento y el enlace de WCF para la ubicación de recepción y el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="74d16-106">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  
  
 <span data-ttu-id="74d16-107">Todos los adaptadores de WCF proporcionan cuadros de diálogo de propiedades de transporte similares para los puertos de envío y las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="74d16-107">All the WCF adapters provide similar transport properties dialog boxes for send ports and receive locations.</span></span> <span data-ttu-id="74d16-108">Sin embargo, las tareas detalladas para configurar los adaptadores de WFC varían en función del adaptador físico.</span><span class="sxs-lookup"><span data-stu-id="74d16-108">However, the detailed tasks to configure the WCF adapters vary depending on the physical adapter.</span></span> <span data-ttu-id="74d16-109">Las tareas que no están directamente relacionadas con los enlaces del adaptador, como la instalación de certificados, son las mismas para todos los adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="74d16-109">Tasks not directly related to the adapter bindings, such as installing certificates, are the same for all the WCF adapters.</span></span> <span data-ttu-id="74d16-110">Esta sección trata las tareas comunes a todos los adaptadores de WFC.</span><span class="sxs-lookup"><span data-stu-id="74d16-110">This section discusses the tasks that are common to all the WCF adapters.</span></span> <span data-ttu-id="74d16-111">Para obtener información acerca de las tareas que difieren para cada adaptador, vea los temas correspondientes para el adaptador en [adaptadores de WCF](../core/wcf-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="74d16-111">For information about tasks that differ for each adapter, see the appropriate topics for the adapter in [WCF Adapters](../core/wcf-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74d16-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="74d16-112">In This Section</span></span>  
  
-   [<span data-ttu-id="74d16-113">Propiedades y esquema de propiedades de adaptadores WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-113">WCF Adapters Property Schema and Properties</span></span>](../core/wcf-adapters-property-schema-and-properties.md)  
  
-   [<span data-ttu-id="74d16-114">Recomendaciones de seguridad de los adaptadores WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-114">WCF Adapters Security Recommendations</span></span>](../core/wcf-adapters-security-recommendations.md)  
  
-   [<span data-ttu-id="74d16-115">Instalación de certificados para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-115">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="74d16-116">Especificar el cuerpo del mensaje para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-116">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="74d16-117">Cómo habilitar los puntos de extensibilidad de WCF con los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-117">How to Enable the WCF Extensibility Points with the WCF Adapters</span></span>](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="74d16-118">Contadores de rendimiento de los adaptadores WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-118">WCF Adapters Performance Counters</span></span>](../core/wcf-adapters-performance-counters.md)  
  
-   [<span data-ttu-id="74d16-119">Compatibilidad de inicio de sesión único para los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-119">Single Sign-On Support for the WCF Adapters</span></span>](../core/single-sign-on-support-for-the-wcf-adapters.md)  
  
## <a name="see-also"></a><span data-ttu-id="74d16-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="74d16-120">See Also</span></span>  
 [<span data-ttu-id="74d16-121">Adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="74d16-121">WCF Adapters</span></span>](../core/wcf-adapters.md)