---
title: "Promoción de propiedades en componentes de canalización de desensamblador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c95c58dafe1f7f875232c5b65962e731334f16
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a>Promoción de propiedades en componentes de canalización de desensamblador
La promoción de propiedad es un proceso por el cual se extrae un valor de propiedad de un documento XML mediante una expresión XPath y se coloca en el contexto del mensaje de manera que se pueda utilizar para enrutamiento de mensajes.  
  
 Si una propiedad promocionada no tiene valor predeterminado o valor fijo, el campo XML para esa propiedad falta, y la propiedad validar la estructura del documento es **False**, no se promociona la propiedad.  
  
 Un componente de canalización personalizado puede promocionar propiedades de múltiples valores (es decir, de matriz). Los mensajes que contienen propiedades de múltiples valores solo se admiten en escenarios de enrutamiento por contenidos (CBR); no pueden enrutarse hacia orquestaciones ni utilizarse para realizar seguimientos.  
  
 El desensamblador XML no promociona valores predeterminados o fijos de un elemento vacío si tiene una etiqueta de cierre. Por ejemplo, \<field1\> no se promociona en el siguiente código XML.  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 Sin embargo, un elemento vacío sin una etiqueta de cierre (como se muestra en el siguiente ejemplo) sí se promociona.  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 Al leer datos del valor datetime desde un documento y colocarlos en la propiedad de contexto, si los datos tienen el formato UTC, éste se conserva. Si los datos de datetime están en formato local + desplazamiento, el servidor BizTalk Server convierte el formato datetime en el formato UTC que resulta de sumar el desplazamiento a la hora local. Si el formato datetime no especifica zona horaria o formato UTC, se entiende que la hora es local y se convierte a UTC en función de la zona horaria actual.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)