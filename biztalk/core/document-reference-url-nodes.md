---
title: Nodos de referencia de dirección URL de documento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Document Reference URL nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- definition files [BAM], related documents
ms.assetid: 38c8ae50-ed56-451c-9549-db852d4770e5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7939a7e74483b8df192530fd9da2deafeda0681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238972"
---
# <a name="document-reference-url-nodes"></a>Nodos de URL de referencia de documento
Existen nodos de URL de referencia de documento en el archivo de definición de actividad que el programador importa desde el trabajador del conocimiento que creó el modelo de observación. Los nodos de URL de referencia de documento incluyen referencias a la ubicación que contiene un documento que está relacionado con esta actividad. Puede ser cualquier tipo de documento, por ejemplo, una actividad que representa un flujo de trabajo de aprobación de pedido, y puede que la URL de referencia de documento señale al documento de pedido subyacente.  
  
## <a name="working-with-document-reference-url-nodes"></a>Trabajar con nodos de URL de referencia de documento  
 El origen de datos para la dirección URL de referencia de documento es normalmente la **MessageRefURL** propiedad del sistema BizTalk Server. También puede utilizar esquemas personalizados que almacenen direcciones URL y que asignen la propiedad a la URL de referencia de documento desde el esquema personalizado.  
  
 Elementos a tener en cuenta de las direcciones URL de referencia de documento:  
  
-   Puede agregar una o más URL de referencia de documento, pero cada nodo debe tener un nombre único dentro de la actividad.  
  
-   El **MessageRefURL** propiedad necesario para rellenar un nodo Document Reference URL solo se rellena con un valor en el caso de los adaptadores de transporte WSS, archivo y FTP.  
  
-   Mientras que los usuarios empresariales finales pueden ver esta referencia en el portal de BAM, el propósito principal de la dirección URL de referencia es permitir que los desarrolladores de interfaz de usuario personalizada obtener acceso a información de documento asociada para que pueda presentar al usuario final.  Para obtener más información acerca de cómo ver la referencia de documento en el portal de BAM, consulte [documentos relacionados](../core/related-documents.md).  
  
## <a name="see-also"></a>Vea también  
 [Nodos de vista de actividad TPE](../core/tpe-activity-view-nodes.md)