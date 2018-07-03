---
title: Operaciones en servicios empresariales de Siebel | Microsoft Docs
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
ms.openlocfilehash: df24fa8ee0bd51ddf919e5f88a47ceae9d0743fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001373"
---
# <a name="operations-on-business-services-in-siebel"></a><span data-ttu-id="d7aa5-102">Operaciones en servicios empresariales de Siebel</span><span class="sxs-lookup"><span data-stu-id="d7aa5-102">Operations on Business Services in Siebel</span></span>
<span data-ttu-id="d7aa5-103">Un servicio de negocio de Siebel es una colección de métodos de negocio que se pueden invocar directamente en Siebel.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-103">A Siebel business service is a collection of business methods that can be directly invoked in Siebel.</span></span> <span data-ttu-id="d7aa5-104">Mientras que los objetos de negocios y componentes empresariales están asociados a los datos específicos y las tablas de Siebel, servicios de negocio invocan los objetos para llevar a cabo tareas específicas.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-104">Whereas business components and business objects are associated to specific data and tables in Siebel, business services invoke the objects to perform specific tasks.</span></span>  
  
 <span data-ttu-id="d7aa5-105">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone los métodos de servicio empresarial, como nombres de operación y admite IN, OUT e INOUT parámetros.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the business service methods as operation names and supports IN, OUT, and INOUT parameters.</span></span> <span data-ttu-id="d7aa5-106">Por ejemplo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies el **ATPRunCheck** método como una operación.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-106">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the **ATPRunCheck** method as an operation.</span></span> <span data-ttu-id="d7aa5-107">Este método pertenece a la **ATP** servicio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-107">This method belongs to the **ATP** business service.</span></span>  
  
 <span data-ttu-id="d7aa5-108">Ciertas condiciones que los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] impone al usar los servicios de negocios de Siebel:</span><span class="sxs-lookup"><span data-stu-id="d7aa5-108">Certain conditions that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] imposes while using the Siebel business services:</span></span>  
  
- <span data-ttu-id="d7aa5-109">Si un método de servicio de negocio de Siebel toma un argumento que no tiene el tipo de datos especificado, el adaptador expone el argumento como texto.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-109">If a Siebel business service method takes an argument that does not have the data type specified, the adapter exposes the argument as TEXT.</span></span>  
  
- <span data-ttu-id="d7aa5-110">Un argumento de método de servicio de negocio de Siebel puede ser de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="d7aa5-110">A Siebel business service method argument can be of the following types:</span></span>  
  
  - <span data-ttu-id="d7aa5-111">Cadena (expuesto como XSD: String)</span><span class="sxs-lookup"><span data-stu-id="d7aa5-111">String (exposed as xsd:string)</span></span>  
  
  - <span data-ttu-id="d7aa5-112">Número (expuestos como xsd: decimal)</span><span class="sxs-lookup"><span data-stu-id="d7aa5-112">Number (exposed as xsd: decimal)</span></span>  
  
  - <span data-ttu-id="d7aa5-113">Fecha (expuesto como XSD: DateTime, con la faceta de patrón que indica que parte del tiempo se debe establecer en 00:00:00)</span><span class="sxs-lookup"><span data-stu-id="d7aa5-113">Date (exposed as xsd:DateTime, with pattern facet indicating that time part must be set to 00:00:00)</span></span>  
  
  - <span data-ttu-id="d7aa5-114">Jerarquía (expuesto como XSD: String)</span><span class="sxs-lookup"><span data-stu-id="d7aa5-114">Hierarchy (exposed as xsd:string)</span></span>  
  
  - <span data-ttu-id="d7aa5-115">Objeto de integración (expuesto como XSD: String)</span><span class="sxs-lookup"><span data-stu-id="d7aa5-115">Integration Object (exposed as xsd:string)</span></span>  
  
    <span data-ttu-id="d7aa5-116">Además, el método de servicio empresarial comprueba si el valor pasado para el argumento cumple con el tipo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-116">Also, the business service method verifies whether the value passed for an argument complies with the corresponding type.</span></span> <span data-ttu-id="d7aa5-117">Por lo tanto, si un método de servicio de negocio acepta o devuelve valores que no son compatibles con el tipo del argumento correspondiente, el adaptador puede producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-117">So, if a business service method accepts or returns values that do not comply with the corresponding argument type, the adapter may throw an exception.</span></span> <span data-ttu-id="d7aa5-118">Si el adaptador funciona al invocar el método de servicio empresarial, se puede producir un error en la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="d7aa5-118">If the adapter does succeed in invoking the business service method, the schema validation may fail.</span></span>  
  
  <span data-ttu-id="d7aa5-119">Para obtener información acerca de:</span><span class="sxs-lookup"><span data-stu-id="d7aa5-119">For information about:</span></span>  
  
- <span data-ttu-id="d7aa5-120">Realizar operaciones en servicios empresariales con BizTalk Server, consulte [invocar Business Service métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="d7aa5-120">Performing operations on business services using BizTalk Server, see [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
- <span data-ttu-id="d7aa5-121">Las estructuras y las acciones SOAP para realizar operaciones en servicios empresariales, vea mensajes [esquemas de mensaje para las operaciones de servicio de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span><span class="sxs-lookup"><span data-stu-id="d7aa5-121">Message structures and SOAP actions to perform operations on business services, see [Message Schemas for Business Service Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7aa5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7aa5-122">See Also</span></span>  
 [<span data-ttu-id="d7aa5-123">Conectarse a un sistema SAP mediante el adaptador</span><span class="sxs-lookup"><span data-stu-id="d7aa5-123">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)