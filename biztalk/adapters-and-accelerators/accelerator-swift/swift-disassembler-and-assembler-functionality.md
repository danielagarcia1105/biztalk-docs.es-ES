---
title: Desensamblador SWIFT y la funcionalidad de ensamblador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, about disassembler
- assembler, about assembler
- assembler, functionality
- disassembler, functionality
ms.assetid: d4fc092e-586d-4360-921d-151af66b8bc1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0109979fbb9bf61fc0e1be833061b2a15b470690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="swift-disassembler-and-assembler-functionality"></a>Desensamblador SWIFT y la funcionalidad de ensamblador
El Desensamblador SWIFT puede realizar las siguientes tareas cuando se invoca en una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] la canalización de recepción:  
  
-   Dinámicamente el tipo de mensaje de detectar y resolver el esquema de documento. Esto permite que un único puerto de recepción y canalización para controlar varios tipos de mensaje SWIFT.  
  
-   Analizar un archivo plano SWIFT en XML.  
  
-   Invoque el lector para realizar la validación de XML (esquema), como la comprobación de validez del tipo de datos, el formato de datos o la conformidad de longitud de la validación de XML.  
  
-   Invocar el motor de reglas de negocios (BRE) para realizar la validación del BRE, como la comprobación de conformidad con las reglas de red SWIFT o realizar otra validación compleja que no implementa el esquema.  
  
-   Publicar un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y colección de errores serializado de XML (con información sobre los errores detectados durante el análisis o validación).  
  
    > [!NOTE]
    >  Si el Desensamblador encuentra errores irrecuperables durante el análisis, el Desensamblador publicará el mensaje en la base de datos de cuadro de mensajes en formato de archivo sin formato nativo en lugar de XML.  
  
-   Procesar lotes entrantes, como se indica a continuación:  
  
    -   Analizar y conservar los sobres de lote (encabezado de lote, el finalizador de lote)  
  
    -   Analizar y conservar los sobres de mensajes (encabezado del mensaje, el finalizador de mensaje)  
  
    -   Analizar y validar los mensajes en el lote de SWIFT individualmente  
  
    -   Publicar mensajes SWIFT en la base de datos de cuadro de mensajes individualmente  
  
    -   Publicar todo el lote de entrada a la base de datos de cuadro de mensajes como un único mensaje (una copia exacta de entrada)  
  
    -   Promocionar propiedades de contexto relacionadas con el lote de correlación de mensajes que se origina en el mismo lote u ordenación  
  
 El ensamblador de SWIFT puede realizar las siguientes tareas cuando se invoca en una canalización de envío de BizTalk:  
  
-   Dinámicamente el tipo de mensaje de detectar y resolver el esquema del documento. Esto permite a un puerto de envío único y la canalización para controlar SWIFT varios tipos de mensajes.  
  
-   Serializar XML analizado en un archivo plano SWIFT.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el Desensamblador SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)