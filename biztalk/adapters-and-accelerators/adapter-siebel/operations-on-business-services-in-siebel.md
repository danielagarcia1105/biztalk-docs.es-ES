---
title: Operaciones en servicios empresariales de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24fa8ee0bd51ddf919e5f88a47ceae9d0743fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001373"
---
# <a name="operations-on-business-services-in-siebel"></a>Operaciones en servicios empresariales de Siebel
Un servicio de negocio de Siebel es una colección de métodos de negocio que se pueden invocar directamente en Siebel. Mientras que los objetos de negocios y componentes empresariales están asociados a los datos específicos y las tablas de Siebel, servicios de negocio invocan los objetos para llevar a cabo tareas específicas.  
  
 La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone los métodos de servicio empresarial, como nombres de operación y admite IN, OUT e INOUT parámetros. Por ejemplo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies el **ATPRunCheck** método como una operación. Este método pertenece a la **ATP** servicio empresarial.  
  
 Ciertas condiciones que los [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] impone al usar los servicios de negocios de Siebel:  
  
- Si un método de servicio de negocio de Siebel toma un argumento que no tiene el tipo de datos especificado, el adaptador expone el argumento como texto.  
  
- Un argumento de método de servicio de negocio de Siebel puede ser de los siguientes tipos:  
  
  - Cadena (expuesto como XSD: String)  
  
  - Número (expuestos como xsd: decimal)  
  
  - Fecha (expuesto como XSD: DateTime, con la faceta de patrón que indica que parte del tiempo se debe establecer en 00:00:00)  
  
  - Jerarquía (expuesto como XSD: String)  
  
  - Objeto de integración (expuesto como XSD: String)  
  
    Además, el método de servicio empresarial comprueba si el valor pasado para el argumento cumple con el tipo correspondiente. Por lo tanto, si un método de servicio de negocio acepta o devuelve valores que no son compatibles con el tipo del argumento correspondiente, el adaptador puede producir una excepción. Si el adaptador funciona al invocar el método de servicio empresarial, se puede producir un error en la validación del esquema.  
  
  Para obtener información acerca de:  
  
- Realizar operaciones en servicios empresariales con BizTalk Server, consulte [invocar Business Service métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).  
  
- Las estructuras y las acciones SOAP para realizar operaciones en servicios empresariales, vea mensajes [esquemas de mensaje para las operaciones de servicio de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)