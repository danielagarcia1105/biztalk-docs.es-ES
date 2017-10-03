---
title: "Configuración de transformación de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XSLT
- maps, compiling
- Source Links property
- BizTalk Mapper, compiler directives
- code samples, XSLT
- compiler directives, copy text and subcontentent value
- compiler directives, copy text value
- maps, XSLT
- compiler directives, copy name
- compiler directives
- maps, code sample [XSLT]
- XSLT, code samples
ms.assetid: 05abe091-5202-4590-99ec-e60ca53a4324
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8304d43f59f63e474a3257915521d5dc36c38d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-transformation-configuration"></a>Configuración de transformación de datos
Cuando se realiza una asignación a partir de un elemento, una Transformación de lenguaje de hojas de estilo extensible (XSLT) típica presenta el siguiente aspecto.  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 Si el elemento **BCT01** contiene contenido mixto, la utilización de text() hace posible tener acceso al primer texto solo hasta el punto del primer subelemento, si lo hay. Si text() no se utilizara en esta instrucción XSLT, el resultado sería que todo el contenido de texto, más cualquier contenido de texto de subelementos, se asignaría como una cadena de texto. Configurar la **vínculos de origen** propiedad para un vínculo permite controlar el origen de los datos que se copian en la estructura definida por el esquema de destino.  
  
 Cuando se selecciona un vínculo en la página de cuadrícula mostrada, una de las propiedades se muestra en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades es el **vínculos de origen** propiedad. Puede elegir alguno de los siguientes valores posibles para cada vínculo de la asignación:  
  
-   **Copiar valor de texto.** Utilice este valor, que es el predeterminado, para copiar el valor del elemento o atributo en el mensaje de instancia de entrada. Por ejemplo, si el elemento correspondiente es BoldExample, como se muestra a continuación:  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     El valor copiado en el elemento o atributo correspondiente en el mensaje de instancia de salida es "This is a ". Para elementos de contenido mixto como éste, el resultado puede no ser el deseado. Sin embargo, dado que los elementos de contenido mixto son relativamente escasos, el **Copiar valor de texto** para el **vínculos de origen** propiedad es suele ser apropiado en la mayoría de los casos.  
  
-   **Nombre de la copia.** Utilice este valor para copiar el nombre del nodo en el mensaje de instancia de entrada. Por ejemplo, en la **Copiar valor de texto** descripción, el resultado es "BoldExample", que es el nombre real del elemento.  
  
-   **Copiar texto y Sub-valor de contenido.** Utilice este valor para concatenar los valores del nodo y todos los valores de sus nodos secundarios en el mensaje de instancia de entrada. Por ejemplo, en la **Copiar valor de texto** descripción, el resultado es "This is a Bold Text example.", que podría ser el resultado apropiado en elementos definidos para contener contenido mixto.  
  
## <a name="see-also"></a>Vea también  
 [Functoid de copia masiva](../core/mass-copy-functoid.md)   
 [Cómo establecer el valor de compilador de vínculos de origen](../core/how-to-set-the-source-links-compiler-value.md)   
 [Coincidencia del nivel jerárquico de nodos](../core/node-hierarchy-level-matching.md)