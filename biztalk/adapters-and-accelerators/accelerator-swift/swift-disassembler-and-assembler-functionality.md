---
title: Funcionalidad de ensamblador y desensamblador de SWIFT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f9a01480c5d308ffa882b2457e26548f4b5e43b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992861"
---
# <a name="swift-disassembler-and-assembler-functionality"></a>Funcionalidad de ensamblador y desensamblador de SWIFT
El Desensamblador de SWIFT puede realizar las tareas siguientes cuando se invoca en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de recepción:  
  
- Detectar el tipo de mensaje y resolver el esquema de documento de forma dinámica. Esto permite que un único puerto de recepción y canalización para controlar varios tipos de mensaje SWIFT.  
  
- Analizar un archivo plano SWIFT en XML.  
  
- Invoque el lector para realizar la validación de XML (esquema), como la comprobación de validez del tipo de datos, el formato de datos o la conformidad de longitud de la validación de XML.  
  
- Invocar el motor de reglas de negocios (BRE) para realizar la validación del BRE, como la comprobación de conformidad con las reglas de red SWIFT o realizar otra validación compleja que no implementa el esquema.  
  
- Publicar un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado XML (con información sobre los errores detectados durante el análisis o validación).  
  
  > [!NOTE]
  >  Si el Desensamblador encuentra errores irrecuperables durante el análisis, el Desensamblador publicará el mensaje en la base de datos de cuadro de mensajes en formato de archivo sin formato nativo en lugar de XML.  
  
- Procesar lotes entrantes, como sigue:  
  
  -   Analizar y conservar los sobres por lotes (encabezado de lote, el finalizador de lote)  
  
  -   Analizar y conservar los sobres de mensajes (encabezado del mensaje, el finalizador de mensaje)  
  
  -   Analizar y validar los mensajes del lote de SWIFT individualmente  
  
  -   Publicar los mensajes de SWIFT para la base de datos de cuadro de mensajes individualmente  
  
  -   Publicar todo el lote de entrada en la base de datos de cuadro de mensajes como un solo mensaje (una copia exacta de entrada)  
  
  -   Promocionar propiedades de contexto relacionado con el lote de ordenación o poner en correlación los mensajes que se origina en el mismo lote  
  
  El ensamblador de SWIFT puede realizar las tareas siguientes cuando se invoca en una canalización de envío de BizTalk:  
  
- Detectar el tipo de mensaje y resolver el esquema de documento de forma dinámica. Esto permite a un puerto de envío único y la canalización para controlar varios SWIFT tipos de mensaje.  
  
- Serializar XML analizado en un archivo plano SWIFT.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)