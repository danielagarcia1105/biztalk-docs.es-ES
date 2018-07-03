---
title: Esquemas de SWIFT | Microsoft Docs
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
ms.openlocfilehash: f749a06c694007008f3d8138b2b087b77b2c4f03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996117"
---
# <a name="swift-schemas"></a>Esquemas de SWIFT
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] envía y recibe mensajes de (FIN) de financieros SWIFT como archivos sin formato individuales a través de la red SWIFT. Cada mensaje individual se compone de un conjunto de bloques de encabezado, un bloque de texto que se compone de un conjunto predefinido de etiquetado campos y subcampos posicionales u ordenados y un conjunto de finalizadores dentro de un bloque de finalizador. El contenido del bloque de texto varía según el tipo de mensaje.  
  
 También hay muchas aplicaciones, que se intercambian los lotes de mensajes de (FIN) financieros SWIFT: un conjunto de mensajes contenidos en un único archivo. El archivo, es posible que se entrega localmente o se transmita a través de FileAct (a través de la red IP SWIFT: SIPN), o a través de FTP.  
  
 Para simplificar la manipulación de los datos asociados con estos mensajes, independientemente de si están por lotes o individualmente, envía Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] proporciona un esquema XSD que define cada tipo de mensaje. Este esquema promueve al tipo de mensaje para que los mensajes puedan asocia automáticamente con el esquema apropiado y se transforma automáticamente entre la representación de archivo sin formato externo, utilizada por la red SWIFT, a y desde XML.  
  
 El esquema incluye todos los bloques que se incluyen los encabezados de texto y finalizadores. Este esquema es un intercambio, porque es lo suficientemente completa para transmitir mensajes a través de la red SWIFT mediante los protocolos de nivel de mensaje FIN y para que contenga toda la información asociada con un mensaje recibido a través de la red SWIFT.  
  
 El esquema para cada tipo de mensaje define el formato general y el contexto de ese tipo de mensaje. A4SWIFT define cada bloque. Dentro de cada bloque, se distribuyen los campos y subcampos. Según corresponda, se crean los campos y subcampos a partir de tipos comunes de bases o complejos, definidos en esquemas distintos. Validación de nivel de esquema que incluye el formato, juego de caracteres, valor establecido, intervalo, obligatorias y opcionales, la repetibilidad, posición y longitud, según corresponda. Las reglas de negocios realizan validaciones de campos cruzados y otras comprobaciones lógicas.  
  
 Esta sección contiene:  
  
-   [Presentación de mensajes de ejemplo](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [Presentación de esquemas de ejemplo](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [Encabezados de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [Texto de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [Finalizadores SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [Actualización de los estándares de mensaje SWIFT](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)