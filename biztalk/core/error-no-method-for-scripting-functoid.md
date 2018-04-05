---
title: 'Error: no hay método para el Functoid de secuencias de comandos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.noMethodForScriptingFunctiod
ms.assetid: 8e844626-2878-4ac2-9e8e-240bd32921ac
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7b053d58de52a52903eef587bff4e76610c984a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---no-method-for-scripting-functoid"></a>Error: no hay método para el Functoid de secuencias de comandos
**Código de error**  
  
 btm1009  
  
 **Explicación**  
  
 El **método de Script** propiedad del functoid **secuencias de comandos** functoid no se ha establecido aunque la **tipo de secuencia de comandos** propiedad indica que un ensamblado externo contiene la secuencia de comandos para este **secuencias de comandos** functoid.  
  
 **Acción del usuario**  
  
 Seleccione el functoid **secuencias de comandos** functoid, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **Script** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, establezca los valores correspondientes el **Configurar secuencia de comandos de Functoid** cuadro de diálogo, incluido el **método de Script** propiedad.