---
title: "Cómo configurar el componente de canalización de ensamblador XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], configuring
- messages, XML documents
- messages, envelopes
- configuring, pipeline components
- pipeline components, XML Assembler
ms.assetid: 6d883819-a1d4-4ad0-b08f-fcd7583134d6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cf69d5bd982571aefcf794d6ad32b0e69499470
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-assembler-pipeline-component"></a>Cómo configurar el componente de canalización de ensamblador XML
El componente de canalización de ensamblador XML se utiliza para ajustar los documentos XML en los sobres XML antes de enviar un mensaje de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-properties-for-the-xml-assembler-pipeline-component"></a>Para configurar las propiedades del componente de canalización de ensamblador XML  
  
1.  Arrastre el componente de canalización de ensamblador XML a la fase de ensamblado de una canalización de envío.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Agregar instrucciones de procesamiento**|**Anexar**: valor de **agregar texto de instrucciones de procesamiento** debería anexarse a las instrucciones de procesamiento en el mensaje preexistentes.<br /><br /> **Crear nuevo:** valor de **agregar texto de instrucciones de procesamiento** especificado en el campo debería sobrescribir o reemplazar las instrucciones que aparecen en el mensaje de procesamiento preexistentes.<br /><br /> Si **crear nuevo** está activada, el **agregar texto de instrucciones de procesamiento** debe contener instrucciones de procesamiento válidas.<br /><br /> **Omitir**: si existe texto en el mensaje de instrucciones de procesamiento, se quita.<br /><br /> Valor predeterminado: **anexado**|  
    |**Agregar texto de instrucciones de procesamiento**|Especificar las instrucciones de procesamiento XML que se agregarán al principio del documento XML de destino. **Nota:** texto debe cumplir los estándares de instrucciones de procesamiento de XML de W3C de instrucción de procesamiento. <br /><br /> Valor predeterminado: ninguno|  
    |**Agregue las declaraciones XML**|Cuando **True**, agrega una declaración de XML similar al siguiente al documento saliente: `<?xml version='1.0' encoding='UTF-8'>`. Codificación se determina por la codificación de juego en tiempo de ejecución del documento de destino.<br /><br /> Valor predeterminado: **True**|  
    |**Esquemas de documentos**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al documento. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md). **Nota:** recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de documentos** propiedad. <br /><br /> Valor predeterminado: colección vacía|  
    |**Esquemas de sobres**|Indica el espacio de nombres y nombre de tipo del esquema o esquemas que se aplicarán a los sobres. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md). **Nota:** recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de sobres** propiedad. <br /><br /> Valor predeterminado: colección vacía|  
    |**Conservar marca de orden de bytes**|Especificar la agregación de una marca de orden de bytes (BOM) a los documentos creados por el componente de ensamblador.<br /><br /> Valor predeterminado: **True**|  
    |**Ámbito de instrucción de procesamiento**|Especificar si se llevará a cabo la definición de la instrucción de procesamiento en el sobre exterior o en el nivel de documento.<br /><br /> Valor predeterminado: **documento**|  
    |**Juego de caracteres de destino**|Especificar el juego de caracteres utilizado para codificar los mensajes salientes.<br /><br /> Valor predeterminado: ninguno|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador XML](../core/xml-assembler-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Propiedades y esquema de propiedad de archivo sin formato y XML](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)