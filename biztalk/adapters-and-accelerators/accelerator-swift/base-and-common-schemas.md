---
title: Esquemas base y comunes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7f8f86e4b74b84cef556ae95bc6255d8575237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012573"
---
# <a name="base-and-common-schemas"></a>Esquemas base y comunes
Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] ha implementado los registros y los elementos que componen los esquemas de mensaje individual en esquemas distintos. Este enfoque proporciona una ubicación única para proporcionar actualizaciones para los campos y formatos, aislar el esquema de mensaje de dichos cambios.  
  
 El esquema de base (**Types.xsd Base SWIFT**) contiene las definiciones de registro y elemento comunes que hacen referencia a los esquemas de mensaje. Las definiciones comunes de registro y elemento corresponden a los campos de mensaje de FIN de SWIFT. Deberá agregar este esquema a cualquier proyecto que utiliza el esquema de mensaje. El esquema de base trata las reglas y las funciones comunes y define los formatos de A4SWIFT para validar las instancias de mensaje adecuado. El esquema de SWIFT Base Types.xsd define XSD **simpleType** y elementos complejos para los campos SWIFT. Ha definido SWIFT **simpleType** elementos para todos los campos de bases, como la cantidad, velocidad, precio etc., que usa SWIFT en muchos de los campos. El esquema de SWIFT Base Types.xsd define también elementos complejos de XSD para los campos que se incluyen muchos de personalizado **simpleTypes** definido en el esquema. Por ejemplo, el **BankIdentifierCode** elemento complejo que usa código del banco, código de país, código de área y código de la sucursal. Los usuarios pueden agregar nuevos **simpleTypes** y elementos complejos que reflejen los campos SWIFT y pueden modificar los tipos existentes. Debe procurar, sin embargo, al modificar tipos existentes, porque las características de validación de motor de reglas de negocios (BRE) y la validación de XML dependen de estos tipos definidos.  
  
 El esquema común (**Types.xsd datos comunes de SWIFT**) define los juegos de caracteres apropiado para los campos en el esquema de base. SWIFT define estos juegos de caracteres, como se hace referencia en el *manual del usuario de SWIFT*. También deberá agregar el esquema común a los proyectos de esquema.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)