---
title: Cómo configurar el componente de canalización de ensamblador de archivo sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], configuring
- messages, flat files
ms.assetid: 5af61bba-4eb2-4bb9-a655-394a76d08d3b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fe9c7a0720db68d8e629410dd3f0a443a99d7a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248636"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a>Cómo configurar el componente de canalización de ensamblador de archivo sin formato
El componente de canalización de ensamblador de archivo sin formato se utiliza para serializar un documento XML en un formato de archivo sin formato delimitado o posicional antes de enviarlo fuera del servidor.  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a>Para configurar las propiedades del componente de canalización de ensamblador de archivo sin formato  
  
1.  Arrastre el componente de canalización de ensamblador de archivo sin formato a la fase de ensamblado de la canalización de envío.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Esquema de documento**|Seleccionar el esquema de documento de archivos sin formato que se va a utilizar para serializar el mensaje de XML al formato de archivo sin formato. Si no se ha especificado ningún esquema, se utiliza la detección de esquemas en tiempo de ejecución. Puede crear el esquema de documento de archivo sin formato en el Editor de BizTalk.<br /><br /> Valor predeterminado: ninguno|  
    |**Esquema de encabezado**|Seleccionar un esquema para la parte del encabezado del mensaje de archivo sin formato. También puede especificarse un esquema de encabezado en la propiedad de contexto de mensaje denominada **HeaderSpecName** en el espacio de nombres xmlnorm. En este caso, reemplazará el esquema de encabezado especificado en el Diseñador de canalizaciones.<br /><br /> Puede crear el esquema para la parte del encabezado del mensaje de archivo sin formato con el Editor de BizTalk.<br /><br /> Valor predeterminado: ninguno|  
    |**Conservar marca de orden de bytes**|Especifica la agregación de una marca de orden de bytes (BOM) al documento creado por el componente de ensamblador.<br /><br /> Valor predeterminado: **False**|  
    |**Juego de caracteres de destino**|Especifica el juego de caracteres de destino utilizado para codificar los mensajes salientes.<br /><br /> Valor predeterminado: ninguno|  
    |**Esquema de finalizador**|Seleccionar un esquema para la parte del finalizador del mensaje de archivo sin formato. Puede crear el esquema para la parte del finalizador del mensaje de archivo sin formato en el Editor de BizTalk.<br /><br /> Valor predeterminado: ninguno|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador de archivo sin formato](../core/flat-file-assembler-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Propiedades y esquema de propiedad de archivo sin formato y XML](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)