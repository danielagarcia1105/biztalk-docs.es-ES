---
title: Mediante los interceptores WF y WCF de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a87a643-8e15-47d1-8d2a-3d899a1494ff
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea631ed3a9058128a71373b6e6c7eb55ebad6c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="60ccc-102">Utilizar los interceptores WCF y WF de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-102">Using the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="60ccc-103">Los interceptores de BAM amplían la funcionalidad del interceptor de BAM para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en Windows Workflow Foundation (WF), Windows Communication Framework (WCF) y otros entornos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60ccc-103">BAM interceptors extend the BAM interceptor functionality for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] into Windows Workflow Foundation (WF), Windows Communication Framework (WCF), and other runtime environments.</span></span> <span data-ttu-id="60ccc-104">Mediante el uso de un interceptor BAM, puede llevar a cabo un seguimiento de sus procesos empresariales sin volver a compilar su solución WF o WCF: la integración se realiza a través de un archivo de configuración mediante XML y una serie de elementos que asignan eventos de aplicación a actividades de BAM y definen los datos, el Id. de correlación, el token de continuación y otros artefactos requeridos y opcionales.</span><span class="sxs-lookup"><span data-stu-id="60ccc-104">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution — integration is done through a configuration file using XML and a series of elements that map application events to BAM activities and define the data, correlation ID, continuation token and other required and optional artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60ccc-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="60ccc-105">In This Section</span></span>  
  
-   [<span data-ttu-id="60ccc-106">¿Cuáles son los interceptores WF y WCF de BAM?</span><span class="sxs-lookup"><span data-stu-id="60ccc-106">What Are the BAM WCF and WF Interceptors?</span></span>](../core/what-are-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="60ccc-107">Problemas conocidos relacionados con los interceptores WF y WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-107">Known Issues with the BAM WCF and WF Interceptors</span></span>](../core/known-issues-with-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="60ccc-108">Interceptores de BAM en un entorno de alta disponibilidad</span><span class="sxs-lookup"><span data-stu-id="60ccc-108">BAM Interceptors in a High Availability Environment</span></span>](../core/bam-interceptors-in-a-high-availability-environment.md)  
  
-   [<span data-ttu-id="60ccc-109">Contadores de rendimiento del Interceptor de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-109">BAM Interceptor Performance Counters</span></span>](../core/bam-interceptor-performance-counters.md)  
  
-   [<span data-ttu-id="60ccc-110">Cargar interceptores de BAM con la API de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-110">Loading BAM Interceptors Using the BAM API</span></span>](../core/loading-bam-interceptors-using-the-bam-api.md)  
  
-   [<span data-ttu-id="60ccc-111">Solución de problemas de interceptores de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-111">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)  
  
-   [<span data-ttu-id="60ccc-112">Consideraciones de seguridad para los interceptores de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-112">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)  
  
-   [<span data-ttu-id="60ccc-113">Archivo de configuración de interceptor</span><span class="sxs-lookup"><span data-stu-id="60ccc-113">Interceptor Configuration File</span></span>](../core/interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="60ccc-114">Interceptor de WF de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-114">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)  
  
-   [<span data-ttu-id="60ccc-115">Configurar el adaptador WCF para interceptar datos BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-115">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)  
  
-   [<span data-ttu-id="60ccc-116">Interceptor de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="60ccc-116">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)