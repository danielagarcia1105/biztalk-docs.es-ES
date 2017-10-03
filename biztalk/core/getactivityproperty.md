---
title: GetActivityProperty | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55f0d24da85088fb8f13693c8c71d32bee1bef7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityproperty"></a>GetActivityProperty
Inserta la propiedad extraída de la actividad relacionada con el evento de seguimiento en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Nombre de la propiedad.  
  
## <a name="return-value"></a>Valor devuelto  
 Cadena que contiene el valor de la propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Puede utilizar la notación con punto para la calificación del nombre de propiedad que desee recuperar. Esto le proporcionará acceso a objetos dentro de otros objetos expuestos mediante las propiedades. Por ejemplo, para obtener acceso a la propiedad de ciudad de una instancia de dirección de un pedido de compra, utilice “purchaseOrder.Address.City”.  
  
 Los nombres de propiedades distinguen primero entre mayúsculas y minúsculas; después no lo hacen. Esto es importante cuando tiene dos o más propiedades de actividad que varían sólo en las mayúsculas y minúsculas en la aplicación WF. Por ejemplo, si la aplicación de flujo de trabajo tiene las propiedades “myWorkflow” y “MyWorkflow” definidas y estuvo buscando “MyWorkflow”, coincidiría con la segunda propiedad gracias a la coincidencia que distingue entre mayúsculas y minúsculas. Si especifica “MYWORKFLOW”, coincidiría con “myWorkflow” gracias a la coincidencia que no distingue entre mayúsculas y minúsculas después de que se produzca un error en el intento de coincidencia que distingue entre mayúsculas y minúsculas.  
  
 Por ejemplo, si tiene dos propiedades de la actividad que varían sólo por mayúsculas: "myProperty" y "MyProperty".  
  
> [!NOTE]
>  Los valores de propiedad NULL crearán una excepción NullReferenceException que se devuelve a la instancia del flujo de trabajo.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo, se utiliza una expresión de actualización para que persista la propiedad de actividad “MyProperty” utilizando `GetActivityProperty`.  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```