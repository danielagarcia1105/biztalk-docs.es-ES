---
title: 'Advertencia: campo XPath promocionado no encontrado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoFieldXPathNotFound
ms.assetid: 21b8c240-5d6f-499d-8211-6e3f2ce2a79c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f45bd1539817f010864226d07b76ca2feee8b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288532"
---
# <a name="warning---promoted-field-xpath-not-found"></a>Advertencia: campo XPath promocionado no encontrado
**Código de error**  
  
 BEC1005  
  
 **Explicación**  
  
 El nodo correspondiente a la promoción de campos de propiedades indicado es posible que no exista en el esquema. El Editor de BizTalk no se puede resolver especificaciones de XPath complejas, y si editó el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo, puede o no puede identificar correctamente el nodo que pretendía promocionar.  
  
 **Acción del usuario**  
  
 Puede evitar esta advertencia siga apareciendo cambiando el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo que se puede acceder desde las celdas de la **ruta del nodo** columna de la **Lista de campos de propiedad** de tabla en la **campos de propiedades** pestaña en el **promocionar propiedades** cuadro de diálogo. Puede tener acceso a la **promocionar propiedades** cuadro de diálogo desde el **promocionar propiedades** propiedad de la **esquema** nodo en el Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.