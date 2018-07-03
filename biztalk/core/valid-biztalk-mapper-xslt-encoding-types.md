---
title: Tipos de codificación XSLT en el asignador de BizTalk válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- grid properties
- Code Page property
- XSLT Encoding property [grid pages]
- Schema node
- XSLT, encoding types [BizTalk Mapper]
- BizTalk Mapper, XSLT encoding
ms.assetid: 922b46cb-7bc8-4267-bf52-e5f0262b8da1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874e30f6d1cb56880dc9b15cce9c815305430871
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012341"
---
# <a name="valid-biztalk-mapper-xslt-encoding-types"></a>Tipos válidos de codificación XSLT en el Asignador de BizTalk
El Asignador de BizTalk admite tipos distintos de codificación Transformación de lenguaje de hojas de estilo extensible (XSLT). Usa el **codificación XSLT** propiedad de cuadrícula para establecer el tipo que prefiera de codificación de XSLT. En la lista siguiente se muestra los formatos de codificación que están disponibles en la lista desplegable asociada la **codificación XSLT** propiedad de cuadrícula:  
  
- None  
  
- Árabe (windows-1256)  
  
- Báltico (windows-1257)  
  
- Centroeuropeo (windows-1250)  
  
- Chino (GB18030)  
  
- Cirílico (windows-1251)  
  
- Griego (windows-1253)  
  
- Hebreo (windows-1255)  
  
- Japonés (Shift_JIS)  
  
- Coreano (ks_c_5601-1987))  
  
- Little Endian Unicode (UTF-16)  
  
- Chino simplificado (GBK)  
  
- Tailandés (windows-874)  
  
- Chino tradicional (Big5)  
  
- Turco (windows-1254)  
  
- UTF-8  
  
- Vietnamita (windows-1258)  
  
- Europeo occidental (windows-1252)  
  
  Si no encuentra la codificación que desea utilizar en la lista, puede escribir un valor de codificación diferente. Asegúrese de que el valor que proporciona es válido, porque el Asignador de BizTalk no comprueba el valor.  
  
> [!NOTE]
>  El **página de códigos** propiedad de la **esquema** nodo define el formato de codificación para los esquemas que usan en las asignaciones. Para configurar el **página de códigos** propiedad, abra el esquema en el Editor de BizTalk y especifique el valor de la **página de códigos** propiedad.  
  
## <a name="see-also"></a>Vea también  
 [Mapas](../core/maps.md)   
 [Creación de mapas con el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)