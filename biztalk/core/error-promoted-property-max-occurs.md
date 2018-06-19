---
title: 'Error: número máximo de coincidencias de propiedad promocionada se produce | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c8395757d19eff5241d47c31b15409a00b6faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239868"
---
# <a name="error---promoted-property-max-occurs"></a>Error: número máximo de coincidencias de propiedad promocionada se produce
**Código de error**  
  
 BEC2002  
  
 **Explicación**  
  
 La configuración de la **Max Occurs** propiedad del nodo promocionado, o de uno de sus nodos antecesores, es incompatible con la promoción de propiedades. La promoción de propiedades se deshabilita para nodos que puedan aparecer más de una vez en un mensaje de instancia. Por lo tanto, la **Max Occurs** propiedades de todos los nodos del nodo promocionado al nodo raíz deben establecerse en 1.  
  
 **Acción del usuario**  
  
 Asegúrese de que el **Max Occurs** propiedad del nodo promocionado y todos sus nodos antecesores está establecida en uno (1).