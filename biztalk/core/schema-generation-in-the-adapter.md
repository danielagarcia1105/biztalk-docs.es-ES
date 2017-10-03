---
title: "Generación de esquema en el adaptador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, generating
- writing, schemas
ms.assetid: 43b69383-bae0-401b-9620-d4302db799b2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10d927e4ede59e716b3f9838c96bac8cd144a81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schema-generation-in-the-adapter"></a>Generación de esquemas del adaptador
Un sistema TIBCO Rendezvous no incluye un repositorio de tipos de mensajes. Todos los análisis y construcciones de mensajes se incluyen en el tipo de aplicación Rendezvous. Debido a esta limitación, el adaptador de Microsoft BizTalk para TIBCO Rendezvous no puede proporcionar capacidades de generación de esquemas.  
  
## <a name="writing-schemas"></a>Esquemas de escritura  
 Debe escribir un esquema y usar **Agregar elemento existente** en Visual Studio para importarlo para su uso en orquestaciones. Los esquemas son muy importantes para las herramientas de desarrollo de BizTalk Server y para la integración en Visual Studio. Los programadores de BizTalk Server tienen la opción de proporcionar un esquema completo, minimalista o una versión intermedia.  
  
## <a name="see-also"></a>Vea también  
 [Introducción](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)