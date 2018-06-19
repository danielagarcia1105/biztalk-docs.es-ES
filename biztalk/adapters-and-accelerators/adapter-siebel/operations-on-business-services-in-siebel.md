---
title: Operaciones en servicios de negocios de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1ffd133d76b1f8cae3f1732e48f817fe4fb26b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221948"
---
# <a name="operations-on-business-services-in-siebel"></a><span data-ttu-id="27c0e-102">Operaciones en servicios de negocios de Siebel</span><span class="sxs-lookup"><span data-stu-id="27c0e-102">Operations on Business Services in Siebel</span></span>
<span data-ttu-id="27c0e-103">Un servicio de negocios de Siebel es una colección de métodos de negocio que se pueden invocar directamente en Siebel.</span><span class="sxs-lookup"><span data-stu-id="27c0e-103">A Siebel business service is a collection of business methods that can be directly invoked in Siebel.</span></span> <span data-ttu-id="27c0e-104">Mientras que los componentes empresariales y objetos comerciales están asociados a datos específicos y tablas de Siebel, servicios de negocio invocación los objetos para realizar tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="27c0e-104">Whereas business components and business objects are associated to specific data and tables in Siebel, business services invoke the objects to perform specific tasks.</span></span>  
  
 <span data-ttu-id="27c0e-105">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone los métodos de servicio de negocio como nombres de operación y admite IN, OUT e INOUT parámetros.</span><span class="sxs-lookup"><span data-stu-id="27c0e-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the business service methods as operation names and supports IN, OUT, and INOUT parameters.</span></span> <span data-ttu-id="27c0e-106">Por ejemplo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies la **ATPRunCheck** método como una operación.</span><span class="sxs-lookup"><span data-stu-id="27c0e-106">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the **ATPRunCheck** method as an operation.</span></span> <span data-ttu-id="27c0e-107">Este método pertenece a la **ATP** servicio para la empresa.</span><span class="sxs-lookup"><span data-stu-id="27c0e-107">This method belongs to the **ATP** business service.</span></span>  
  
 <span data-ttu-id="27c0e-108">Ciertas condiciones que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] impone al usar los servicios de negocios de Siebel:</span><span class="sxs-lookup"><span data-stu-id="27c0e-108">Certain conditions that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] imposes while using the Siebel business services:</span></span>  
  
-   <span data-ttu-id="27c0e-109">Si un método de servicio de negocios de Siebel toma un argumento que no tiene el tipo de datos especificado, el adaptador expone el argumento como texto.</span><span class="sxs-lookup"><span data-stu-id="27c0e-109">If a Siebel business service method takes an argument that does not have the data type specified, the adapter exposes the argument as TEXT.</span></span>  
  
-   <span data-ttu-id="27c0e-110">Un argumento de método de servicio de negocios de Siebel puede ser de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="27c0e-110">A Siebel business service method argument can be of the following types:</span></span>  
  
    -   <span data-ttu-id="27c0e-111">Cadena (expuesto como XSD: String)</span><span class="sxs-lookup"><span data-stu-id="27c0e-111">String (exposed as xsd:string)</span></span>  
  
    -   <span data-ttu-id="27c0e-112">Número (expuestos como xsd: decimal)</span><span class="sxs-lookup"><span data-stu-id="27c0e-112">Number (exposed as xsd: decimal)</span></span>  
  
    -   <span data-ttu-id="27c0e-113">Fecha (expuesto como XSD: DateTime, con la faceta de patrón que indica que parte de hora debe establecerse en 00:00:00)</span><span class="sxs-lookup"><span data-stu-id="27c0e-113">Date (exposed as xsd:DateTime, with pattern facet indicating that time part must be set to 00:00:00)</span></span>  
  
    -   <span data-ttu-id="27c0e-114">Jerarquía (expuesto como XSD: String)</span><span class="sxs-lookup"><span data-stu-id="27c0e-114">Hierarchy (exposed as xsd:string)</span></span>  
  
    -   <span data-ttu-id="27c0e-115">Objeto de integración (expuesto como XSD: String)</span><span class="sxs-lookup"><span data-stu-id="27c0e-115">Integration Object (exposed as xsd:string)</span></span>  
  
     <span data-ttu-id="27c0e-116">Además, el método de servicio de negocio comprueba si el valor pasado para un argumento cumple con el tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="27c0e-116">Also, the business service method verifies whether the value passed for an argument complies with the corresponding type.</span></span> <span data-ttu-id="27c0e-117">Por lo tanto, si un método de servicio de negocio acepta o devuelve valores que no son compatibles con el tipo de argumento correspondiente, el adaptador puede producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="27c0e-117">So, if a business service method accepts or returns values that do not comply with the corresponding argument type, the adapter may throw an exception.</span></span> <span data-ttu-id="27c0e-118">Si el adaptador funciona en invocar el método de servicio de negocio, se puede producir un error en la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="27c0e-118">If the adapter does succeed in invoking the business service method, the schema validation may fail.</span></span>  
  
 <span data-ttu-id="27c0e-119">Para obtener información acerca de:</span><span class="sxs-lookup"><span data-stu-id="27c0e-119">For information about:</span></span>  
  
-   <span data-ttu-id="27c0e-120">Realizar operaciones en servicios de negocio mediante BizTalk Server, consulte [invocar Business servicio métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="27c0e-120">Performing operations on business services using BizTalk Server, see [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
-   <span data-ttu-id="27c0e-121">Estructuras y las acciones de SOAP para realizar operaciones en servicios de negocio, vea mensajes [esquemas de mensaje para las operaciones de servicio de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span><span class="sxs-lookup"><span data-stu-id="27c0e-121">Message structures and SOAP actions to perform operations on business services, see [Message Schemas for Business Service Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27c0e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="27c0e-122">See Also</span></span>  
 [<span data-ttu-id="27c0e-123">Conectarse a un sistema SAP mediante el adaptador</span><span class="sxs-lookup"><span data-stu-id="27c0e-123">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)