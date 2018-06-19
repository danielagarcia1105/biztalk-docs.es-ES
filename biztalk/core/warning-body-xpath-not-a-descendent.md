---
title: 'Advertencia: XPath de cuerpo no es un descendiente | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.bodyXPathNotDescendant
ms.assetid: bfeff370-9b84-4fd9-81e9-1e54b166f561
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b5d228e1119bc7c569b45cc6795f3f5b8454ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288028"
---
# <a name="warning---body-xpath-not-a-descendent"></a>Advertencia: XPath de cuerpo no es un descendiente
**Código de error**  
  
 BEC1004  
  
 **Explicación**  
  
 El **XPath de cuerpo** propiedad del nodo raíz indicado en este esquema de sobre hace referencia a un nodo que no es un descendiente del nodo raíz, según sea necesario. Este error no debería producirse a menos que la **XPath de cuerpo** propiedad se modificó fuera del Editor de BizTalk.  
  
 **Acción del usuario**  
  
 Seleccione el nodo raíz indicado y el valor para el **XPath de cuerpo** propiedad que identifique correctamente el nodo de nivel superior del cuerpo del mensaje asociado.