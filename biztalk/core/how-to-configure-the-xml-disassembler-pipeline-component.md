---
title: "Cómo configurar el componente de canalización de desensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, pipeline components
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], configuring
- disassembly stage, pipelines
- receive pipelines, disassembly stage
ms.assetid: 93dd9148-4ae4-4868-b85d-66eada354f58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376daf04abb9bb555e9190fc819c3a3360cbe3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-disassembler-pipeline-component"></a>Cómo configurar el componente de canalización de desensamblador XML
El componente de canalización de desensamblador XML debe utilizarse en la fase de desensamblado de una canalización de recepción.  
  
### <a name="to-configure-the-properties-for-the-xml-disassembler-pipeline-component"></a>Para configurar las propiedades del componente de canalización de desensamblador XML  
  
1.  Arrastre el componente de canalización de desensamblador XML a la fase de desensamblado de una canalización de recepción.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Permitir mensaje desconocido**|Indica si se permite que los mensajes que no tienen un tipo de mensaje conocido pasen a través del desensamblador.<br /><br /> Valor predeterminado: **False**|  
    |**Esquemas de documentos**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al documento. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md).<br /><br /> Los esquemas especificados en esta propiedad deben tener espacios de nombres de destino únicos. Si alguno de los esquemas tiene el mismo espacio de nombres, puede que la validación de las instancias del documento no funcione como se esperaba. Si los esquemas tienen tienen el mismo espacio de nombres, debe crear una canalización separada para cada esquema y especificar un esquema cada componente de canalización de desensamblador XML o utilizar una canalización, pero no especificar ningún esquema como parámetros para la canalización de desensamblador XML componente.<br /><br /> Valor predeterminado: colección vacía|  
    |**Esquemas de sobres**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al sobre. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md).<br /><br /> Los esquemas especificados en esta propiedad deben tener espacios de nombres de destino únicos. Si alguno de los esquemas tiene el mismo espacio de nombres, puede que la validación de las instancias del documento no funcione como se esperaba. Si los esquemas tienen tienen el mismo espacio de nombres, debe crear una canalización separada para cada esquema y especificar un esquema cada componente de canalización de desensamblador XML o utilizar una canalización, pero no especificar ningún esquema como parámetros para la canalización de desensamblador XML componente.<br /><br /> Valor predeterminado: colección vacía|  
    |**Procesamiento de intercambio recuperable**|Cuando es "false" indica que todo el intercambio está desensamblado como unidad (si falla cualquiera de los mensajes que contiene, se suspende todo el intercambio).<br /><br /> Cuando es "true" indica que el desensamblador extrae los mensajes que contiene el intercambio de forma individual con la posibilidad de que algunos se propaguen mediante la ruta de mensajería y otros se suspendan.<br /><br /> Para obtener más información sobre el procesamiento de intercambio recuperable, consulte [el procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md).|  
    |**Validar la estructura del documento**|Cuando **True**, realiza una validación del mensaje entrante en el documento y, opcionalmente, los esquemas de sobres.<br /><br /> Si una propiedad promocionada no tiene un valor predeterminado o fijo y esta propiedad se establece en **False**, no se promociona la propiedad.<br /><br /> Valor predeterminado: **False** **Nota:** cuando **True**, recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para el **esquemas de documentos** o **esquemas de sobres** propiedades.|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md)   
 [Propiedades y esquema de propiedad de archivo sin formato y XML](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)