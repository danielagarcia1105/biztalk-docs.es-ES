---
title: Base y los esquemas comunes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ca51abfcdbfe965bc3da8deeb97f72df736903
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="base-and-common-schemas"></a>Base y los esquemas comunes
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] ha implementado los registros y los elementos que componen los esquemas de mensaje individual en esquemas distintos. Este enfoque proporciona una única ubicación para proporcionar actualizaciones para los campos y formatos, aislar el esquema de mensaje de dichos cambios.  
  
 El esquema de base (**Types.xsd Base SWIFT**) contiene las definiciones de registro y elemento comunes que hacen referencia a los esquemas de mensaje. Las definiciones comunes de registro y elemento corresponden a los campos de mensaje de FIN de SWIFT. Debe agregar este esquema a cualquier proyecto que utiliza el esquema de mensaje. El esquema de base trata las reglas y las funciones comunes y define los formatos de A4SWIFT se utiliza para validar las instancias de mensaje adecuado. El esquema de SWIFT Base Types.xsd define XSD **simpleType** y elementos complejos para SWIFT campos. Ha definido SWIFT **simpleType** elementos para todos los campos de base, como la cantidad, velocidad, precio etc., que utiliza SWIFT en muchos de los campos. El esquema de SWIFT Base Types.xsd define también elementos complejos de XSD para los campos que incluyen muchos personalizado **simpleTypes** definido en el esquema. Por ejemplo, el **BankIdentifierCode** elemento complejo utiliza código del banco, código de país, código de área y código de la bifurcación. Los usuarios pueden agregar nuevos **simpleTypes** y elementos complejos que SWIFT campos espejo y pueden modificar los tipos existentes. También debe tener cuidado, sin embargo, cuando se modifican los tipos existentes, porque las características de validación de motor de reglas de negocios (BRE) y la validación de XML dependen de estos tipos definidos.  
  
 El esquema común (**Types.xsd de datos común de SWIFT**) define los juegos de caracteres apropiado para los campos en el esquema de base. SWIFT define estos juegos de caracteres, como se hace referencia en el *manual de usuario de SWIFT*. También debe agregar el esquema común a los proyectos de esquema.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)