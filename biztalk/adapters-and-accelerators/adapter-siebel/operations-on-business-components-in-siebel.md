---
title: Operaciones en componentes de negocio de Siebel | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business components, operations on
- operations, on business components
- operations, on business components with picklist fields
ms.assetid: 5430a8bd-88eb-4851-92e3-676ca83780c9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc634d48d4a39e610247edbab98104bc3c6da379
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-business-components-in-siebel"></a>Operaciones en componentes de negocio de Siebel
Un componente de negocio de Siebel es una entidad lógica que asocia las columnas de una o varias tablas de base de datos en una única estructura. Los clientes de adaptador pueden realizar las siguientes operaciones en los componentes de negocios de Siebel mediante el adaptador:  
  
-   **Insertar**. Los clientes de adaptador pueden insertar uno o más registros en un componente empresarial.  
  
-   **Consulta**. Los clientes de adaptador pueden consultar los registros de uno o más de un componente empresarial. Esta operación toma los siguientes parámetros como entrada:  
  
    -   SearchExpr: Contiene una expresión de búsqueda. Todos los registros en un componente empresarial especificado se comparan con esta expresión de búsqueda y registros que coinciden se devuelven al cliente de adaptador.  
  
    -   SortSpec: Si hay varios registros que coinciden con la expresión de búsqueda, esta especificación determina el orden en que se devuelven los registros. Este parámetro es opcional.  
  
    -   QueryFields: Permite a los clientes de adaptador recuperar los valores de solo un subconjunto de campos de registros devueltos. Este parámetro es opcional.  
  
        > [!NOTE]
        >  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite el uso de nombres originales en el parámetro QueryField en la operación de consulta en el componente empresarial  
  
-   **Actualización**. Los clientes de adaptador pueden actualizar uno o más registros en un componente empresarial.  
  
-   **Eliminar**. Los clientes de adaptador pueden eliminar uno o más registros en un componente empresarial mediante la especificación de un conjunto de identificadores o proporcionando una expresión de búsqueda.  
  
    > [!NOTE]
    >  Además de otros parámetros de las operaciones de consulta, actualización y eliminación también toman un parámetro de ViewMode. Este parámetro toma un entero que determina los permisos de acceso del usuario. Para obtener más información sobre el parámetro ViewMode y los demás parámetros para estas operaciones, vea el mensaje de solicitud para las operaciones de componentes empresariales en [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 Para obtener información acerca de:  
  
-   Realizar operaciones en los componentes empresariales mediante BizTalk Server, vea [ejecutar operaciones en componentes empresariales mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-using-the-siebel-adapter-in-biztalk.md).  
  
-   Realizar operaciones en los componentes empresariales mediante el modelo de servicio WCF, vea [ejecutar operaciones en los componentes empresariales con el adaptador de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md).  
  
-   Realizar operaciones en los componentes empresariales mediante el modelo de canal WCF, vea [ejecutar operaciones en los componentes empresariales con el adaptador de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-the-siebel-adapter-using-wcf-service.md).  
  
-   Realizar operaciones en los componentes empresariales mediante estructuras de mensajes y las acciones de SOAP, vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
## <a name="operations-on-business-components-with-mvg-fields"></a>Operaciones en los componentes empresariales con campos MVG  
 Un componente de negocio de Siebel puede recuperar los campos de otros componentes empresariales mediante combinaciones o grupos con varios valores (MVG). Además de las operaciones de inserción, consulta, actualización y eliminación que se exponen para todos los componentes empresariales, los clientes de adaptador pueden realizar las siguientes operaciones en los componentes de negocios de Siebel mediante el adaptador:  
  
-   **Asociar**. Los clientes de adaptador pueden asociar registros especificando expresiones de búsqueda primarios y secundarios. Esto es aplicable sólo para los componentes empresariales con campos MVG. Las expresiones de búsqueda deben utilizar un filtro exactamente un registro para el elemento primario y el secundario componentes empresariales.  
  
-   **Desasociar**. Los clientes de adaptador pueden anular la asociación de registros mediante la especificación de expresiones de búsqueda primarios y secundarios. Esto es aplicable sólo para los componentes empresariales con campos MVG. Las expresiones de búsqueda deben filtrar exactamente un registro para el elemento primario y el secundario componentes empresariales.  
  
-   **Query_ [MVG_Child_Business_Comp]**. Los clientes de adaptador pueden consultar los registros secundarios que están asociados a un registro primario especificando el registro primario y el nombre del campo MVG. Esto es aplicable sólo para los componentes empresariales con campos MVG.  
  
    > [!NOTE]
    >  Además de otros parámetros, estas operaciones también tienen un parámetro de ViewMode. Este parámetro toma un entero que determina los permisos de acceso del usuario. Para obtener más información sobre el parámetro ViewMode y los demás parámetros para estas operaciones, vea el mensaje de solicitud para las operaciones de componentes empresariales en [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 Para obtener más información acerca de:  
  
-   Realizar estas operaciones en los componentes empresariales mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [ejecutar operaciones en los componentes empresariales con el adaptador MVG campos mediante BizTalk Server y Siebel](../../adapters-and-accelerators/adapter-siebel/run-operations-on-business-components-with-mvg-fields-using-the-siebel-adapter.md).  
  
-   Realizar estas operaciones en los componentes empresariales mediante el modelo de servicio WCF, consulte [ejecutar operaciones en los componentes empresariales con campos de MVG con el adaptador de Siebel mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/work-with-mvp-fields-using-the-siebel-adapter-and-the-wcf-service-model.md).  
  
-   Las estructuras y las acciones de SOAP para estas operaciones de mensajes, vea [esquemas de mensaje para las operaciones de componentes empresariales](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
## <a name="operations-on-business-components-with-picklist-fields"></a>Operaciones en los componentes empresariales con campos de lista desplegable  
 Tipos de campo de lista de selección de componentes empresariales constituyen una colección de valores desde el que los usuarios puedan elegir valores específicos para pasar al sistema Siebel. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite operaciones en un componente empresarial con los campos de la lista desplegable. Las operaciones en los componentes empresariales que contiene campos de la lista desplegable son los mismos que las operaciones en cualquier otro componente de negocio, como se describe en el párrafo anterior. Sin embargo, dependiendo del tipo de lista de selección, los valores de entrada para el componente empresarial pueden variar. Para obtener más información sobre las listas desplegables y sus tipos, consulte la documentación de Siebel.  
  
 Uno de los tipos de lista de selección, listas desplegables enlazados estáticos, se producen por los adaptadores de como una lista de selección enumerado tipo en los metadatos generados por el adaptador en tiempo de diseño. Contiene un conjunto estático de valores que debe especificarse para el tipo de lista de selección en tiempo de ejecución.  Al especificar un valor de una lista de desplegable enlazado estática, siempre debe especificar un valor que pertenece al conjunto.  
  
 La estructura del mensaje para realizar operaciones en los componentes empresariales con campos de la lista de selección es similar a las estructuras de mensajes para las operaciones en cualquier otro componente de negocio, como se describe en [esquemas de mensaje para las operaciones de componentes de negocio](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-component-operations.md).  
  
 Para obtener más información acerca de:  
  
-   Estructuras para los componentes empresariales que contiene campos de la lista de selección de mensajes, vea [esquema de mensaje para las operaciones de lista de selección](../../adapters-and-accelerators/adapter-siebel/message-schema-for-picklist-operations.md).  
  
-   Realizar operaciones en un componente empresarial que contiene campos de la lista de selección, consulte [ejecutar operaciones en los componentes empresariales con campos de lista desplegable mediante BizTalk Server y el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/run-tasks-on-business-components-with-picklist-fields-using-the-siebel-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)