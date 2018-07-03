---
title: Operaciones en componentes empresariales de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business components, operations on
- operations, on business components
- operations, on business components with picklist fields
ms.assetid: 5430a8bd-88eb-4851-92e3-676ca83780c9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2156aa058126e4029ee0002a24eca1bcedb19999
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988485"
---
# <a name="operations-on-business-components-in-siebel"></a>Operaciones en componentes empresariales de Siebel
Un componente empresarial de Siebel es una entidad lógica que asocia las columnas de una o varias tablas de base de datos en una única estructura. Los clientes del adaptador pueden realizar las siguientes operaciones en los componentes empresariales de Siebel mediante el adaptador:  
  
- **Insertar**. Los clientes del adaptador pueden insertar uno o más registros en un componente empresarial.  
  
- **Consulta**. Los clientes del adaptador pueden consultar uno o más registros de un componente empresarial. Esta operación toma los siguientes parámetros como entrada:  
  
  - SearchExpr: Contiene una expresión de búsqueda. Todos los registros en un componente empresarial especificado se comparan con esta expresión de búsqueda y los registros coincidentes se devuelven al cliente de adaptador.  
  
  - SortSpec: Si hay varios registros que coinciden con la expresión de búsqueda, esta especificación determina el orden en que se devuelven los registros. Este parámetro es opcional.  
  
  - QueryFields: Permite a los clientes del adaptador recuperar valores para solo un subconjunto de campos de registros devueltos. Este parámetro es opcional.  
  
    > [!NOTE]
    >  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite el uso de nombres originales en el parámetro QueryField en la operación de consulta en el componente empresarial  
  
- **Actualización**. Los clientes del adaptador pueden actualizar uno o más registros en un componente empresarial.  
  
- **Eliminar**. Los clientes del adaptador pueden eliminar uno o más registros en un componente empresarial mediante la especificación de un conjunto de identificadores o proporcionando una expresión de búsqueda.  
  
  > [!NOTE]
  >  Además de otros parámetros de las operaciones de consulta, actualización y eliminación también toman un parámetro de ViewMode. Este parámetro toma un entero que determina los permisos de acceso del usuario. Para obtener más información sobre el parámetro ViewMode y los demás parámetros para estas operaciones, vea el mensaje de solicitud para operaciones de componentes empresariales en [esquemas de mensaje para operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
  Para obtener información acerca de:  
  
- Realizar operaciones en componentes empresariales con BizTalk Server, consulte [ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md).  
  
- Realizar operaciones en componentes empresariales mediante el modelo de servicio WCF, consulte [ejecutar operaciones en componentes empresariales con el adaptador de Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md).  
  
- Realizar operaciones en componentes empresariales mediante el modelo de canal WCF, consulte [ejecutar operaciones en componentes empresariales con el adaptador de Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md).  
  
- Realizar operaciones en componentes empresariales con estructuras de mensajes y las acciones de SOAP, consulte [esquemas de mensaje para operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
## <a name="operations-on-business-components-with-mvg-fields"></a>Operaciones en componentes empresariales con campos MVG  
 Un componente empresarial de Siebel también puede recuperar los campos de otros componentes empresariales mediante combinaciones o grupos con varios valores (MVG). Además de las operaciones de consulta, Insert, Update y Delete que se exponen para todos los componentes empresariales, los clientes del adaptador pueden realizar las siguientes operaciones en los componentes empresariales de Siebel mediante el adaptador:  
  
- **Asociar**. Pueden asociar a los clientes del adaptador registros mediante la especificación de las expresiones de búsqueda para el elemento primario y secundario. Esto es aplicable solo para los componentes empresariales con campos MVG. Las expresiones de búsqueda deben filtrar exactamente un registro para los componentes empresariales primario o secundario.  
  
- **Desasociar**. Los clientes del adaptador pueden desasociar registros mediante la especificación de las expresiones de búsqueda para el elemento primario y secundario. Esto es aplicable solo para los componentes empresariales con campos MVG. Las expresiones de búsqueda deben filtrar exactamente un registro para los componentes empresariales primario o secundario.  
  
- **Query_ [MVG_Child_Business_Comp]**. Los clientes del adaptador pueden consultar los registros secundarios que están asociados con un registro principal especificando el registro primario y el nombre del campo MVG. Esto es aplicable solo para los componentes empresariales con campos MVG.  
  
  > [!NOTE]
  >  Además de otros parámetros, estas operaciones también toman un parámetro de ViewMode. Este parámetro toma un entero que determina los permisos de acceso del usuario. Para obtener más información sobre el parámetro ViewMode y los demás parámetros para estas operaciones, vea el mensaje de solicitud para operaciones de componentes empresariales en [esquemas de mensaje para operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
  Para obtener más información acerca de:  
  
- Realizar estas operaciones en componentes empresariales mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones en componentes empresariales con campos MVG mediante BizTalk Server y Siebel adaptador](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md).  
  
- Realizar estas operaciones en componentes empresariales mediante el modelo de servicio WCF, consulte [ejecutar operaciones en componentes empresariales con campos MVG con el adaptador de Siebel mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md).  
  
- Estructuras de mensajes de acciones SOAP para estas operaciones, vea [esquemas de mensaje para operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
## <a name="operations-on-business-components-with-picklist-fields"></a>Operaciones en componentes empresariales con campos de lista desplegable  
 Tipos de campo de lista desplegable de componentes empresariales constituyen una colección de valores desde el que los usuarios puedan elegir valores específicos para pasar al sistema Siebel. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite operaciones en un componente empresarial con campos de lista desplegable. Las operaciones en componentes empresariales que contiene campos de lista desplegable son los mismos que las operaciones en cualquier otro componente de negocio, como se describe en el párrafo anterior. Sin embargo, según el tipo de lista desplegable, los valores de entrada para el componente empresarial pueden variar. Para obtener más información acerca de las listas desplegables y sus tipos, consulte la documentación de Siebel.  
  
 Uno de los tipos de lista desplegable, listas desplegables delimitados estáticos, aparecen por los adaptadores como una lista desplegable enumerado tipo en los metadatos generados por el adaptador en tiempo de diseño. Contiene un conjunto estático de valores que se deben especificar en tiempo de ejecución para el tipo de lista desplegable.  Al especificar un valor para una lista desplegable delimitada estática, siempre debe especificar un valor que pertenece al conjunto.  
  
 La estructura del mensaje para realizar operaciones en componentes empresariales con campos de lista desplegable es similar a las estructuras de mensajes para las operaciones en cualquier otro componente de negocio, como se describe en [esquemas de mensaje para operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 Para obtener más información acerca de:  
  
-   Estructuras para los componentes empresariales que contiene campos de lista desplegable de mensajes, vea [esquema de mensaje para operaciones de lista desplegable](../../adapters-and-accelerators/adapter-siebel/message-schema-for-picklist-operations.md).  
  
-   Realizar operaciones en un componente empresarial que contiene campos de lista desplegable, consulte [ejecutar operaciones en componentes empresariales con campos de lista desplegable mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)