---
title: Find (método) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5432c68c36dcf8e769351af6d57f3cd3ed712b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245972"
---
# <a name="find-method"></a>Find (método)
Se usa para devolver una lista de claves que satisfacen las claves de búsqueda parciales proporcionada. Tenga en cuenta que, para una interfaz de componente que solo tiene una instancia, es decir, que no existe clave, no se genera la función `Find()`. Vea también [Get (método)](../core/get-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Description|  
|---------------|-----------------|  
|`partialKey`|Una estructura donde las claves individuales son opcionales.|  
|`keyList`|Lista de claves que coincide con `partialKey`. Es un parámetro de salida.<br /><br /> Las claves corresponden con el conjunto de claves Buscar definido para la interfaz de componentes concreta.|  
  
## <a name="remarks"></a>Comentarios  
 Si especifica las claves parciales, se puede usar la misma búsqueda con comodín disponible desde la función interna de PeopleSoft `Find()`. Por ejemplo, la clave parcial de CUENTA "11" devuelve todas las claves de CUENTA que comienzan por "11", mientras que "%40" devuelve todas las claves de CUENTA que contienen "40" en cualquier lugar de la clave. La clave parcial "_4_4" devuelve todas las claves de CUENTA que tengan el carácter "4" en las posiciones 2 y 4.  
  
 Nota: Con la implementación actual de PeopleSoft Server, si más de 300 elementos coinciden con los criterios de búsqueda, la llamada produce un error. Esto es una restricción del servidor PeopleSoft. Se proporciona el método `Find()` del adaptador de Microsoft BizTalk para PeopleSoft Enterprise si la función `Find` de PeopleSoft está habilitada en la interfaz de componentes y las claves Obtener están disponibles.  
  
## <a name="see-also"></a>Vea también  
 [Apéndice A: métodos de interfaz de componente](../core/appendix-a-component-interface-methods.md)