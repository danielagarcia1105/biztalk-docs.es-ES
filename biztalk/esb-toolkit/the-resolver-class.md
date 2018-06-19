---
title: La clase de resolución | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9ebd6c2-fd86-471a-bc50-b1b89f701fab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1359bcbb9c6c918fc0ee6d5e67bacb8e3559c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294852"
---
# <a name="the-resolver-class"></a>La clase de resolución
El **resolución** clase es una estructura simple que expone un par nombre/valor. El servicio Web de resolución, devuelve una colección genérica de instancias de esta clase de sus métodos.  
  
 El instalador de ESB Core instala y registra el **Microsoft.Practices.ESB.Resolver.dll** ensamblado con la clase de resolución de la caché global de ensamblados.  
  
 El uso de un nombre/valor basada en diccionario aproximarse hace más fácil agregar nuevos elementos en el futuro libera y reduce el tamaño del resultado de la resolución al evitar la inclusión de propiedades no pertinentes que varían en función del método de resolución y el tipo de resolución actual.  
  
 El **resolución** clase expone dos propiedades:  
  
-   **Nombre**. Este es el nombre de un par de nombre/valor que contiene información que se devuelve después de que se resuelve una cadena de conexión.  
  
-   **Valor**. Este es el valor que corresponde al nombre del par nombre/valor.