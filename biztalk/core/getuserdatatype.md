---
title: "Getuserdatatype (operación) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5525dba034571acd91d1f3dd99f2b56069f81fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="getuserdatatype"></a>GetUserDataType (operación)
Inserta el nombre del tipo de datos del usuario actual en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a>Parámetros  
 Ninguno.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el tipo de datos del usuario actual en formato completo de ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 A diferencia de **GetActivityType**, esta operación no utiliza el formato de nombre de clase cualificado del ensamblado; en su lugar, inserta el nombre de tipo:  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  Si usa el formato de nombre de clase completo de ensamblado como constante al comparar valores, siempre se evaluará como `false`.  
  
## <a name="special-filter-behavior"></a>Comportamiento de filtro especial  
 Cuando se realiza esta operación dentro de un filtro, también se buscan coincidencias de los tipos de datos del usuario.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo contiene una expresión de filtro de evento que se evaluará como `true` para las instancias de `MyLibrary.MyObject` y para cualquier instancia de las clases que se deriven de `MyLibrary.MyObject`.  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyLibrary.MyObject</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```