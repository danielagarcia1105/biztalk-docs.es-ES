---
title: GetWorkflowProperty | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 505fc41ce544cdf16e3826116514ba1991ba012e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246436"
---
# <a name="getworkflowproperty"></a>GetWorkflowProperty
Inserta la propiedad extraída de la actividad raíz del flujo de trabajo en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Nombre de la propiedad.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el valor de la propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Esta operación sólo es válida en las actualizaciones.  
  
 Puede utilizar la notación con punto para la calificación del nombre de propiedad que desee recuperar. Esto le proporcionará acceso a objetos dentro de otros objetos expuestos mediante las propiedades. Por ejemplo, para obtener acceso a la propiedad de ciudad de una instancia de dirección de un pedido de compra, utilice “purchaseOrder.Address.City”.  
  
 Los nombres de propiedades distinguen primero entre mayúsculas y minúsculas; después no lo hacen. Esto es importante cuando tiene dos o más propiedades de actividad que varían sólo en las mayúsculas y minúsculas en la aplicación WF. Por ejemplo, si la aplicación de flujo de trabajo tiene las propiedades “myWorkflow” y “MyWorkflow” definidas y estuvo buscando “MyWorkflow”, coincidiría con la segunda propiedad gracias a la coincidencia que distingue entre mayúsculas y minúsculas. Si especifica “MYWORKFLOW”, coincidiría con “myWorkflow” gracias a la coincidencia que distingue entre mayúsculas y minúsculas después de que se produzca un error en el intento de coincidencia que no distingue entre mayúsculas y minúsculas.  
  
> [!NOTE]
>  Los valores de propiedad NULL crearán una excepción NullReferenceException que se devuelve a la instancia del flujo de trabajo.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo, se utiliza una expresión de actualización para que persista la propiedad de flujo de trabajo de ciudad a partir de un pedido de compra utilizando `GetWorkflowProperty`.  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```