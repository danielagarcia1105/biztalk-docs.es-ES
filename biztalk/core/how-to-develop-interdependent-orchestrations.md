---
title: Cómo desarrollar orquestaciones interdependientes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6375add6d27e6ce0d3dff89bd2b172a2b693356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992405"
---
# <a name="how-to-develop-interdependent-orchestrations"></a><span data-ttu-id="82678-102">Cómo desarrollar orquestaciones interdependientes</span><span class="sxs-lookup"><span data-stu-id="82678-102">How to Develop Interdependent Orchestrations</span></span>
<span data-ttu-id="82678-103">Puede usar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para desarrollar un conjunto de orquestaciones que tienen servicios Web interdependientes.</span><span class="sxs-lookup"><span data-stu-id="82678-103">You can use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to develop a set of orchestrations that have interdependent Web services.</span></span> <span data-ttu-id="82678-104">Esta situación se produce al tener orquestaciones que hacen referencia a tipos de datos o puertos en la orquestación desde las que se les llama.</span><span class="sxs-lookup"><span data-stu-id="82678-104">This scenario arises when you have orchestrations that reference data types and/or ports in the orchestration from which they were called.</span></span> <span data-ttu-id="82678-105">Un ejemplo de este tipo de escenario se caracteriza por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="82678-105">An example of this type of scenario is characterized by the following:</span></span>  
  
- <span data-ttu-id="82678-106">Tiene dos o más orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="82678-106">You have two or more orchestrations.</span></span>  
  
- <span data-ttu-id="82678-107">La primera orquestación (Orq1) llama a la segunda orquestación (Orq2) con una llamada de servicio Web unidireccional.</span><span class="sxs-lookup"><span data-stu-id="82678-107">The first orchestration (Orch1) calls the second orchestration (Orch2) with a one-way Web service call.</span></span>  
  
- <span data-ttu-id="82678-108">Orq2 responde a Orq1 con una llamada de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="82678-108">Orch2 responds back to Orch1 with a Web service call.</span></span>  
  
  <span data-ttu-id="82678-109">Para obtener un ejemplo de este tipo de proyecto, vea [Tutorial 2: proceso de pedido de compra](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467).</span><span class="sxs-lookup"><span data-stu-id="82678-109">For one example of this type of project, see [Tutorial 2: Purchase Order Process](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467).</span></span>  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a><span data-ttu-id="82678-110">Para desarrollar dos orquestaciones interdependientes (Orq1 y Orq2)</span><span class="sxs-lookup"><span data-stu-id="82678-110">To develop two interdependent orchestrations Orch1 and Orch2</span></span>  
  
1. <span data-ttu-id="82678-111">Uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree una versión parcial de la orq1 que tiene un puerto de recepción que se expondrá como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="82678-111">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a partial version of the Orch1 that has a receive port which will be exposed as a Web service.</span></span>  
  
2. <span data-ttu-id="82678-112">Compile Orq1.</span><span class="sxs-lookup"><span data-stu-id="82678-112">Compile Orch1.</span></span>  
  
3. <span data-ttu-id="82678-113">Ejecute el Asistente para publicar servicios Web y publique el puerto.</span><span class="sxs-lookup"><span data-stu-id="82678-113">Run the Web Services Publishing Wizard and publish the port.</span></span>  
  
4. <span data-ttu-id="82678-114">Uso de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree y complete toda la orq2, consumir servicio web de orq1.</span><span class="sxs-lookup"><span data-stu-id="82678-114">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create and complete all of Orch2, consuming Orch1's web service.</span></span>  
  
5. <span data-ttu-id="82678-115">Compile Orq2.</span><span class="sxs-lookup"><span data-stu-id="82678-115">Compile Orch2.</span></span>  
  
6. <span data-ttu-id="82678-116">Ejecute el Asistente para publicar servicios Web y publique los puertos.</span><span class="sxs-lookup"><span data-stu-id="82678-116">Run the Web Services Publishing Wizard and publish the port(s).</span></span>  
  
7. <span data-ttu-id="82678-117">Complete Orq1, que utiliza el servicio Web de Orq2, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="82678-117">Complete Orch1, consuming Orch2's web service(s) as needed.</span></span>  
  
8. <span data-ttu-id="82678-118">Vuelva a compilar Orq1.</span><span class="sxs-lookup"><span data-stu-id="82678-118">Recompile Orch1.</span></span>  
  
9. <span data-ttu-id="82678-119">Implemente Orq1 y Orq2.</span><span class="sxs-lookup"><span data-stu-id="82678-119">Deploy Orch1 and Orch2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82678-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="82678-120">See Also</span></span>  
 [<span data-ttu-id="82678-121">Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como un servicio Web</span><span class="sxs-lookup"><span data-stu-id="82678-121">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)