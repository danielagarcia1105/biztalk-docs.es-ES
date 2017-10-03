---
title: "Documento de validación en el componente de canalización de desensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dcea790208bf0234c67c8c941e6355fb367d82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a>Validación de documentos en el componente de canalización de desensamblador XML
De forma predeterminada, el desensamblador XML no valida los documentos XML con respecto a un esquema. Sin embargo, puede configurar el desensamblador XML para validar un documento XML mediante el establecimiento del **validar la estructura del documento** propiedad.  
  
> [!CAUTION]
>  Si un campo para promoción se declara con un tipo de datos simples pero contiene datos complejos, la promoción de la propiedad causará resultados impredecibles. Para evitar este escenario, configure el desensamblador XML para llevar a cabo la validación de documentos estableciendo la **validar la estructura del documento** propiedad **True**.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)