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
# <a name="data-transformation-configuration"></a><span data-ttu-id="45fd7-102">Configuración de transformación de datos</span><span class="sxs-lookup"><span data-stu-id="45fd7-102">Data Transformation Configuration</span></span>
<span data-ttu-id="45fd7-103">Cuando se realiza una asignación a partir de un elemento, una Transformación de lenguaje de hojas de estilo extensible (XSLT) típica presenta el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="45fd7-103">When mapping from an element, a typical Extensible Stylesheet Language Transformations (XSLT) looks as follows.</span></span>  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 <span data-ttu-id="45fd7-104">Si el elemento **BCT01** contiene contenido mixto, la utilización de text() hace posible tener acceso al primer texto solo hasta el punto del primer subelemento, si lo hay.</span><span class="sxs-lookup"><span data-stu-id="45fd7-104">If the element **BCT01** contains mixed content, the use of text() makes it possible to access the first text only up to the point of the first subelement, if any.</span></span> <span data-ttu-id="45fd7-105">Si text() no se utilizara en esta instrucción XSLT, el resultado sería que todo el contenido de texto, más cualquier contenido de texto de subelementos, se asignaría como una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="45fd7-105">If text() were not used in this XSLT statement, the result would be that all text content, plus any text content of subelements, would be mapped as one string of text.</span></span> <span data-ttu-id="45fd7-106">Configurar la **vínculos de origen** propiedad para un vínculo permite controlar el origen de los datos que se copian en la estructura definida por el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="45fd7-106">Configuring the **Source Links** property for a link allows you to control the source of the data that is copied into the structure defined by the destination schema.</span></span>  
  
 <span data-ttu-id="45fd7-107">Cuando se selecciona un vínculo en la página de cuadrícula mostrada, una de las propiedades se muestra en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades es el **vínculos de origen** propiedad.</span><span class="sxs-lookup"><span data-stu-id="45fd7-107">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Source Links** property.</span></span> <span data-ttu-id="45fd7-108">Puede elegir alguno de los siguientes valores posibles para cada vínculo de la asignación:</span><span class="sxs-lookup"><span data-stu-id="45fd7-108">You can choose between the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="45fd7-109">**Copiar valor de texto.**</span><span class="sxs-lookup"><span data-stu-id="45fd7-109">**Copy text value.**</span></span> <span data-ttu-id="45fd7-110">Utilice este valor, que es el predeterminado, para copiar el valor del elemento o atributo en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="45fd7-110">Use this value, which is the default, to copy the value of the element or attribute in the input instance message.</span></span> <span data-ttu-id="45fd7-111">Por ejemplo, si el elemento correspondiente es BoldExample, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="45fd7-111">For example, if the relevant element is BoldExample, as follows:</span></span>  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     <span data-ttu-id="45fd7-112">El valor copiado en el elemento o atributo correspondiente en el mensaje de instancia de salida es "This is a ".</span><span class="sxs-lookup"><span data-stu-id="45fd7-112">The value copied into the relevant element or attribute in the output instance message is "This is a ".</span></span> <span data-ttu-id="45fd7-113">Para elementos de contenido mixto como éste, el resultado puede no ser el deseado.</span><span class="sxs-lookup"><span data-stu-id="45fd7-113">For mixed content elements like this, this result may not be what is desired.</span></span> <span data-ttu-id="45fd7-114">Sin embargo, dado que los elementos de contenido mixto son relativamente escasos, el **Copiar valor de texto** para el **vínculos de origen** propiedad es suele ser apropiado en la mayoría de los casos.</span><span class="sxs-lookup"><span data-stu-id="45fd7-114">But because mixed content elements are relatively rare, the **Copy text value** setting for the **Source Links** property is probably appropriate in most cases.</span></span>  
  
-   <span data-ttu-id="45fd7-115">**Nombre de la copia.**</span><span class="sxs-lookup"><span data-stu-id="45fd7-115">**Copy name.**</span></span> <span data-ttu-id="45fd7-116">Utilice este valor para copiar el nombre del nodo en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="45fd7-116">Use this value to copy the name of the node in the input instance message.</span></span> <span data-ttu-id="45fd7-117">Por ejemplo, en la **Copiar valor de texto** descripción, el resultado es "BoldExample", que es el nombre real del elemento.</span><span class="sxs-lookup"><span data-stu-id="45fd7-117">For the example in the **Copy text value** description, the result is "BoldExample", which is the actual name of the element.</span></span>  
  
-   <span data-ttu-id="45fd7-118">**Copiar texto y Sub-valor de contenido.**</span><span class="sxs-lookup"><span data-stu-id="45fd7-118">**Copy text and sub content value.**</span></span> <span data-ttu-id="45fd7-119">Utilice este valor para concatenar los valores del nodo y todos los valores de sus nodos secundarios en el mensaje de instancia de entrada.</span><span class="sxs-lookup"><span data-stu-id="45fd7-119">Use this value to concatenate the values of the node and all values of its child nodes in the input instance message.</span></span> <span data-ttu-id="45fd7-120">Por ejemplo, en la **Copiar valor de texto** descripción, el resultado es "This is a Bold Text example.", que podría ser el resultado apropiado en elementos definidos para contener contenido mixto.</span><span class="sxs-lookup"><span data-stu-id="45fd7-120">For the example in the **Copy text value** description, the result is "This is a Bold Text example.", which might very well be the appropriate result for elements defined to contain mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45fd7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="45fd7-121">See Also</span></span>  
 <span data-ttu-id="45fd7-122">[Functoid de copia masiva](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="45fd7-122">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="45fd7-123">[Cómo establecer el valor de compilador de vínculos de origen](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="45fd7-123">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="45fd7-124">Coincidencia del nivel jerárquico de nodos</span><span class="sxs-lookup"><span data-stu-id="45fd7-124">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)