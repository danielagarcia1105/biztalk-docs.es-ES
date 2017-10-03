---
title: "Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, WCF services
- WCF services, orchestrations
- WCF services, errors
- orchestrations, WCF services
ms.assetid: 89f57841-d40e-4a5a-90a8-5556a2766c03
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bf64501f619e74991fafa59b2ab1c2a3e62cbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a><span data-ttu-id="e4838-102">Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF</span><span class="sxs-lookup"><span data-stu-id="e4838-102">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>
<span data-ttu-id="e4838-103">Se pueden enviar dos tipos de errores de SOAP desde una orquestación: tipo y sin tipo errores de SOAP.</span><span class="sxs-lookup"><span data-stu-id="e4838-103">Two types of SOAP faults can be sent from an orchestration: typed and untyped SOAP faults.</span></span> <span data-ttu-id="e4838-104">Los errores de SOAP con tipo son aquellos en los que una operación tiene un **System.ServiceModel.FaultContractAttribute** que especifica un tipo de error SOAP personalizado.</span><span class="sxs-lookup"><span data-stu-id="e4838-104">Typed SOAP faults are those in which an operation has a **System.ServiceModel.FaultContractAttribute** that specifies a custom SOAP fault type.</span></span> <span data-ttu-id="e4838-105">Los errores de SOAP sin tipo son aquellos que no están especificados en el contrato de una operación.</span><span class="sxs-lookup"><span data-stu-id="e4838-105">Untyped SOAP faults are those that are not specified in the contract for an operation.</span></span>  
  
 <span data-ttu-id="e4838-106">Los adaptadores de WCF no admiten el procesamiento de excepciones de contrato de error con tipo publicadas como servicios WCF.</span><span class="sxs-lookup"><span data-stu-id="e4838-106">WCF adapters do not support processing typed fault contract exceptions for orchestrations published as WCF services.</span></span> <span data-ttu-id="e4838-107">Sin embargo, los errores de SOAP sin tipo siempre pueden ser devueltos por orquestaciones o canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="e4838-107">However, untyped SOAP faults can always be returned by orchestrations or pipelines.</span></span> <span data-ttu-id="e4838-108">Para devolver un error SOAP sin tipo, debe establecer el **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults** en la ubicación de recepción o en el archivo de configuración, para permitir que los clientes WCF para obtener información acerca de las excepciones de operaciones de servicio interno.</span><span class="sxs-lookup"><span data-stu-id="e4838-108">To return an untyped SOAP fault, you need to set the **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults** on the receive location, or in the config file, to permit WCF clients to obtain information about internal service operation exceptions.</span></span>  
  
 <span data-ttu-id="e4838-109">El código siguiente muestra cómo establecer la propiedad en un archivo config:</span><span class="sxs-lookup"><span data-stu-id="e4838-109">The following code shows how to set the property in a config file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="ServiceBehaviorConfiguration">  
                    <serviceDebug includeExceptionDetailInFaults="true" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4838-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4838-110">See Also</span></span>  
 [<span data-ttu-id="e4838-111">Cómo controlar los contratos con tipos erróneos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="e4838-111">How to Handle Typed Fault Contracts in Orchestrations</span></span>](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)