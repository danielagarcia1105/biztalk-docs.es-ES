---
title: Functoids de cadena | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d73be02-9c93-481f-81e4-39b60bcfa2df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72e2651c38d3cc69e5c6d7c7d80c6e0d29136033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966605"
---
# <a name="string-functoids"></a>Functoids de cadena

## <a name="overview"></a>Información general
**Cadena** functoids se utilizan para manipular las cadenas de forma estándar, como conversiones a mayúsculas o minúsculas, concatenación de cadenas, determinación de la longitud de cadena, recorte, el espacio en blanco y así sucesivamente.  

 Los functoids **mayúsculas**, **minúsculas**, **tamaño**, **recorte derecho de cadena**, y **recorte izquierdo de cadena** acepta un solo parámetro de entrada. Los functoids **búsqueda de cadenas**, **cadena izquierda**, y **cadena derecha** acepta dos parámetros de entrada. El **extracción de cadenas** functoid acepta tres entradas, mientras que el **concatenación de cadenas** functoid acepta parámetros de entrada entre 1 y 100.  

 Dos **cadena** functoids hacen referencia a la posición numérica de un carácter en una cadena: **extracción de cadenas** y **búsqueda de cadenas**. Estos functoids empiezan a contar posiciones de caracteres en 1, no en 0.  

 Los dos functoids de recorte de cadena **recorte izquierdo de cadena** y **recorte derecho de cadena**, quitar todos los caracteres de espacio en blanco (espacios, tabulaciones etc.) de la izquierda o derecha (como puede ser el caso) de la cadena especificada.  

## <a name="available-functoids"></a>Functoids disponibles 
 El **cadena** functoids son: 

* Minúsculas
* Tamaño
* Concatenación de cadenas
* Extracción de cadenas
* Búsqueda de cadenas
* Cadena izquierda
* Recorte izquierdo de cadena
* Cadena derecha
* Recorte derecho de cadena
* Mayúsculas

Obtener más detalles sobre estos functoids [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

## <a name="see-also"></a>Vea también  
- [Cómo agregar Functoids básicos a una asignación](../core/how-to-add-basic-functoids-to-a-map.md)   
- **Referencia a Functoids de cadena** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
