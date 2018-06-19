---
title: Usar espacios de nombres con el Proxy de WSDL en el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 781d20fa-83e3-42fa-866e-5650d5eb71a7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc21b37ae80299bf5ddd78d1ca48331e1e369e78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965050"
---
# <a name="use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="e87b2-102">Usar espacios de nombres con el Proxy de WSDL en el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e87b2-102">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="e87b2-103">El [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] genera WSDL y servidores proxy para un adaptador con los valores suministrados por el programador mediante el [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] o se ha especificado en el código mediante la modificación de la variable privada SERVICENAMESPACE o `Namespace` propiedad del adaptador.</span><span class="sxs-lookup"><span data-stu-id="e87b2-103">The [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] generates WSDL and proxies for an adapter using values supplied by the developer using the [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)] or specified in code through modification of the SERVICENAMESPACE private variable and/or the `Namespace` property of the adapter.</span></span>  
  
 <span data-ttu-id="e87b2-104">Los tipos de esquema y los elementos definidos dentro de la \<WSDL: Types\>\<esquema\> use {OperationNamespace} de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e87b2-104">The schema types and elements defined within the \<wsdl:types\>\<schema\> use the {OperationNamespace} by default.</span></span> <span data-ttu-id="e87b2-105">Si un tipo determinado tiene un TypeNamespace invalidado establecido el **TypeMetadata** objeto, ese espacio de nombres se utiliza para el tipo complejo u o definición de elemento.</span><span class="sxs-lookup"><span data-stu-id="e87b2-105">If a particular type has an overridden TypeNamespace set in the **TypeMetadata** object, that namespace is used for the complex type and/or or element definition.</span></span>  
  
## <a name="impact-on-wsdl"></a><span data-ttu-id="e87b2-106">Impacto en WSDL</span><span class="sxs-lookup"><span data-stu-id="e87b2-106">Impact on WSDL</span></span>  
 <span data-ttu-id="e87b2-107">En la tabla siguiente se muestra cómo afectan los espacios de nombres diferentes en un adaptador personalizado a WSDL correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e87b2-107">The following table shows how the different namespaces in a custom adapter affect the corresponding WSDL.</span></span> <span data-ttu-id="e87b2-108">En la tabla, ~ {OperationNamespace} es la asignación de espacio de nombres de clase de un identificador URI; Por ejemplo, si es de {OperationNamespace} "myscheme://a.b/c", ~ {OperationNamespace} será myscheme.a.b.c.</span><span class="sxs-lookup"><span data-stu-id="e87b2-108">In the table, ~{OperationNamespace} is the class namespace mapping of a URI; for example, if {OperationNamespace} is "myscheme://a.b/c", ~{OperationNamespace} will be myscheme.a.b.c.</span></span>  
  
|<span data-ttu-id="e87b2-109">Construcción WSDL</span><span class="sxs-lookup"><span data-stu-id="e87b2-109">WSDL Construct</span></span>|<span data-ttu-id="e87b2-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e87b2-110">Syntax</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="e87b2-111">TargetNamespace WSDL,</span><span class="sxs-lookup"><span data-stu-id="e87b2-111">WSDL targetNamespace,</span></span><br /><br /> <span data-ttu-id="e87b2-112">Xmlns:TS</span><span class="sxs-lookup"><span data-stu-id="e87b2-112">Xmlns:ts</span></span>|<span data-ttu-id="e87b2-113">{Custom} Adapter.Namespace</span><span class="sxs-lookup"><span data-stu-id="e87b2-113">{Custom}Adapter.Namespace</span></span>|  
|<span data-ttu-id="e87b2-114">\<WSDL: portType\></span><span class="sxs-lookup"><span data-stu-id="e87b2-114">\<wsdl:portType\></span></span>|<span data-ttu-id="e87b2-115">{esquema de}. ~ {OperationNamespace}</span><span class="sxs-lookup"><span data-stu-id="e87b2-115">{scheme}.~{OperationNamespace}</span></span>|  
|<span data-ttu-id="e87b2-116">Nombre del mensaje de entrada de WSDL</span><span class="sxs-lookup"><span data-stu-id="e87b2-116">WSDL Input Message Name</span></span>|<span data-ttu-id="e87b2-117">{esquema de}. ~ {OperationNamespace} _ {OperationName} _InputMessage</span><span class="sxs-lookup"><span data-stu-id="e87b2-117">{scheme}.~{OperationNamespace}_{OperationName}_InputMessage</span></span>|  
|<span data-ttu-id="e87b2-118">Nombre del mensaje de salida WSDL</span><span class="sxs-lookup"><span data-stu-id="e87b2-118">WSDL Output Message Name</span></span>|<span data-ttu-id="e87b2-119">{esquema de}. ~ {OperationNamespace} _ {OperationName} _OutputMessage</span><span class="sxs-lookup"><span data-stu-id="e87b2-119">{scheme}.~{OperationNamespace}_{OperationName}_OutputMessage</span></span>|  
|<span data-ttu-id="e87b2-120">\<WSDL: Types\>\<esquema\> targetNamespace</span><span class="sxs-lookup"><span data-stu-id="e87b2-120">\<wsdl:types\>\<schema\> targetNamespace</span></span>|<span data-ttu-id="e87b2-121">{esquema} :// {OperationNamespace}</span><span class="sxs-lookup"><span data-stu-id="e87b2-121">{scheme}://{OperationNamespace}</span></span>|  
|<span data-ttu-id="e87b2-122">\<elemento\>\<complexType\></span><span class="sxs-lookup"><span data-stu-id="e87b2-122">\<element\>\<complexType\></span></span>|<span data-ttu-id="e87b2-123">Use {TypeNamespace} si su valor no es null o está vacío.</span><span class="sxs-lookup"><span data-stu-id="e87b2-123">Use {TypeNamespace} if its value is not null or empty.</span></span>|  
  
## <a name="impact-on-proxy"></a><span data-ttu-id="e87b2-124">Impacto en el servidor Proxy</span><span class="sxs-lookup"><span data-stu-id="e87b2-124">Impact on Proxy</span></span>  
 <span data-ttu-id="e87b2-125">Tres atributos diferentes en el proxy se ven afectados por los espacios de nombres:</span><span class="sxs-lookup"><span data-stu-id="e87b2-125">Three different attributes in the proxy are affected by namespaces:</span></span>  
  
-   <span data-ttu-id="e87b2-126">[**System.ServiceModel.ServiceContractAttribute**(nombre = "{esquema}. ~ {OperationNamespace}", Namespace="{Custom}Adapter.Namespace"]</span><span class="sxs-lookup"><span data-stu-id="e87b2-126">[**System.ServiceModel.ServiceContractAttribute**(Name="{scheme}.~{OperationNamespace}", Namespace="{Custom}Adapter.Namespace”]</span></span>  
  
-   <span data-ttu-id="e87b2-127">[**System.ServiceModel.MessageContractAttribute**(WrapperName = "DivideResponse", WrapperNamespace = "{esquema} :// {OperationNamespace}", IsWrapped = true)]</span><span class="sxs-lookup"><span data-stu-id="e87b2-127">[**System.ServiceModel.MessageContractAttribute**(WrapperName="DivideResponse", WrapperNamespace="{scheme}://{OperationNamespace}", IsWrapped=true)]</span></span>  
  
-   <span data-ttu-id="e87b2-128">[**System.ServiceModel.MessageBodyMemberAttribute**(Namespace = "{esquema} :// {TypeNamespace}", orden = 0)]</span><span class="sxs-lookup"><span data-stu-id="e87b2-128">[**System.ServiceModel.MessageBodyMemberAttribute**(Namespace="{scheme}://{TypeNamespace}", Order=0)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e87b2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e87b2-129">See Also</span></span>  
 [<span data-ttu-id="e87b2-130">Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e87b2-130">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)