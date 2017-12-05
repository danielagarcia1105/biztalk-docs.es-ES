---
title: 'Error: entrada de Variable de Functoid no coincidente | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.functoidVariableInputMismatch
ms.assetid: fda3066b-d0de-4f61-b78f-4726f6796e1f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edb9268adccc3af652e4ac0f1087b231da2c8277
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="error---functoid-variable-input-mismatch"></a>Error: entrada de Variable de Functoid no coincidente
**Código de error**  
  
 btm1011  
  
 **Explicación**  
  
 El functoid indicado no tiene el número correcto de parámetros de entrada especificados. El número de parámetros de entrada debe pertenecer al intervalo especificado.  
  
 **Acción del usuario**  
  
 Utilice uno o más de los siguientes métodos para proporcionar el número indicado de parámetros de entrada al functoid indicado y preste especial atención al orden de parámetros de entrada esperado:  
  
-   Para crear vínculos adicionales, arrastre para crear vínculos entre el functoid indicado y los nodos del esquema de origen o la salida de otros functoids situados a la izquierda del functoid indicado en una página de cuadrícula de asignación.  
  
-   Para crear vínculos adicionales, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, configure y reorganice el orden de los parámetros de entrada en el **configurar \<Functoid\> Functoid** cuadro de diálogo. Se pueden crear parámetros de entrada, dados los valores, y se pueden poner en el orden correcto en relación con otros parámetros de entrada de este cuadro de diálogo.  
  
-   Para eliminar vínculos existentes, para cada vínculo conectado al lado izquierdo del functoid indicado, haga clic en el vínculo y, a continuación, haga clic en **eliminar**.  
  
-   Para eliminar vínculos existentes, seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, en la **configurar \<Functoid\> Functoid**cuadro de diálogo, elimine todos los parámetros de entrada seleccionando y haciendo clic en el ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") botón para cada uno de ellos. Utilice este método para eliminar parámetros de entrada constantes.