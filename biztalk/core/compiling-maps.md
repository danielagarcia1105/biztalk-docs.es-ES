---
title: Compilar asignaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346769519343afe9456a7b1e7cf9a3bd5bb159ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="compiling-maps"></a>Compilar asignaciones
Cuando se validan asignaciones, el componente de compilador de Asignador de BizTalk genera una hoja de estilo de Transformación de lenguaje de hojas de estilo extensible (XSLT). Esto crea una asignación compilada que transforma un mensaje de instancia definido por el esquema de origen en un mensaje de instancia definido por el esquema de destino. Compilar una asignación reclama las transformaciones y reglas estructurales especificadas en las páginas de cuadrícula.  
  
 Las transformaciones, como los vínculos, se procesan en el mismo orden en que los registros y campos aparecen en el esquema de destino. Por ejemplo, cuando el asignador de BizTalk alcanza un destino **registro** o **campo** nodo con un vínculo, el asignador de BizTalk compila las propiedades del vínculo. La acción puede ser un sencillo valor copiado desde un registro o campo del esquema de origen, o puede implicar varios cálculos mediante functoids y múltiples registros y campos.  
  
 El asignador de BizTalk genera advertencias en el **salida** ventana y **lista de tareas** ventana cuando el compilador encuentra una situación que podría producir un resultado incorrecto. Por ejemplo, si un functoid requiere un parámetro de entrada y no tiene ningún parámetro de entrada, el asignador de BizTalk genera una advertencia en el **salida** ventana. Generalmente, no debe utilizar una asignación en un entorno de producción si está generando advertencias.  
  
 También aparece un vínculo a la hoja de estilos XSLT generado en el **salida** ventana cuando la asignación se compila correctamente.  
  
 El servidor BizTalk Server utiliza la asignación compilada para llevar a cabo la traducción de un mensaje de instancia de entrada a un mensaje de instancia de salida.  
  
## <a name="see-also"></a>Vea también  
 [Probar las asignaciones](../core/testing-maps.md)   
 [Configuración de transformación de datos](../core/data-transformation-configuration.md)   
 [Coincidencia del nivel jerárquico de nodos](../core/node-hierarchy-level-matching.md)