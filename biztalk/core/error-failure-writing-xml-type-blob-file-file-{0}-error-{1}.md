---
title: 'Error: error al escribir el archivo Blob de tipo XML (&lt;file:---{0}&gt;). Error: {1} | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb787db4-0919-4e1b-bfe1-ba0e19a08881
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d76ff1a81045d3b764a6a26112a1efd74b284674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241100"
---
# <a name="error---failure-writing-xml-type-blob-file-ltfile---0gt-error-1"></a>Error: error al escribir el archivo Blob de tipo XML (&lt;file:---{0}&gt;). Error: {1}
**Código de error**  
  
 btm1062  
  
 **Explicación**  
  
 Esto se produce cuando el compilador del asignador no puede crear el archivo blob de tipo xml en la ubicación especificada por la tarea de compilación.  
  
 **Acción del usuario**  
  
 Compruebe el mensaje de error incluido en el mensaje (Error {1})i. Si es una excepción de acceso no autorizado, es posible que no tenga permiso de escritura para la carpeta saliente del proyecto.