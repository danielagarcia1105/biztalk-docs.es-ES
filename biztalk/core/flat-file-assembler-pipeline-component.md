---
title: Componente de canalización de ensamblador de archivos planos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component]
ms.assetid: 3c851771-55b2-4d21-9291-d707dd66837c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385b1f8ea6c2ce707069cde522ea2f6712290be7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245868"
---
# <a name="flat-file-assembler-pipeline-component"></a>Componente de canalización de ensamblador de archivo sin formato
Un ensamblador de archivo sin formato combina documentos individuales en un lote y, opcionalmente, le agrega un encabezado o finalizador (o ambos). Para obtener más información acerca de los archivos sin formato, vea [mensajes de archivo sin formato con registros delimitados](../core/flat-file-messages-with-delimited-records.md). Consulte también [mensajes de archivo sin formato con registros posicionales](../core/flat-file-messages-with-positional-records.md).  
  
 El componente de canalización de ensamblador de archivo sin formato no valida el mensaje XML entrante. Para garantizar la validación XML, incluya el componente de validador XML en la fase de preensamblado de la canalización de envío.  
  
 El componente de canalización de ensamblador de archivo sin formato solo admite conversiones que admita Microsoft .NET Framework. Cualquier conversión adicional puede hacerse escribiendo en un escritor de texto personalizado.  
  
 Para obtener información acerca de cómo configurar el componente de canalización de ensamblador de archivo sin formato, vea [cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md).  
  
> [!NOTE]
>  En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], no puede ensamblar mensajes en un intercambio.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Codificación de caracteres en el componente de canalización de ensamblador de archivo sin formato](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [Obligatoriedad de estructura del documento en el componente de canalización de ensamblador de archivo sin formato](../core/document-structure-enforcement-in-the-flat-file-assembler-pipeline-component.md)  
  
-   [Conservar delimitadores en el componente de canalización de ensamblador de archivo sin formato](../core/retaining-delimiters-in-the-flat-file-assembler-pipeline-component.md)