---
title: Mediante el análisis y serialización motores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e820b2dce1257ec948aa214c9fdf1d43a6a7152
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287684"
---
# <a name="using-the-parsing-and-serializing-engines"></a>Utilizar los motores de análisis y serialización
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un análisis y motor para simplificar el proceso de análisis y serialización de documentos de archivos sin formato de serialización.  
  
 El motor de análisis es un marco de trabajo controlado por esquemas que puede analizar muy diferentes formatos de documentos en XML. Además, el motor dispone de un modelo de extensibilidad bien definido para facilitar aún más el análisis de los formatos personalizados.  
  
 Para análisis complejos se usan desensambladores. Además de convertir el formato nativo en XML, el desensamblador también puede separar un solo documento en múltiples documentos.  
  
 El motor de serialización es similar al de análisis, pero trabaja en sentido opuesto. Mientras que el motor de análisis convierte formatos nativos en XML, el motor de serialización convierte XML en formatos nativos. Y del mismo modo que el motor de análisis usa desensambladores, el motor de serialización usa ensambladores.  
  
 En esta sección se explica cómo llevar a cabo el análisis, la serialización y la codificación de caracteres según esquemas en lenguaje de definición de esquemas XML (XSD) y a efectuar otras tareas comunes mediante las API del motor de análisis y del motor de serialización.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Implementación de codificación de caracteres en un componente de canalización](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [Uso de esquemas](../core/using-schemas.md)  
  
-   [Usar el motor de análisis de archivo sin formato](../core/using-the-flat-file-parsing-engine.md)  
  
-   [Usar el motor de serialización de archivo sin formato](../core/using-the-flat-file-serializing-engine.md)