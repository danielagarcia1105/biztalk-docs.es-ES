---
title: 'Advertencia: XPath de cuerpo de registro no encontrado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.recordBodyXPathNotFound
ms.assetid: d46e0732-08ce-4292-84d8-56dc020063e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebd6640aa469fe9383b615d70235ab488c8798f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="warning---record-body-xpath-not-found"></a>Advertencia: XPath de cuerpo de registro no encontrado
**Código de error**  
  
 BEC1008  
  
 **Explicación**  
  
 El **XPath de cuerpo** se encontró la propiedad del nodo raíz indicado en este esquema de sobre para que esté vacía o hacer referencia a un nodo no existente. Esquemas de sobres, tal y como especifica la **sobres** propiedad de la **esquema** nodo, es necesario que tengan un valor válido el **XPath de cuerpo** propiedad de la raíz especificada nodo de referencia en el esquema.  
  
 Si no se especifica ningún nodo raíz por el **referencia raíz** propiedad de la **esquema** nodo, el primer nodo raíz en el esquema, el nodo de referencia raíz de forma predeterminada, es necesario tener un valor válido en su  **XPath de cuerpo** propiedad. **XPath de cuerpo** valores de propiedad se utilizan para identificar el esquema de cada uno de los mensajes contenidos en el sobre.  
  
 **Acción del usuario**  
  
 Seleccione el nodo raíz indicado y, a continuación, seleccione el valor de la **XPath de cuerpo** propiedad que identifique correctamente el esquema del cuerpo del mensaje asociado.