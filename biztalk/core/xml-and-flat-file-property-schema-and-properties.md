---
title: Propiedades y esquema de propiedad de archivo XML y plana | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d917b82-62c6-489f-99a9-97e429b6f7c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de871dedff280604a48c7e2adcd47bb6bea5d41
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006149"
---
# <a name="xml-and-flat-file-property-schema-and-properties"></a>Propiedades y esquema de propiedades de archivo sin formato y XML
El **http://schemas.microsoft.com/BizTalk/2003/xmlnorm-properties** espacio de nombres contiene propiedades que puede utilizar para configurar los componentes de canalización de ensamblador de archivo sin formato y el Desensamblador de archivo sin formato. Las propiedades se describen en la tabla siguiente.  

## <a name="properties-list"></a>Lista Propiedades

|Property|Tipo|Descripción|  
|--------------|----------|-----------------|  
|**FlatFileHeaderDocument**|xs:string|El encabezado de un documento de archivo sin formato entrante puede almacenarse con esta propiedad.|  
|**AllowUnrecognizedMessage**|xs:Boolean|Especifica si componentes XML deben procesar mensajes desconocidos.|  
|**ProcessingInstruction**|xs:string|Texto de instrucciones de procesamiento para documentos salientes.|  
|**DocumentSpecName**|xs:string|Esquema para componentes XML que se utilizará para analizar o serializar documentos.<br /><br /> Los esquemas especificados en esta propiedad deben tener espacios de nombres # root de destino únicos. Si alguno de los esquemas tiene el mismo espacio de nombres # root, puede que la validación de las instancias del documento no funcione como se esperaba. El espacio de nombres # root debe ser único.  Si los esquemas tienen que tener el mismo espacio de nombres # root, debe: bien crear una canalización independiente para cada esquema y especificar un esquema para cada componente de canalización de desensamblador XML, o bien usar una canalización, pero no especificar ningún esquema como parámetros del componente de canalización de desensamblador XML.  Esto también funcionará si no hay ningún espacio de nombres de destino.|  
|**EnvelopeSpecName**|xs:string|Especificación de sobre para componentes XML que se utilizará para analizar o serializar documentos.<br /><br /> Los esquemas especificados en esta propiedad deben tener espacios de nombres # root de destino únicos. Si alguno de los esquemas tiene el mismo espacio de nombres # root, puede que la validación de las instancias del documento no funcione como se esperaba. El espacio de nombres # root debe ser único.  Si los esquemas tienen que tener el mismo espacio de nombres # root, debe: bien crear una canalización independiente para cada esquema y especificar un esquema para cada componente de canalización de desensamblador XML, o bien usar una canalización, pero no especificar ningún esquema como parámetros del componente de canalización de desensamblador XML.  Esto también funcionará si no hay ningún espacio de nombres de destino.|  
|**TargetCharset**|xs:string|Juego de caracteres para componentes XML que se utilizará para codificar mensajes de salida.|  
|**SourceCharset**|xs:string|Juego de caracteres utilizado para codificar un documento antes de que el desensamblador XML lo procese.|  
|**ProcessingInstructionOption**|xs:int|Especificar cómo se agregan las instrucciones de procesamiento a los documentos salientes. Para obtener más información acerca de ProcessingInstructionOption, consulte [instrucciones de procesamiento en el componente de canalización de ensamblador XML](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md).|  
|**AddXMLDeclaration**|xs:boolean|Especificar si debe agregarse una declaración XML a un documento saliente.|  
|**HeaderSpecName**|xs:string|Especifica un encabezado de documento de archivo sin formato.|  
|**TrailerSpecName**|xs:string|Especifica un finalizador de documento de archivo sin formato.|  
|**PromotePropertiesOnly**|xs:boolean|Cuando se establece en **True**, el componente de desensamblador XML no quita un sobre de mensaje ni lo desensamblar. solo se realiza una promoción de propiedad.|  

## <a name="see-also"></a>Vea también  
- [Configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
- [Configurar el componente de canalización de desensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
- [Configurar el componente de canalización de ensamblador de XML](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
- [Configurar el componente de canalización de desensamblador de XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
- [Configurar componentes de canalización nativos](../core/configuring-native-pipeline-components.md)   
- **Propiedades de contexto de mensaje** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
