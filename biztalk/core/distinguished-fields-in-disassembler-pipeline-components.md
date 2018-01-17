---
title: "Componentes de canalización de campos distintivos en el Desensamblador | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, distinquished fields
- Flat File Disassembler [pipeline component], distinquished fields
- BizTalk Framework Disassembler [pipeline component], distinquished fields
- XML Disassembler [pipeline component], distinquished fields
ms.assetid: 7e51d2fe-0004-4a7b-9055-bd41e8a4b7ab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64e4c8f15d167f5343089c11b92b0f373aa45576
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="distinguished-fields-in-disassembler-pipeline-components"></a>Componentes de canalización de campos distintivos en el Desensamblador
Los componentes de desensamblador XML, desensamblador de BizTalk Framework o desensamblador de archivos sin formato escriben en el contexto del mensaje los campos distintivos definidos en un esquema.  
  
 *nombre usado* es el campo distintivo en XPath  
  
 *espacio de nombres URI* es "http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields"  
  
 El valor de la propiedad es el **System.String** especificado de valor extraído del documento XML utilizando XPath.  
  
 El siguiente esquema de ejemplo tiene un campo distintivo Price (precio).  
  
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
  
 Para la instancia de documento  
  
```  
<PO>  
            <Item>Bolt</Item>  
            <Price>10</Price>  
<PO>  
```  
  
 el desensamblador XML escribe un campo distintivo en un contexto del mensaje como se indica a continuación:  
  
 Nombre de la propiedad en el contexto: "/ * [local-name () = 'Pedido' y el espacio = 'http://SendHtmlMessage.PO'] /\*[local-name () = 'Precio' y el espacio ='']"  
  
 Namespace de la propiedad: http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields  
  
 Valor de la propiedad: 10  
  
> [!NOTE]
>  Si el tamaño de los valores de los elementos del documento XML supera los 85KB, puede que haya una degradación en el rendimiento a la hora de procesar estos documentos.  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de desensamblador de archivos sin formato](../core/flat-file-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)