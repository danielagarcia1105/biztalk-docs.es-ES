---
title: Esquemas SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b4bac26d99fb3282650c20381bbc18237f8908a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214924"
---
# <a name="swift-schemas"></a>Esquemas SWIFT
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]envía y recibe mensajes de (FIN) de financieros SWIFT distintos archivos planos a través de la red SWIFT. Cada mensaje individual se compone de un conjunto de bloques de encabezado, un bloque de texto que se compone de un conjunto predefinido de etiquetado campos y subcampos ordenados o posicionales y un conjunto de finalizadores dentro de un bloque de finalizador. El contenido del bloque de texto varía según el tipo de mensaje.  
  
 También hay muchas aplicaciones, que intercambian lotes de mensajes de (FIN) financieros SWIFT: un conjunto de mensajes contenidos en un único archivo. El archivo puede entregar localmente o que se transmita a través de FileAct (a través de la red IP de SWIFT: SIPN), o a través de FTP.  
  
 Para simplificar la manipulación de los datos asociados a estos mensajes, independientemente de si se procesan por lotes o envían individualmente, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] proporciona un esquema XSD que define cada tipo de mensaje. Este esquema promueve al tipo de mensaje para que los mensajes se puedan asociados automáticamente con el esquema apropiado y transforma automáticamente entre la representación de archivo sin formato externo, utilizada por la red SWIFT, a y desde XML.  
  
 El esquema incluye todos los bloques incluidos los encabezados, el texto y finalizadores. Este esquema es un esquema de intercambio, porque es lo suficientemente exhaustivos para transmitir mensajes a través de la red SWIFT mediante los protocolos de nivel de mensaje FIN y para que contenga toda la información asociada a un mensaje recibido a través de la red SWIFT.  
  
 El esquema para cada tipo de mensaje define el formato global y el contexto de ese tipo de mensaje. A4SWIFT define cada bloque. Dentro de cada bloque están dispuestos los campos y subcampos. Según corresponda, se generan los campos y subcampos a partir de tipos comunes de base o complejos, definidos en esquemas distintos. Validación de nivel de esquema que incluye el formato, juego de caracteres, valor establecido, intervalo, obligatorias y opcionales, capacidad de repetición, posición y longitud, según corresponda. Las reglas de negocios realizan validaciones de campos cruzados y otras comprobaciones lógicas.  
  
 Esta sección contiene:  
  
-   [Presentación de mensajes de ejemplo](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [Presentación del esquema de ejemplo](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [Encabezados de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [Texto SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [Finalizadores SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [Actualización de los estándares de mensaje SWIFT](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)