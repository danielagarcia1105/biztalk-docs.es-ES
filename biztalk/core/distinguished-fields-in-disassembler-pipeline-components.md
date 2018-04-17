---
title: Componentes de canalización de campos distintivos en el Desensamblador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, distinquished fields
- Flat File Disassembler [pipeline component], distinquished fields
- BizTalk Framework Disassembler [pipeline component], distinquished fields
- XML Disassembler [pipeline component], distinquished fields
ms.assetid: 7e51d2fe-0004-4a7b-9055-bd41e8a4b7ab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a9c79050b4489238ed94444eaebf8c3dac79d9
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a><span data-ttu-id="e50f9-102">Componentes de canalización de campos distintivos en el Desensamblador</span><span class="sxs-lookup"><span data-stu-id="e50f9-102">Distinguished Fields in Disassembler Pipeline Components</span></span>
<span data-ttu-id="e50f9-103">Los componentes de desensamblador XML, desensamblador de BizTalk Framework o desensamblador de archivos sin formato escriben en el contexto del mensaje los campos distintivos definidos en un esquema.</span><span class="sxs-lookup"><span data-stu-id="e50f9-103">Distinguished fields defined in a schema are written to the message context by the XML Disassembler, BizTalk Framework Disassembler, or Flat File Disassembler pipeline components in the following format:</span></span>  
  
 <span data-ttu-id="e50f9-104">*nombre usado* es el campo distintivo en XPath</span><span class="sxs-lookup"><span data-stu-id="e50f9-104">*name used* is the distinguished field in XPath</span></span>  
  
 <span data-ttu-id="e50f9-105">*espacio de nombres URI* es "http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"</span><span class="sxs-lookup"><span data-stu-id="e50f9-105">*namespace URI* is "http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"</span></span>  
  
 <span data-ttu-id="e50f9-106">El valor de la propiedad es el **System.String** especificado de valor extraído del documento XML utilizando XPath.</span><span class="sxs-lookup"><span data-stu-id="e50f9-106">The value of the property is the **System.String** value extracted from the XML document using specified XPath.</span></span>  
  
 <span data-ttu-id="e50f9-107">El siguiente esquema de ejemplo tiene un campo distintivo Price (precio).</span><span class="sxs-lookup"><span data-stu-id="e50f9-107">The following example schema has a distinguished field Price.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns="http://SendHtmlMessage.PO" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://SendHtmlMessage.PO xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="PO">  
      <xs:annotation>  
         <xs:appinfo>  
            <b:properties>  
               <b:property distinguished="true" xpath="/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/*[local-  
               name()='Price' and namespace-uri()='']" />   
            </b:properties>  
         </xs:appinfo>  
      </xs:annotation>  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="Item" type="xs:string" />   
            <xs:element name="Price" type="xs:string" />   
         </xs:sequence>  
      </xs:complexType>  
   </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="e50f9-108">Para la instancia de documento</span><span class="sxs-lookup"><span data-stu-id="e50f9-108">For the document instance</span></span>  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 <span data-ttu-id="e50f9-109">el desensamblador XML escribe un campo distintivo en un contexto del mensaje como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e50f9-109">the XML Disassembler writes a distinguished field on a message context as follows:</span></span>  
  
 <span data-ttu-id="e50f9-110">Nombre de la propiedad en el contexto: `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`</span><span class="sxs-lookup"><span data-stu-id="e50f9-110">Name of the property on the context: `"/*[local-name()='PO' and namespace-uri()='http://SendHtmlMessage.PO']/\*[local-name()='Price' and namespace-uri()='']"`</span></span>  
  
 <span data-ttu-id="e50f9-111">Namespace de la propiedad: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span><span class="sxs-lookup"><span data-stu-id="e50f9-111">Namespace of the property: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields</span></span>  
  
 <span data-ttu-id="e50f9-112">Valor de la propiedad: 10</span><span class="sxs-lookup"><span data-stu-id="e50f9-112">Value of the property: 10</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e50f9-113">Si el tamaño de los valores de los elementos del documento XML supera los 85KB, puede que haya una degradación en el rendimiento a la hora de procesar estos documentos.</span><span class="sxs-lookup"><span data-stu-id="e50f9-113">If the size of any XML document element values exceeds 85KB, a degradation in the performance of processing those documents may occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e50f9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e50f9-114">See Also</span></span>  
 <span data-ttu-id="e50f9-115">[Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e50f9-115">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="e50f9-116">Cómo configurar el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="e50f9-116">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)
