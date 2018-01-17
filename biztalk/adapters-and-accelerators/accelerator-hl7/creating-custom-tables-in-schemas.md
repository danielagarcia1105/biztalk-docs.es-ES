---
title: Crear tablas personalizadas en esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a663dd593123e647f2f466b6d472d60bb32be1be
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-custom-tables-in-schemas"></a>Crear tablas personalizadas en esquemas
Puede crear una tabla personalizada en el tablevalues_\<*versión*\>esquema común de XSD. Puede basar una tabla personalizada en un tipo de datos existente, un tipo de base de datos, o en una enumeración definidos en una tabla.  
  
### <a name="to-create-a-z-table"></a>Para crear una tabla de Z  
  
1.  En el Explorador de soluciones, abra el archivo de esquema de tipo de datos común **tablevalues_\<*versión*\>.xsd**y, a continuación, haga clic en **abrir**.  
  
2.  En el Editor de BizTalk, haga clic en **HL7DefinedTables**, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.  
  
3.  Nombre de la tabla con una etiqueta que empieza por la letra "Z".  
  
4.  En el panel Propiedades, escriba los valores que desee para determinadas propiedades, según sea necesario.  
  
5.  Para asociar una enumeración con la tabla, en el panel Propiedades, establezca **Derived By** a **restricción**, haga clic en **enumeración**, haga clic en el botón de puntos suspensivos (...) para  **Enumeración**y, a continuación, escriba los valores que desea que la enumeración para que contenga en el Editor de enumeración. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)   
 [Control de segmentos de Z no declarados](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)