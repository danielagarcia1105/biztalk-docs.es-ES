---
title: Ejemplo de cálculo de deshidratación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4da41d0d-10ee-4f64-97d1-3cfa9da153f7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ff231b630a5848494c45cd8d4d05f89e764eb41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268884"
---
# <a name="sample-dehydration-calculation"></a>Ejemplo de cálculo de deshidratación
A continuación, se muestra un ejemplo del cálculo, utilizando bytes privados, para determinar si BizTalk se deshidratará o no. Usa los valores configurados predeterminados y algunos ejemplos de valores de tiempo de ejecución.  
  
 Presuponga los valores siguientes para las propiedades de deshidratación:  
  
-   **TimeBlocked** = 60 (ejemplo de tiempo bloqueado en segundos)  
  
-   **WaitingHistory** = 90 (historial de ejemplo espera en segundos)  
  
-   **ActualPrivateBytes** = 250 (ejemplo del valor de bytes privados)  
  
-   **OptimalUsage** = 50 (valor de configuración predeterminado)  
  
-   **MaximalUsage** = 350 (valor de configuración predeterminado)  
  
 Puesto que la **ActualPrivateBytes** están comprendidos entre **OptimalUsage** y **MaximalUsage**, alpha se calcula como:  
  
```  
alpha(private) = (350 – 250) / 350 – 50)  
alpha(private) = 100 / 300  
alpha(private) = 0.33  
```  
  
 A continuación, calcula el **TestThreshold** como se indica a continuación:  
  
```  
TestThreshold = 1 + (0.33 * (1800 – 1))  
TestThreshold = 1 + 599.66  
TestThreshold = 600.66  
```  
  
 Por último, se toma la decisión sobre si deshidratar o no:  
  
```  
Dehydrate = (90 == -1 OR 90 > 600 OR 60 > (2 * 600))  
Dehydrate = false  
```  
  
 Mediante este ejemplo, se puede establecer que la orquestación no se deshidratará en este momento.