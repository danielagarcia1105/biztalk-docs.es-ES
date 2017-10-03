---
title: Elemento EventSource del interceptor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d78846c1-3984-43af-a13f-9d5c0a66d3b5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35b5cd6b2e872f689988f3d10d18df002f66d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-eventsource-element"></a>Elemento EventSource del interceptor
El **EventSource** elemento proporciona información sobre el origen de uno o varios de los eventos que aparecen en el archivo de configuración de interceptor. Además del nombre de origen de eventos, debe indicar la tecnología y el manifiesto del origen.  
  
## <a name="format"></a>Formato  
 El elemento `EventSource` cuenta con tres atributos y puede disponer de elementos secundarios, en función de los esquemas que se incluyan. Por ejemplo, el esquema WCF WcfInterceptorConfiguration.xsd proporciona el elemento `NamespaceMapping`.  
  
### <a name="attributes"></a>Atributos  
  
|Nombre del atributo|Description|  
|--------------------|-----------------|  
|Nombre|Nombre del origen de eventos. Este nombre se usa por **OnEvent** entradas para hacer referencia al origen.|  
|Tecnología|El tipo de tecnología que aloja el origen de eventos indicado en el manifiesto. Utilice "WF" para Windows Workflow Foundation y "WCF" para Windows Communication Framework.|  
|Manifiesto|Nombre de clase cualificado por el ensamblado del tipo que se va a usar como origen de eventos. Por ejemplo, `TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08`<br /><br /> Si no cuenta con un token de clave pública, utilice `PublicKeyToken=null`.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo contiene dos **EventSource** elementos, un WF de destino y un WCF de destino.  
  
```  
<!-- WF -->  
<ic:EventSource Name="OrderWorkflow" Technology="WF" Manifest="SimpleWorkflow.OrderWorkflow, SimpleWorkflow, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
<!-- WCF -->  
<ic:EventSource Name="PurchaseService" Technology="WCF" Manifest="Service.IProcessPOContract, DuplexService, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
```