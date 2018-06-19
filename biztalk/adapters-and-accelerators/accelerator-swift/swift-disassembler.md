---
title: Desensamblador SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler
- messages, receive pipelines
- receive pipelines, messages
ms.assetid: 42641550-0c88-4535-b5d5-b90acb30a6d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0024abe862f777e7ee798991d97845ec5098a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214188"
---
# <a name="swift-disassembler"></a>Desensamblador SWIFT
Una canalización de recepción entrante procesa todos los mensajes enviados a un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (recibida en una ubicación de recepción).  
  
 Fases de ejecución lógico relacionados con el procesamiento de entrada componen BizTalk canalizaciones de recepción. Un componente de canalización de servicios o que implemente cada fase. En concreto, el Desensamblador de servicios de la fase de desensamblado en la canalización de recepción. A4SWIFT proporciona funcionalidad en un componente de desensamblador personalizado de procesamiento de mensajes de SWIFT específica.  
  
 El Desensamblador SWIFT, un desensamblador de archivos sin formato personalizado, proporciona funcionalidad para procesar lotes y los mensajes entrantes de SWIFT y realiza las siguientes funciones:  
  
-   Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento  
  
-   Analiza los archivos planos SWIFT en XML  
  
-   Invoca el lector para realizar la validación XML (esquema) de validación de XML  
  
-   Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE  
  
-   Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado de XML  
  
-   Procesa y desensambla lotes entrantes  
  
 En la siguiente ilustración se muestra los datos SWIFT Desensamblador flujo.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
 Para obtener más información acerca de cómo el Desensamblador SWIFT, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para SWIFT en tiempo de ejecución](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)