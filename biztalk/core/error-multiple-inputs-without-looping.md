---
title: Error - varias entradas sin bucle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a8a11b25c3c1df52827bdbf4098f0cd37bdd8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240508"
---
# <a name="error---multiple-inputs-without-looping"></a>Error - varias entradas sin bucle
**Código de error**  
  
 btm1004  
  
 **Explicación**  
  
 Varios vínculos conectados al nodo indicado en el esquema de destino, lo cual solo es válido cuando uno de los nodos antecesores del nodo indicado está conectado a un **bucle** functoid.  
  
 **Acción del usuario**  
  
 Elimine todos los vínculos del nodo indicado en el esquema de destino menos uno, o bien conecte uno de los nodos primarios del nodo indicado a un functoid de Bucle.