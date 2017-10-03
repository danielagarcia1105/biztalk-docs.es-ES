---
title: 'Error: falta el campo de propiedad | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.propFieldMissing
ms.assetid: 8d07e72b-f876-4a37-8c95-ec7aa0033983
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d77311e4c8585cfb7f6108364e6a5085619595a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---property-field-missing"></a>Error: falta el campo de propiedad
**Código de error**  
  
 BEC2008  
  
 **Explicación**  
  
 El nodo indicado en este esquema se está promocionando a un **elemento de campo** nodo en el esquema de propiedad correspondiente que no existe. Esta condición puede producirse cuando un **elemento de campo** nodo se quitó o cambió de nombre en un esquema de propiedad una vez que se haya utilizado como destino de una promoción de propiedades.  
  
 **Acción del usuario**  
  
 Modifique el esquema de propiedades para que contenga el carácter que falta **elemento de campo** nodo, o utilizar el **promocionar propiedades** cuadro de diálogo para eliminar o modificar la promoción de propiedad correspondiente.