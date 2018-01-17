---
title: Crear tipos de datos personalizados en esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, creating Z data types [Z objects]
- data types, creating [Z objects]
- Z objects, creating Z data types
ms.assetid: e545c849-d414-4d5d-bb56-d3f9d5238c70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea38eb106b3554b72885355aaa9aef4928f4fda2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-custom-data-types-in-schemas"></a>Crear tipos de datos personalizados en esquemas
Puede crear un tipo de datos personalizados en el datatypes_\<*versión*\>esquema común de XSD. Puede basar un tipo de datos personalizado en un tipo de datos existente, un tipo de base de datos, o en una enumeración definidos en una tabla.  
  
### <a name="to-create-a-z-data-type"></a>Para crear un tipo de datos de Z  
  
1.  En el Explorador de soluciones de Visual Studio, abra el archivo de esquema de tipo de datos comunes (**datatypes_\<*versión*\>.xsd**) y, a continuación, haga clic en **abrir**.  
  
2.  En el Editor de BizTalk, haga clic en **HL7DefinedDataTypes**, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario** para crear un tipo de datos de componentes, o haga clic en  **Elemento secundario** para crear un tipo de datos simple.  
  
3.  Nombre para el tipo de datos con una etiqueta de tres caracteres a partir de "Z".  
  
4.  En el panel Propiedades, escriba los valores que desee para **Base Data Type**, **tipo de datos**y otras propiedades, según sea necesario.  
  
## <a name="see-also"></a>Vea también  
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [Crear tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)   
 [Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [Control de segmentos de Z no declarados](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)