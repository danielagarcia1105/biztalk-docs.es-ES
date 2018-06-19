---
title: 'Error: archivo de entrada nativo no existe | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333849007c808a20130f10dfb1f22a756024a4c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241892"
---
# <a name="error---native-input-file-does-not-exist"></a>Error: archivo de entrada nativo no existe
**Código de error**  
  
 btm1040  
  
 **Explicación**  
  
 El archivo de mensaje de instancia de entrada nativo especificado para la operación Comprobar asignación no existe. Cuando el valor de la **entrada de comprobar asignación** asignar la propiedad se establece en **nativo**, debe especificar un archivo de mensaje de instancia nativo existente para la **instancia de entrada de comprobar asignación** mapa propiedad.  
  
 **Acción del usuario**  
  
 Haga clic en la asignación correspondiente en el Explorador de soluciones, haga clic en **propiedades**y, a continuación, en la **comprobar asignación** pestaña en el **páginas de propiedades** cuadro de diálogo para la asignación, haga clic en los puntos suspensivos () **...** ) botón en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad. En el **Seleccionar archivo de entrada** cuadro de diálogo, seleccione archivo de mensaje que se ajusta al esquema de origen del mapa de la instancia de un nativo existente. Como alternativa, puede escribir la ruta de acceso del archivo nativo directamente en el campo de valor de la **instancia de entrada de comprobar asignación** propiedad.