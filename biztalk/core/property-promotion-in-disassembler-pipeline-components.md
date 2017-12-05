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
# <a name="property-promotion-in-disassembler-pipeline-components"></a><span data-ttu-id="05ada-102">Promoción de propiedades en componentes de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="05ada-102">Property Promotion in Disassembler Pipeline Components</span></span>
<span data-ttu-id="05ada-103">La promoción de propiedad es un proceso por el cual se extrae un valor de propiedad de un documento XML mediante una expresión XPath y se coloca en el contexto del mensaje de manera que se pueda utilizar para enrutamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="05ada-103">Property promotion is a process by which a property value is extracted from an XML document by using an XPath expression and placed on the message context so that it can be used for message routing.</span></span>  
  
 <span data-ttu-id="05ada-104">Si una propiedad promocionada no tiene valor predeterminado o valor fijo, el campo XML para esa propiedad falta, y la propiedad validar la estructura del documento es **False**, no se promociona la propiedad.</span><span class="sxs-lookup"><span data-stu-id="05ada-104">If a promoted property does not have a default or fixed value, the XML field for that property is missing, and the Validate Document Structure property is **False**, the property is not promoted.</span></span>  
  
 <span data-ttu-id="05ada-105">Un componente de canalización personalizado puede promocionar propiedades de múltiples valores (es decir, de matriz).</span><span class="sxs-lookup"><span data-stu-id="05ada-105">A custom pipeline component can promote multivalued (that is, arrayed) properties.</span></span> <span data-ttu-id="05ada-106">Los mensajes que contienen propiedades de múltiples valores solo se admiten en escenarios de enrutamiento por contenidos (CBR); no pueden enrutarse hacia orquestaciones ni utilizarse para realizar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="05ada-106">Messages that contain multivalued properties are only supported in content-based routing (CBR) scenarios; they cannot be routed to orchestrations or be used for tracking purposes.</span></span>  
  
 <span data-ttu-id="05ada-107">El desensamblador XML no promociona valores predeterminados o fijos de un elemento vacío si tiene una etiqueta de cierre.</span><span class="sxs-lookup"><span data-stu-id="05ada-107">The XML Disassembler does not promote default or fixed values for an empty element if it has a closing tag.</span></span> <span data-ttu-id="05ada-108">Por ejemplo, \<field1\> no se promociona en el siguiente código XML.</span><span class="sxs-lookup"><span data-stu-id="05ada-108">For example, \<field1\> is not promoted in the following XML.</span></span>  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 <span data-ttu-id="05ada-109">Sin embargo, un elemento vacío sin una etiqueta de cierre (como se muestra en el siguiente ejemplo) sí se promociona.</span><span class="sxs-lookup"><span data-stu-id="05ada-109">However, an empty element without a closing tag (as shown in the following example) is promoted.</span></span>  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 <span data-ttu-id="05ada-110">Al leer datos del valor datetime desde un documento y colocarlos en la propiedad de contexto, si los datos tienen el formato UTC, éste se conserva.</span><span class="sxs-lookup"><span data-stu-id="05ada-110">When reading datetime data from a document and placing it into the context property, if the data is in UTC format, that format is preserved.</span></span> <span data-ttu-id="05ada-111">Si los datos de datetime están en formato local + desplazamiento, el servidor BizTalk Server convierte el formato datetime en el formato UTC que resulta de sumar el desplazamiento a la hora local.</span><span class="sxs-lookup"><span data-stu-id="05ada-111">If the datetime data is in local+offset format, BizTalk Server converts the datetime format to the UTC format that results from adding the offset to the local time.</span></span> <span data-ttu-id="05ada-112">Si el formato datetime no especifica zona horaria o formato UTC, se entiende que la hora es local y se convierte a UTC en función de la zona horaria actual.</span><span class="sxs-lookup"><span data-stu-id="05ada-112">If the datetime format does not specify time zone or UTC format, the time is assumed to be local and is converted to UTC based on the current time zone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ada-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="05ada-113">See Also</span></span>  
 <span data-ttu-id="05ada-114">[Componente de canalización de desensamblador XML](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="05ada-114">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="05ada-115">Cómo configurar el componente de canalización de desensamblador XML</span><span class="sxs-lookup"><span data-stu-id="05ada-115">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)