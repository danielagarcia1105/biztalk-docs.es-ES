---
title: Error - promoción de campos de propiedades duplicados | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.dupPropFieldPromo
ms.assetid: 59ac55c3-7613-493c-85a3-3965c250a3bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87d9f6ee346f5aae98ea69c2ce4e00c4fa1d6dbf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241348"
---
# <a name="error---duplicate-property-field-promotion"></a>Error - promoción de campos de propiedades duplicados
**Código de error**  
  
 BEC2016  
  
 **Explicación**  
  
 Varios nodos de este esquema se están promocionando como campos de propiedades al mismo **elemento de campo** nodo en el mismo esquema de propiedad.  
  
 **Acción del usuario**  
  
 Use el **campos de propiedades** pestaña de la **promocionar propiedades** cuadro de diálogo, tiene acceso a través de la **promocionar propiedades** propiedad de la **esquema**nodo, para eliminar todo excepto una de las promociones de campo de propiedad que están asociadas con el mismo **elemento de campo** nodo en el esquema de propiedades. Puede que desee agregar nuevos **elemento de campo** nodos en el esquema de propiedad para que las promociones eliminadas se puedan volver a promovido a su propia **elemento de campo** nodos.