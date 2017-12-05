---
title: "Cómo recorrer en iteración ArrayList en reglas de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9010907cfe9fb6d79a8d9fcead533376b014640e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a>Cómo recorrer en iteración ArrayList en reglas de negocios
Esta sección proporciona un ejemplo de cómo recorrer en iteración los miembros de un **ArrayList** en reglas de negocios.  
  
 Suponga que tiene un **ArrayList** con una colección de **MyClass** objetos. Las reglas de negocio tendrían el siguiente aspecto.  
  
## <a name="rule-a"></a>Regla A  
 IF 1==1  
  
 THEN Assert (ArrayList.GetEnumerator)  
  
 Un **IEnumerator** tipo se impone en la memoria de trabajo, porque la condición de regla (1 == 1) siempre se evalúa como true.  
  
## <a name="rule-b"></a>Regla B  
 IF IEnumerator.MoveNext  
  
 THEN    Assert (IEnumerator.get_Current)  
  
 Update (IEnumerator)  
  
 Como la regla recorre en iteración la **ArrayList**, cada **MyClass** objeto en la colección se agrega a la memoria de trabajo.  
  
## <a name="rule-c"></a>Regla C  
 IF MyClass.MyProperty==2  
  
 A continuación, \<hacer algo...\>  
  
 Esta regla ejecuta una acción (o acciones) cuando el valor de propiedad del objeto coincide con la condición.