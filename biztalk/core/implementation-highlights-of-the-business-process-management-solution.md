---
title: Solución de administración de procesos de aspectos destacados de la implementación de la empresa | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, implementing
ms.assetid: 3558db0e-d7f6-4c10-bd58-1601bd44e73f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decad6f68398cca2d0b88c4904d3e63c075749b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257420"
---
# <a name="implementation-highlights-of-the-business-process-management-solution"></a><span data-ttu-id="71c18-102">Aspectos destacados de la implementación de la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="71c18-102">Implementation Highlights of the Business Process Management Solution</span></span>
<span data-ttu-id="71c18-103">En esta sección se describen con gran detalle los elementos relacionados con la implementación de la solución.</span><span class="sxs-lookup"><span data-stu-id="71c18-103">This section describes the implementation-related elements of the solution in greater detail.</span></span> <span data-ttu-id="71c18-104">Estos elementos incluyen el marco de trabajo de reglas de negocios, el número de fases de procesamiento, el modo **OrderManager** se comunica con las fases de procesamiento, el uso de la **OrderHandler** objeto y cómo el aplicación utiliza el adaptador Ops.</span><span class="sxs-lookup"><span data-stu-id="71c18-104">These elements include the Business Rules Framework, the number of processing stages, how the **OrderManager** communicates with the processing stages, the use of the **OrderHandler** object, and how the application uses the Ops Adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="71c18-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="71c18-105">In This Section</span></span>  
  
-   [<span data-ttu-id="71c18-106">Validación con reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="71c18-106">Validation with Business Rules</span></span>](../core/validation-with-business-rules.md)  
  
-   [<span data-ttu-id="71c18-107">Número de fases de procesamiento</span><span class="sxs-lookup"><span data-stu-id="71c18-107">Number of Processing Stages</span></span>](../core/number-of-processing-stages.md)  
  
-   [<span data-ttu-id="71c18-108">Enlace de socio directo inverso</span><span class="sxs-lookup"><span data-stu-id="71c18-108">Inverse Direct Partner Binding</span></span>](../core/inverse-direct-partner-binding.md)  
  
-   [<span data-ttu-id="71c18-109">Comunicación entre OrderBroker y OrderManager</span><span class="sxs-lookup"><span data-stu-id="71c18-109">Communication between OrderBroker and OrderManager</span></span>](../core/communication-between-orderbroker-and-ordermanager.md)  
  
-   [<span data-ttu-id="71c18-110">Usar SSO de forma eficaz en la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="71c18-110">Using SSO Efficiently in the Business Process Management Solution</span></span>](../core/using-sso-efficiently-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="71c18-111">Utilizando el objeto Orderhandler para comunicarse con sistemas de back-end</span><span class="sxs-lookup"><span data-stu-id="71c18-111">Using the Order Handler Object to Communicate with Backend Systems</span></span>](../core/using-the-order-handler-object-to-communicate-with-backend-systems.md)  
  
-   [<span data-ttu-id="71c18-112">Combinar documentos XML</span><span class="sxs-lookup"><span data-stu-id="71c18-112">Merging XML Documents</span></span>](../core/merging-xml-documents.md)  
  
-   [<span data-ttu-id="71c18-113">El adaptador Ops</span><span class="sxs-lookup"><span data-stu-id="71c18-113">The Ops Adapter</span></span>](../core/the-ops-adapter.md)  
  
-   [<span data-ttu-id="71c18-114">Objeto Recaller</span><span class="sxs-lookup"><span data-stu-id="71c18-114">The Recaller Object</span></span>](../core/the-recaller-object.md)