---
title: 'Error: segunda entrada de Functoid acumulativo no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.secondInputToCumulativeNotValid
ms.assetid: e41a58a7-e0a2-4284-bd19-279578a8915d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0228beda57b961d515471e42760abe3ab92db54
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968522"
---
# <a name="error---second-input-to-cumulative-functoid-not-valid"></a>Error: segunda entrada de Functoid acumulativo no válida
**Código de error**  
  
 btm1031  
  
 **Explicación**  
  
 El functoid **acumulativa** el functoid tiene un segundo parámetro de entrada que no es válido. El segundo parámetro de entrada de los functoids acumulativos debe ser un número entero positivo que indique el intervalo dentro del esquema de origen en el que tendrá lugar la acumulación.  
  
 **Acción del usuario**  
  
 Seleccione el functoid **acumulativa** functoid, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **entradas de Functoid de orden** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, en la **configurar \<Functoid\> Functoid** diálogo cuadro, asegúrese de que el segundo parámetro de entrada, si existe, es un entero positivo.