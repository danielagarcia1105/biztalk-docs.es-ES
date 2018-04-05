---
title: 'Error: se generan varios elementos secundarios equivalentes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.couldGenMultipleEquivChildren
ms.assetid: ef3ea6db-6759-4f38-804c-e32a1f24d758
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 686899c2871ded25f6901e919e9283694b9bacf0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---could-generate-multiple-equivalent-children"></a>Error: se generan varios elementos secundarios equivalentes
**Código de error**  
  
 btm1026  
  
 **Explicación**  
  
 Vínculos al esquema de destino habilitan, indebidamente varios nodos dentro de un **equivalente** nodo de grupo que se genere.  
  
 **Acción del usuario**  
  
 Cambie los vínculos del esquema de destino, utilizan potencialmente functoids lógicos, por lo que es un único nodo dentro de la **equivalente** nodo de grupo puede generarse durante la asignación.