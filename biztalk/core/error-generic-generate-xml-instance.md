---
title: Error - generar instancia XML | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.genericGenerateXmlInstance
ms.assetid: f2b42589-fd44-45d6-86e6-c2502820beee
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c859cfc775e74ab817e66dbb8b896f51458f0301
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-generate-xml-instance"></a>Error - generar instancia XML
**Código de error**  
  
 btm1038  
  
 **Explicación**  
  
 El Asignador de BizTalk no pudo generar un archivo de mensaje de instancia XML para el esquema de origen de la asignación, lo cual sugiere que existe un problema con el esquema de origen asociado a la asignación.  
  
 **Acción del usuario**  
  
 Utilice el Editor de BizTalk para abrir el esquema de origen asociado a la asignación y empiece a investigar si existen problemas con el esquema de origen. Además, el **Validar esquema** y **generar instancia** comandos, que aparecen cuando hace clic en un esquema en el Explorador de soluciones, son útiles para encontrar errores de esquema.