---
title: "Cómo configurar el componente de canalización de desensamblador de BizTalk Framework | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- disassembly stage, pipelines
- receive pipelines, disassembly stage
- BizTalk Framework Disassembler [pipeline component], configuring
ms.assetid: a5599bcb-dbee-46a5-a91d-3c54f901cd30
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07fefb577e5322fa303a1a1476a976b453adb083
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a>Cómo configurar el componente de canalización de desensamblador de BizTalk Framework
El componente de canalización de desensamblador de BizTalk Framework debe utilizarse en la fase de desensamblado de una canalización de recepción.  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a>Para configurar las propiedades del componente de canalización de desensamblador de BizTalk Framework  
  
1.  Arrastre el componente de canalización de desensamblador de BizTalk Framework hasta la fase de desensamblado de una canalización de recepción.  
  
2.  En la ventana Propiedades, en la **propiedades de componente de canalización** sección, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Permitir mensaje desconocido**|Indica si se permite que los mensajes sin un esquema reconocido pasen a través del desensamblador.<br /><br /> Valor predeterminado: **False**|  
    |**Esquemas de documentos**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al documento. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md).<br /><br /> Los esquemas especificados en esta propiedad deben tener espacios de nombres de destino únicos. Si alguno de los esquemas tiene el mismo espacio de nombres, puede que la validación de las instancias del documento no funcione como se esperaba. Si los esquemas tienen que tener el mismo espacio de nombres, debe: bien crear una canalización separada para cada esquema y especificar un esquema para cada componente de canalización de desensamblador de BizTalk Framework, o bien utilizar una canalización, pero no especificar ningún esquema como parámetros del componente de canalización de desensamblador de BizTalk Framework.<br /><br /> Valor predeterminado: colección vacía|  
    |**Esquemas de sobres**|Indica el espacio de nombres y el nombre de tipo del esquema o esquemas que se van a aplicar al sobre. Para obtener más información, consulte [cómo utilizar el Editor de propiedades de la colección de esquema](../core/how-to-use-the-schema-collection-property-editor.md).<br /><br /> Los esquemas especificados en esta propiedad deben tener espacios de nombres de destino únicos. Si alguno de los esquemas tiene el mismo espacio de nombres, puede que la validación de las instancias del documento no funcione como se esperaba. Si los esquemas tienen que tener el mismo espacio de nombres, debe: bien crear una canalización separada para cada esquema y especificar un esquema para cada componente de canalización de desensamblador de BizTalk Framework, o bien utilizar una canalización, pero no especificar ningún esquema como parámetros del componente de canalización de desensamblador de BizTalk Framework.<br /><br /> Valor predeterminado: colección vacía|  
    |**Validar la estructura del documento**|Cuando **True**, realiza una validación del mensaje entrante en el desensamblador, incluidos los sobres. **Nota:** cuando **True**, recibirá un error "dos o más esquemas seleccionados comparten el mismo espacio de nombres de destino" Si especifica dos o más esquemas para la **esquemas de documentos,** o **Esquemas de sobres** propiedades. <br /><br /> Valor predeterminado: **False**|  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador de BizTalk Framework](../core/biztalk-framework-disassembler-pipeline-component.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
 [Las canalizaciones-AssemblerDisassembler (carpeta de ejemplos de BizTalk Server)](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)