---
title: 'Error: no existe el archivo de entrada | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a14221857ebb567020a52c2ff0939b506d28937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241804"
---
# <a name="error---input-file-does-not-exist"></a>Error: no existe el archivo de entrada
**Código de error**  
  
 btm1037  
  
 **Explicación**  
  
 El archivo de mensaje de instancia de entrada especificado para la operación Comprobar asignación no existe y el tipo de la entrada de comprobar asignación no se establece en **generar instancia**. Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad no está establecida en **generar instancia**, debe especificar un archivo de mensaje de instancia existente para la **instancia de entrada de comprobar asignación** asignar la propiedad.  
  
 **Acción del usuario**  
  
 Según resulte necesario, establezca una u otra de las propiedades de asignación siguientes:  
  
-   **Instancia de entrada de comprobar asignación.** Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad. Mediante el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione el archivo que se ajusta al esquema de origen del mapa de mensajes de una instancia existente. Como alternativa, puede escribir la ruta de acceso de este archivo directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.  
  
-   **Entrada de comprobar asignación.** Para evitar especificar un archivo de mensaje de instancia de entrada, haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña de la **páginas de propiedades**cuadro de diálogo para la asignación, use la lista desplegable lista en el campo de valor de la **entrada de comprobar asignación** propiedad para seleccionar **generar instancia**. En este caso, no necesitan especificar un archivo para el **instancia de entrada de comprobar asignación** propiedad.