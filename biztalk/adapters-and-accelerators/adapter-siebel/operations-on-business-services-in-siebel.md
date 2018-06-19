---
title: Operaciones en servicios de negocios de Siebel | Documentos de Microsoft
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
ms.openlocfilehash: a1ffd133d76b1f8cae3f1732e48f817fe4fb26b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221948"
---
# <a name="operations-on-business-services-in-siebel"></a>Operaciones en servicios de negocios de Siebel
Un servicio de negocios de Siebel es una colección de métodos de negocio que se pueden invocar directamente en Siebel. Mientras que los componentes empresariales y objetos comerciales están asociados a datos específicos y tablas de Siebel, servicios de negocio invocación los objetos para realizar tareas específicas.  
  
 La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone los métodos de servicio de negocio como nombres de operación y admite IN, OUT e INOUT parámetros. Por ejemplo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] superficies la **ATPRunCheck** método como una operación. Este método pertenece a la **ATP** servicio para la empresa.  
  
 Ciertas condiciones que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] impone al usar los servicios de negocios de Siebel:  
  
-   Si un método de servicio de negocios de Siebel toma un argumento que no tiene el tipo de datos especificado, el adaptador expone el argumento como texto.  
  
-   Un argumento de método de servicio de negocios de Siebel puede ser de los siguientes tipos:  
  
    -   Cadena (expuesto como XSD: String)  
  
    -   Número (expuestos como xsd: decimal)  
  
    -   Fecha (expuesto como XSD: DateTime, con la faceta de patrón que indica que parte de hora debe establecerse en 00:00:00)  
  
    -   Jerarquía (expuesto como XSD: String)  
  
    -   Objeto de integración (expuesto como XSD: String)  
  
     Además, el método de servicio de negocio comprueba si el valor pasado para un argumento cumple con el tipo correspondiente. Por lo tanto, si un método de servicio de negocio acepta o devuelve valores que no son compatibles con el tipo de argumento correspondiente, el adaptador puede producir una excepción. Si el adaptador funciona en invocar el método de servicio de negocio, se puede producir un error en la validación del esquema.  
  
 Para obtener información acerca de:  
  
-   Realizar operaciones en servicios de negocio mediante BizTalk Server, consulte [invocar Business servicio métodos mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).  
  
-   Estructuras y las acciones de SOAP para realizar operaciones en servicios de negocio, vea mensajes [esquemas de mensaje para las operaciones de servicio de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).  
  
## <a name="see-also"></a>Vea también  
 [Conectarse a un sistema SAP mediante el adaptador](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)