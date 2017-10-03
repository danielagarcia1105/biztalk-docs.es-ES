---
title: Constante | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674307acea439bc260399cc01da4165eedaa2da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="constant"></a>Constante
Inserta un valor único y constante en la pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a>Parámetros  
 Valor constante.  
  
## <a name="pushed-value"></a>Valor insertado  
 Cadena que contiene el valor constante.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="example"></a>Ejemplo  
 La siguiente expresión de filtro de ejemplo utiliza la **constante** operación para insertar un valor que se usará en un **es igual a** operación para asegurarse de que el nombre de la actividad actual sea "FoodAndDrinksPolicy".  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 Se trata de un patrón de uso común para la **constante** operación.  
  
## <a name="see-also"></a>Vea también  
 [Operaciones de interceptor](../core/interceptor-operations.md)