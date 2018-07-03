---
title: Degradación de propiedades en componentes de canalización de ensamblador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aa2e53c7bb4ca671bdc4879f537b550e23da5a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988077"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a>Degradación de propiedades en componentes de canalización de ensamblador
Puede utilizar la degradación de la propiedad para copiar un valor de propiedad del contexto del mensaje en el contenido del mensaje, su encabezado o finalizador. La degradación de propiedad se consigue utilizando una expresión XPath que se especifica en el documento o en el esquema de encabezado o finalizador.  
  
 Al escribir datos del valor datetime de la propiedad de contexto en el documento que se obtiene, BizTalk Server supone que todos los datos de datetime tienen el formato UTC.  
  
 El formato que se utiliza para escribir propiedades en los datos viene determinado por el tipo de datos XSD como se muestra en la siguiente tabla.  
  
|Tipo de datos|Formato|  
|---------------|------------|  
|xs:datetime|aaaa-MM-ddTHH:mm:ss.fffffffZ|  
|xs:date|aaaa-MM-ddZ|  
|xs:gDay|---ddZ|  
|xs:gMonth|--MM: Z|  
|xs:gMonthDay|--MM-ddZ|  
|xs:gYear|aaaaZ|  
|xs:gYearMonth|aaaa-MMZ|  
|xs:time|HH:mm:ss.fffffffZ|  
  
## <a name="property-demotion-and-envelopes"></a>Degradación de propiedades y sobres  
 A menudo, resulta útil degradar valores de un espacio de nombres de sistema o de varios (o de uno de sus propios espacios de nombres) al ensamblar archivos en un sobre. Entre otros escenarios comunes, se incluyen:  
  
- Se desea incluir el nombre de archivo original enviado al sistema en mensajes de salida para que los sistemas de servidor puedan efectuar un seguimiento del origen de los datos.  
  
- Se desea escribir datos del mensaje de cuerpo al encabezado. Por ejemplo, para un pedido, podría resultar útil escribir el nombre de envío en un sobre para sistemas de nivel inferior.  
  
- Se desea combinar varios campos distintos en el encabezado sin escribir código personalizado. La degradación de propiedades del ensamblador de XML o de archivo sin formato puede llevar a cabo el trabajo.  
  
  Es importante recordar que los componentes de ensamblador de XML y de archivo sin formato permiten especificar el esquema que se va a utilizar para el cuerpo del documento y el sobre. Puede seleccionar los mismos esquemas utilizados en el desensamblado o crear un nuevo esquema de sobre con campos distintos.  
  
  Para obtener un ejemplo de estos conceptos, consulte [EnvelopeProcessing (ejemplo de BizTalk Server)](../core/envelopeprocessing-biztalk-server-sample.md).  
  
## <a name="see-also"></a>Vea también  
 [Componente de canalización de ensamblador de archivo sin formato](../core/flat-file-assembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de ensamblador de archivo sin formato](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)