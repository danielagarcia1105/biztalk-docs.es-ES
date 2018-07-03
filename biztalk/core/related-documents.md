---
title: Documentos relacionados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- queries [BAM], document references
- definition files [BAM], related documents
- Query Builder [BAM portal], viewing details
- document references [BAM]
- Query Builder [BAM portal], document references
- queries [BAM], viewing details
ms.assetid: 9c5f2175-fe7c-40ec-910d-1ac5c8142045
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56338d268bac6568f8e175b6e70da202715fd7a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006739"
---
# <a name="related-documents"></a>Documentos relacionados
El área de documentos relacionados de los detalles de los resultados de consulta muestra una lista de los documentos de referencia que están relacionados con la actividad. Los documentos pueden ser de cualquier tipo, incluso una imagen CAD, un archivo WAV o un pedido de compra. Por ejemplo, una actividad de pedido de compra tendrá, por lo general, un pedido de compra como tipo de documento base. La lista tendrá un vínculo al pedido de compra.  
  
## <a name="adding-document-references"></a>Agregar referencias de documento  
 La lista de documentos relacionados se genera de una de las dos maneras siguientes:  
  
- Cuando desarrolla su perfil de seguimiento, se incluye un nodo de URL de referencia de documento en el árbol de actividades y luego se asigna al documento físico desde el origen que contiene un puntero de referencia.  
  
- Su programador de integraciones rellena mediante programación la lista llamando a su aplicación personalizada.  
  
  Definir la referencia de documento mediante cualquiera de estos métodos agrega una fila en la \<activityname\>tabla _References con la ubicación del documento.  
  
  Si se ha realizado ninguna de estas tareas, el **documentos relacionados** área está en blanco.  
  
## <a name="see-also"></a>Vea también  
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)