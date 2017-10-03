---
title: "Obligatoriedad de la estructura en el componente de canalización de ensamblador de archivo sin formato de documentos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], document structure
ms.assetid: 3ac75706-1d4d-443a-a4bf-af8f79a6a092
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb35c7b31eda69d03d532d13d975d618d4f36f76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-flat-file-assembler-pipeline-component"></a>Obligatoriedad de estructura del documento en el componente de canalización de ensamblador de archivo sin formato
Si se hace referencia explícita a los esquemas de sobres o de documentos en el ensamblador de archivo sin formato, éste garantiza que únicamente se procesen los documentos con el tipo de mensaje correspondiente a los esquemas a los que se hace referencia.  El resto de documentos no se procesa, aunque puede implementarse un esquema para ellos.  
  
> [!NOTE]
>  El esquema de sobre se toma solo del primer mensaje. Las propiedades del sobre siempre se toman del primer mensaje.