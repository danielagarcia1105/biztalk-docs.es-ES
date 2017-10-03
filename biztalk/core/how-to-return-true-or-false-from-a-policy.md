---
title: "Cómo devolver True o False desde una directiva | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7bb9b2-14aa-44e7-a290-e49bf53bc594
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281d5ab7648545f2e0616095f3c535d7d109136f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-return-true-or-false-from-a-policy"></a>Cómo devolver un valor True o False desde una directiva
No es posible especificar directamente un tipo de valor devuelto para una directiva. Sin embargo, puede pasar uno de los siguientes tipos de hechos a la directiva, tiene la directiva de cambiar el valor del hecho a `true` o `false`y, a continuación, compruebe el valor de la propiedad, el elemento o la columna después de ejecutar la directiva:  
  
-   Un objeto .NET con una propiedad de tipo`Boolean`  
  
-   Un documento XML con un elemento de tipo`Boolean`  
  
-   Una tabla de base de datos con una columna de tipo`Boolean`