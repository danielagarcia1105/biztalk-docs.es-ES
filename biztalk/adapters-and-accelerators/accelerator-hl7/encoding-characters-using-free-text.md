---
title: La codificación de caracteres con texto sin formato | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a69dffe1-3fb2-4902-a9a2-093f3ea7b11f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02294e089eef6fa541f7e5bbcd2864c6f1bf023d
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "25961642"
---
# <a name="encoding-characters-using-free-text"></a>La codificación de caracteres con texto sin formato
A partir de [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], "FreeText" puede utilizarse en un campo o un segmento. No se analizan los datos en el campo "FreeText" / segmento.  
  
## <a name="what-you-need-to-know"></a>Lo que necesita saber  
  
||Comportamiento|Ejemplo|  
|-|--------------|-------------|  
|~: Separador de repeticiones|En un campo, repetición (~) se trata como un delimitador de repetición. En un segmento no disponibles, repetición (~) se trata como un delimitador de repetición. En un segmento libre, repetición (~) se trata como parte de texto sin formato, no una repetición nuevo.|En el ejemplo siguiente, FRE es segmento libre. Puede tener cualquier carácter como texto sin formato, incluido ~. Las repeticiones adicionales (~) no se consideran un delimitador de repetición y se tratan como el contenido de texto sin formato. Validación se realiza correctamente aunque el elemento secundario del segmento libre es no repetibles y contiene repetición (~). Ejemplo FRE:<br /><br /> **FRE&#124; Foo & ^&#124;Foo & ^&#124;Foo & ^&#124;Foo & ^ ~ Foo & ^&#124;Foo & ^&#124;Foo & ^&#124;Foo & ^**<br /><br /> En el ejemplo siguiente, EVN4 se define como texto sin formato porque contiene *&^*. Cuando el "&#124;" delimitador se encuentra, se trata como el final de la factura actual. Ejemplo EVN:<br /><br /> **EVN&#124;&#124;&#124;&#124;Foo & ^ Foo & ^ Foo & ^ Foo & ^ Foo & ^&#124;&#124;**<br /><br /> En el ejemplo siguiente, el primer elemento secundario de EVN5 se define como texto sin formato porque contiene *&*. Cuando el "^" se encuentra delimitador, se trata como el final de la factura actual. Ejemplo de EVN5:<br /><br /> **EVN&#124; &#124; &#124; &#124; &#124; Foo & Foo Foo & Foo & Foo & ^ 5.2&#124;**<br /><br /> En el ejemplo siguiente, 5.2.1 y 5.2.2 no pueden tener cualquier delimitadores como texto sin formato, incluso si está definido como FreeText en el esquema. ejemplo de 5.2.1 y 5.2.2:<br /><br /> **EVN&#124; &#124; &#124; &#124; &#124; Foo1 ^ 5.2.1 & 5.2.2&#124;**<br /><br /> En el ejemplo siguiente, suponga EVN4 puede repetirse y es del tipo de texto sin formato. *Foo1 & ^* se considerará la primera repetición y *Foo2 & ^* se trata como la segunda repetición. Si no es repetible EVN4 (MaxOccurs = 1), la validación no se realizará correctamente si contiene ~, incluso si es de tipo de texto sin formato (como en los casos de los campos no texto libre). Ejemplo de EVN4:<br /><br /> **EVN &#124; &#124; &#124; &#124; Foo1 & ^ ~ Foo2 & ^&#124;&#124;**|  
|&#124;: Separador de campos|Si falta un delimitador de campo después de la etiqueta de segmento de un segmento libre, la validación es correcta.|En los ejemplos siguientes, FRE es un tipo de texto sin formato. Contenido de texto libre se puede iniciar inmediatamente después de que el FRE segmentar etiqueta, con o sin "&#124;" delimitador de campo. Ambos ejemplos correctamente:<br /><br /> **FREabc** <br /> **FRE&#124;abc**<br /><br /> En los ejemplos siguientes, validación es correcta:<br /><br /> Mensaje de entrada a DASM: **FRE&#124;abcd**<br />Salida de DASM:  **\<SegmentData\>&#124;abcd\</SegmentData\>**<br />Salida de ASM: **FRE&#124;abcd**<br /><br /> Mensaje de entrada a DASM: **FREabcd**<br />Salida de DASM:  **\<SegmentData\>abcd\</SegmentData\>**<br />Salida de ASM: **FREabcd**|  
|Elementos primarios y secundarios opcionales|Todavía se aplican las reglas de validación opcional de elementos primarios y secundarios.|El elemento primario es opcional y, a continuación, uno de sus elementos secundarios es obligatorio, se supone:<br /><br /> -Si no se rellena ninguno de los otros elementos secundarios y el elemento secundario obligatorio, validación del mensaje se realiza correctamente.<br />-Si al menos un elemento secundario se rellena, a continuación, el elemento secundario obligatorio debe también se pueden rellenar. En caso contrario, se produce un error en validación del mensaje.<br /><br /> En el ejemplo siguiente, el campo 1 como opcional. Su *1.a* secundario es opcional y es el tipo de texto sin formato. Su *1.b* secundarios es obligatorio:<br /><br /> **XYZ&#124;1.a^1.b&#124;2**<br /><br /> En el siguiente mensaje de ejemplo, *dfssdf**&** sdf* se considera como un solo elemento - 1.a. El analizador comprueba si existe 1.b. Cuando el *&#124;* es alcanza, supone 1.b no se rellena y se produce un error de validación del mensaje:<br /><br /> **XYZ&#124;dfssdf & sdf&#124;2**|  
|Segmentos de MSH, FSH y FIGF|Texto sin formato se omite para todos los campos. Estos segmentos corresponden a la sección de encabezado. Validación tiene lugar como lo haría normalmente, incluso si se definen como texto sin formato.||  
|\\: Carácter de escape|Si hay un número par de "\" en el elemento, la validación se realiza correctamente (incluso si no son contiguas). Si hay un número impar, se produce un error de validación. El mismo comportamiento continúa para campos de no texto libre. Con los campos de texto sin formato, no hay ninguna validación en el número; tratan como contenido de texto sin formato.||  
  
 [Delimitadores de mensaje](../../adapters-and-accelerators/accelerator-hl7/message-delimiters.md) proporciona más información sobre los separadores en estos ejemplos.  
  
## <a name="using-free-text"></a>Uso de texto sin formato  
  
1.  En el proyecto en Visual Studio, abra el esquema.  
  
2.  Haga clic en un registro, seleccione **Insertar nodo de esquema**, seleccione **elemento de campo secundario**.  
  
3.  En Propiedades, seleccione **tipo de datos**y, a continuación, seleccione **texto sin formato (SimpleType)**.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)