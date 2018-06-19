---
title: GetActivityType | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a5aae3-9688-4c49-a78e-1d9c1cc85fea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67e6f31331907e20e810c11e82002fb08b89abe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246420"
---
# <a name="getactivitytype"></a>GetActivityType
Inserta el nombre del tipo de actividad actual en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el tipo de actividad actual en un formato de nombre de clase cualificado del ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 La operación `GetActivityType` recupera el tipo de actividad actual y lo coloca en la pila del formato de nombre de clase cualificado del ensamblado:  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 Al realizar la comparación, puede especificar la mayor parte del tipo necesario para satisfacer los requisitos de búsqueda específicos. Por ejemplo, se podría comparar el resultado de GetActivityType con la constante:  
  
 TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0  
  
 Es menos restrictivo que el formato de nombre de clase cualificado del ensamblado.  
  
## <a name="special-filter-behavior"></a>Comportamiento de filtro especial  
 Cuando se realiza esta operación dentro de un filtro, también se buscan coincidencias de las actividades derivadas.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene un filtro de evento que se evaluará como `true` para las instancias de `System.Workflow.ComponentModel.Activity` y para cualquier instancia de las clases que se deriven de `System.Workflow.ComponentModel.Activity`.  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```