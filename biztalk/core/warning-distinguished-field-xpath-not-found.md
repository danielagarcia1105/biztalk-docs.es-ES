---
title: "Advertencia: no se encontró el XPath de campo distintivo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.distingFieldXPathNotFound
ms.assetid: a925c39c-9ae1-4334-b329-aa2f5afd97ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9df2e34c27fe3e5e3540ac384443f86143bf741
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---distinguished-field-xpath-not-found"></a>Advertencia: XPath de campo distintivo no encontrado
**Código de error**  
  
 BEC1006  
  
 **Explicación**  
  
 El nodo correspondiente a la promoción del campo distintivo indicado es posible que no exista en el esquema. El Editor de BizTalk no se puede resolver especificaciones de XPath complejas, y si editó el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo, puede o no puede identificar correctamente el nodo que pretendía promocionar.  
  
 **Acción del usuario**  
  
 Puede evitar esta advertencia siga apareciendo cambiando el XPath de la propiedad promocionada en el **Editar XPath de instancia** cuadro de diálogo que se puede acceder desde las celdas de la **ruta del nodo** columna de la tabla en el **Campos distintivos** pestaña en el **promocionar propiedades** cuadro de diálogo. Puede tener acceso a la **promocionar propiedades** cuadro de diálogo desde el **promocionar propiedades** propiedad de la **esquema** nodo en el Microsoft® [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.