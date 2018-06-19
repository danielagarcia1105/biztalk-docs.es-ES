---
title: 'Error: no existe el archivo de entrada de XML | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xmlInputFileDoesNotExist
ms.assetid: d222e615-60c8-46f5-a8de-fc59650978c7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4b70e749565bcf33f99c39faa0653c7fd952e9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245852"
---
# <a name="error---xml-input-file-does-not-exist"></a>Error: no existe el archivo de entrada de XML
**Código de error**  
  
 btm1039  
  
 **Explicación**  
  
 El archivo de mensaje de instancia de entrada XML especificado para la operación Comprobar asignación no existe. Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad se establece en XML, debe especificar un archivo de mensaje de instancia XML existente para la **instancia de entrada de comprobar asignación** asignar la propiedad.  
  
 **Acción del usuario**  
  
 Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad. Mediante el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione archivo de mensaje que se ajusta al esquema de origen del mapa de la instancia de un documento XML. Como alternativa, puede escribir la ruta de acceso de este archivo XML directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.