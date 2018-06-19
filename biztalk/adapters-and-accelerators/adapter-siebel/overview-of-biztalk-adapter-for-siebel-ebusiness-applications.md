---
title: Información general del adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- overview, adapter
- adapter, overview of
- adapter, overview
ms.assetid: 41ab7d42-7096-45ef-9763-a5ccf88eb652
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efcc3a90f7025a5f396cd778676f5f3152bc7657
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222044"
---
# <a name="overview-of-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="d9c01-102">Información general del adaptador de BizTalk para Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="d9c01-102">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="d9c01-103">La [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone el sistema Siebel como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d9c01-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes the Siebel system as a WCF service.</span></span> <span data-ttu-id="d9c01-104">Los clientes de adaptador pueden realizar operaciones en el sistema Siebel mediante el intercambio de mensajes SOAP con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="d9c01-104">Adapter clients can perform operations on the Siebel system by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="d9c01-105">El adaptador utiliza el mensaje de WCF y realiza las llamadas adecuadas al sistema Siebel para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="d9c01-105">The adapter consumes the WCF message and makes appropriate calls to the Siebel system to perform the operation.</span></span> <span data-ttu-id="d9c01-106">El adaptador devuelve la respuesta en el sistema Siebel al cliente en forma de mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="d9c01-106">The adapter returns the response from the Siebel system back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="d9c01-107">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] metadatos de las superficies de artefactos de Siebel (componentes empresariales, servicios de negocio) que describen la estructura de SOAP del mensaje en forma de WSDL.</span><span class="sxs-lookup"><span data-stu-id="d9c01-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces metadata of Siebel artifacts (business components, business services) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="d9c01-108">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] utiliza la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes de adaptador recuperar metadatos para las operaciones y genera los artefactos de programación que se pueden usar en la solución de programación.</span><span class="sxs-lookup"><span data-stu-id="d9c01-108">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="d9c01-109">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] usa el Control de datos de Siebel COM para tener acceso al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="d9c01-109">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses the Siebel COM Data Control to access the Siebel system.</span></span> <span data-ttu-id="d9c01-110">El Control de datos de Siebel COM viene incluido con el cliente Siebel Web.</span><span class="sxs-lookup"><span data-stu-id="d9c01-110">The Siebel COM Data Control comes bundled with the Siebel Web client.</span></span> <span data-ttu-id="d9c01-111">Por lo tanto, asegúrese de que tiene instalado en el mismo equipo que el cliente de Siebel Web el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9c01-111">Hence, make sure you have the Siebel Web client installed on the same computer as the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="d9c01-112">Puede usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para comunicarse con el sistema Siebel de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9c01-112">You can use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to communicate with the Siebel system in the following ways:</span></span>  
  
-   <span data-ttu-id="d9c01-113">Al desarrollar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d9c01-113">By developing BizTalk applications.</span></span> <span data-ttu-id="d9c01-114">Vea [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).</span><span class="sxs-lookup"><span data-stu-id="d9c01-114">See [Developing BizTalk Server Applications](../../core/developing-biztalk-server-applications.md).</span></span>
  
-   <span data-ttu-id="d9c01-115">Mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d9c01-115">By using the WCF service model.</span></span> <span data-ttu-id="d9c01-116">Vea [desarrollar aplicaciones Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="d9c01-116">See [Develop Siebel Applications by Using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="d9c01-117">Mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="d9c01-117">By using the WCF channel model.</span></span> <span data-ttu-id="d9c01-118">Consulte desarrollar aplicaciones de base de datos de Oracle mediante el modelo de canal de WCF[escriba la descripción del vínculo](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span><span class="sxs-lookup"><span data-stu-id="d9c01-118">See Develop Oracle Database Applications by Using the WCF Channel Model[enter link description here](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d9c01-119">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d9c01-119">In This Section</span></span>  
  
-   <span data-ttu-id="d9c01-120">[¿Cómo se conecta el adaptador a un sistema Siebel?](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="d9c01-120">[How Does the Adapter Connect to a Siebel System?](https://msdn.microsoft.com/library/cc185212(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="d9c01-121">[¿Cómo los metadatos de Siebel expuesta del adaptador?](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="d9c01-121">[How Does the Adapter Surface Siebel Metadata?](https://msdn.microsoft.com/library/cc185267(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="d9c01-122">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="d9c01-122">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="d9c01-123">[Otras características admitidas por el adaptador](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="d9c01-123">[Other Features Supported by the Adapter](https://msdn.microsoft.com/library/cc185252(v=bts.10).aspx)</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d9c01-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9c01-124">See Also</span></span>  
 [<span data-ttu-id="d9c01-125">Comprender el adaptador de BizTalk para Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="d9c01-125">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)