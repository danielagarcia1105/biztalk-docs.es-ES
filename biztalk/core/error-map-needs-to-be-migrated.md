---
title: 'Error: asignación debe migrar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f49ef4aae0db47216f6117f1053185df6fae0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240556"
---
# <a name="error---map-needs-to-be-migrated"></a>Error: asignación debe migrar
**Código de error**  
  
 btm1064  
  
 **Explicación**  
  
 No se puede compilar la asignación porque se creó mediante una versión anterior del Asignador de BizTalk. Debe migrar las asignaciones de este tipo a esta versión del Asignador de BizTalk para poder compilarlas.  
  
 **Acción del usuario**  
  
 Para migrar la asignación a la versión actual del Asignador de BizTalk, cambie su extensión de archivo de "xml" a "btm", y agréguela al proyecto de Microsoft BizTalk Server correspondiente. Use la **Agregar elemento existente** comandos disponibles en la **archivo** menú en el menú contextual de BizTalk del proyecto en el Explorador de soluciones y, a continuación, abra la asignación haciendo doble clic en él en el Explorador de soluciones. Puesto que ha llegado a este tema, probablemente ya haya llevado a cabo los dos primeros pasos. Con tan solo abrir la asignación de la versión actual del Asignador de BizTalk se realizará una migración dinámica de la asignación.