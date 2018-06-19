---
title: Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, WCF services
- WCF services, orchestrations
- WCF services, errors
- orchestrations, WCF services
ms.assetid: 89f57841-d40e-4a5a-90a8-5556a2766c03
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bf64501f619e74991fafa59b2ab1c2a3e62cbca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255740"
---
# <a name="how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services"></a>Cómo iniciar excepciones erróneas desde orquestaciones publicadas como servicios WCF
Se pueden enviar dos tipos de errores de SOAP desde una orquestación: tipo y sin tipo errores de SOAP. Los errores de SOAP con tipo son aquellos en los que una operación tiene un **System.ServiceModel.FaultContractAttribute** que especifica un tipo de error SOAP personalizado. Los errores de SOAP sin tipo son aquellos que no están especificados en el contrato de una operación.  
  
 Los adaptadores de WCF no admiten el procesamiento de excepciones de contrato de error con tipo publicadas como servicios WCF. Sin embargo, los errores de SOAP sin tipo siempre pueden ser devueltos por orquestaciones o canalizaciones. Para devolver un error SOAP sin tipo, debe establecer el **System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults** en la ubicación de recepción o en el archivo de configuración, para permitir que los clientes WCF para obtener información acerca de las excepciones de operaciones de servicio interno.  
  
 El código siguiente muestra cómo establecer la propiedad en un archivo config:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Cómo controlar los contratos con tipos erróneos en orquestaciones](../core/how-to-handle-typed-fault-contracts-in-orchestrations.md)