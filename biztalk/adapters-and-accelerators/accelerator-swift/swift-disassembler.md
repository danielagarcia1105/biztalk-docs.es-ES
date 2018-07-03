---
title: Desensamblador de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 25c389e10a48287ef87495b32fe2d69644a8259e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010925"
---
# <a name="swift-disassembler"></a>Desensamblador de SWIFT
Una canalización de recepción entrante procesa todos los mensajes enviados a un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (se recibe en una ubicación de recepción).  
  
 Canalizaciones de recepción de las fases de la lógica de ejecución relacionados con el procesamiento de entrada se componen de BizTalk. Un componente de canalización de servicios o implementa cada fase. En concreto, el Desensamblador de servicios de la fase de desensamblado en la canalización de recepción. A4SWIFT proporciona la funcionalidad en un componente de desensamblador personalizado de procesamiento de mensajes de SWIFT específicos.  
  
 El Desensamblador de SWIFT, un desensamblador de archivos sin formato personalizado, proporciona funcionalidad para el procesamiento de lotes y los mensajes entrantes de SWIFT y realiza las siguientes funciones:  
  
- Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento  
  
- Analiza archivos planos SWIFT en XML  
  
- Invoca el lector para realizar la validación de XML (esquema) de validación de XML  
  
- Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE  
  
- Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado XML  
  
- Procesa y desensambla los lotes de entrada  
  
  La siguiente ilustración muestra los datos de desensamblador de SWIFT flujo.  
  
  ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro2.gif "FSA_Intro2")  
  
  Para obtener más información sobre el Desensamblador de SWIFT, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para el tiempo de ejecución de SWIFT](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)