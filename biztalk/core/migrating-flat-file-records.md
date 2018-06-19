---
title: Migrar registros de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75cd5fbc-66c1-4c8b-b81a-1d028e9647b4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd43c231077f4e23efca374edbda5bf152f1415
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710823"
---
# <a name="migrate-flat-file-records"></a>Migrar registros de archivo sin formato

## <a name="overview"></a>Información general
Microsoft BizTalk Server es compatible con varios caracteres delimitadores, aunque admite solo un tipo de delimitador: delimitador secundario. 
  
 Tres anotaciones de esquema controlan el tratamiento de delimitadores en BizTalk Server: dos para el análisis (**skip_CR**, **skip_LF**) y uno para la serialización (**append_newline**). BizTalk Server interpreta estas anotaciones al migrar los siguientes registros:  
  
-   Si el **skip_CR** anotación tiene un valor de **true** y el delimitador actual no es un retorno de carro (0x0D), BizTalk Server agrega un retorno de carro al delimitador actual. Por ejemplo, si el delimitador actual fuese el símbolo de canalización (0x7C), el delimitador resultante sería un símbolo de canalización seguido de un retorno de carro (0x7C 0x0D). Si el delimitador actual es un retorno de carro, permanece como un solo retorno de carro, el valor de **skip_CR**.  
  
-   Si el **skip_LF** anotación tiene un valor de **true**, BizTalk Server agrega un salto de línea de caracteres (0x0A) al delimitador actual. Observe que en el caso anterior donde el delimitador actual es el símbolo de canalización (0x7C), se produce un delimitador de tres caracteres (0x7C 0x0D 0x0A) si ambos **skip_CR** y **skip_LF** son **true**.  
  
-   BizTalk Server pasa por alto la configuración de la **append_newline** anotación.  
  
 Mientras que estas interpretaciones de las anotaciones garantizan una migración sin problemas en la mayoría de casos, hay algunos casos en los que se producen errores. Por ejemplo, si **skip_CR** y **skip_LF** son **true** y el delimitador actual es el símbolo de canalización (0x7C), BizTalk Server acepta todas las opciones siguientes como válidos delimitadores en un único conjunto de registros: 0x7C 0x0D 0x0A, 0x7C 0x0D, 0x7C 0x0A y 0x7C. Los registros mediante estos conjuntos de delimitadores no se pueden migrar y necesitan un código de analizador personalizado en BizTalk Server.  
  
 Aunque BizTalk Server tiene un único tipo de delimitador, interpreta las anotaciones antiguas para que los registros se migren fácilmente. Si un esquema de BizTalk Server tiene valores para **def_record_delimdef_field_delim**, **def_field_delim**, y estos se hace referencia en **delimiter_type** como **inherit_record**, y así sucesivamente, BizTalk Server recupera el valor correspondiente y lo almacena localmente.  
  
 Además, BizTalk Server agrega campos para registros posicionales etiquetados sin elementos secundarios.  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos relacionados con la generación y validación de esquemas](../core/known-issues-with-schema-generation-and-validation.md)