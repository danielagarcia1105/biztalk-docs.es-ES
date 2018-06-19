---
title: 'Error: entrada de comprobar asignación no válida | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.testMapInputsNotValid
ms.assetid: d885d366-92a3-4d2a-8e2b-58e06960864f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912b70bcd74180a20d54da11dffdab79f54fc5b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242180"
---
# <a name="error---test-map-inputs-not-valid"></a>Error: entrada de comprobar asignación no válida
**Código de error**  
  
 btm1036  
  
 **Explicación**  
  
 No se ha especificado ningún archivo de mensaje de instancia de entrada para la operación Comprobar asignación y el tipo de la entrada de comprobar asignación no está establecido en **generar instancia**. Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad no está establecida en **generar instancia**, debe especificar un archivo de mensaje de instancia para la **instancia de entrada de comprobar asignación** mapa propiedad.  
  
 **Acción del usuario**  
  
 Según resulte necesario, establezca una u otra de las propiedades de asignación siguientes:  
  
-   **Instancia de entrada de comprobar asignación.** Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad. Mediante el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione una instancia de archivo que se ajuste al esquema de origen del mapa de mensajes. Como alternativa, puede escribir la ruta de acceso de este archivo directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.  
  
-   **Entrada de comprobar asignación.** Para evitar especificar un archivo de mensaje de instancia de entrada, haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades**cuadro de diálogo para la asignación, use la lista desplegable lista en el campo de valor de la **entrada de comprobar asignación** propiedad para seleccionar **generar instancia**. En este caso, no necesitan especificar un archivo para el **instancia de entrada de comprobar asignación** propiedad.