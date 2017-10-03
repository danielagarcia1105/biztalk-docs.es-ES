---
title: Migrar registros de archivo sin formato | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28daa8426dff3d9cbe9330430e4ba3de64410e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="migrating-flat-file-records"></a>Migrar registros de archivo sin formato
Microsoft [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] y Microsoft [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] únicamente admiten delimitadores de un solo carácter en los registros de archivo sin formato durante los procesos de análisis y serialización. Esta restricción se desplaza por la mayor flexibilidad para controlar los delimitadores. [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)]y [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] también admite la configuración delimitadores diferentes en registros, campos y subcampos. Por el contrario, Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] admite delimitadores de varios caracteres, aunque solo admite un tipo de delimitador: el delimitador secundario. Las mejoras en el tratamiento de los delimitadores pueden afectar a cómo se tratan los registros de archivos sin formato de [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] y [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
 Tres anotaciones de esquema controlan el tratamiento de delimitadores en [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] y [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)], dos para el análisis (**skip_CR**, **skip_LF**) y uno para la serialización (**append_newline** ). [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]interpreta estas anotaciones al migrar los siguientes registros:  
  
-   Si el **skip_CR** anotación tiene un valor de **true** y el delimitador actual no es un retorno de carro (0x0D), [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] agrega un retorno de carro al delimitador actual. Por ejemplo, si el delimitador actual fuese el símbolo de canalización (0x7C), el delimitador resultante sería un símbolo de canalización seguido de un retorno de carro (0x7C 0x0D). Si el delimitador actual es un retorno de carro, permanece como un solo retorno de carro, el valor de **skip_CR**.  
  
-   Si el **skip_LF** anotación tiene un valor de **true**, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] agrega un salto de línea de caracteres (0x0A) al delimitador actual. Observe que en el caso anterior donde el delimitador actual es el símbolo de canalización (0x7C), se produce un delimitador de tres caracteres (0x7C 0x0D 0x0A) si ambos **skip_CR** y **skip_LF** son **true**.  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]omite la configuración de la **append_newline** anotación.  
  
 Mientras que estas interpretaciones de las anotaciones garantizan una migración sin problemas en la mayoría de casos, hay algunos casos en los que se producen errores. Por ejemplo, si **skip_CR** y **skip_LF** son **true** y el delimitador actual es el símbolo de canalización (0x7C), [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] y [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] aceptan todos los después como delimitadores válidos en un único conjunto de registros: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A y 0x7C. Los registros que usan estos conjuntos de delimitadores no se pueden migrar y necesitan un código de analizador personalizado en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)].  
  
 Aunque [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] tiene un único tipo de delimitador, interpreta las anotaciones antiguas para que los registros se migren fácilmente. Si un [!INCLUDE[btsBizTalkServer2000](../includes/btsbiztalkserver2000-md.md)] o [!INCLUDE[btsBizTalkServer2002](../includes/btsbiztalkserver2002-md.md)] esquema tiene valores para **def_record_delimdef_field_delim**, **def_field_delim**, y estos se hace referencia en **delimiter_type** como **inherit_record**, y así sucesivamente, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] recupera el valor correspondiente y lo almacena localmente.  
  
 Además, [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] agrega campos para registros posicionales etiquetados sin elementos secundarios.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos con la generación de esquemas y validación](../core/known-issues-with-schema-generation-and-validation.md)