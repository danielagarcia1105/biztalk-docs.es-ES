---
title: "Adaptador de Oracle E-Business Suite preguntas más frecuentes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7fe4e0-ddd5-402f-bbbc-b320850eaf3b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d576fa5dae04a43daa54f2d99e7f9c14d1341e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="oracle-e-business-suite-adapter-faqs"></a>Adaptador de Oracle E-Business Suite preguntas más frecuentes
Los siguientes son algunas preguntas más frecuentes (P+f) relacionadas con [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]. Consulte también [BizTalk Adapter Pack preguntas más frecuentes](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md).
  

## <a name="how-can-i-use-the-oracle-e-business-adapter-to-communicate-with-oracle-e-business-suite"></a>¿Cómo se puede usar el adaptador de Oracle E-Business para comunicarse con Oracle E-Business Suite?  
 Puede usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para comunicarse con Oracle E-Business Suite por desarrollar aplicaciones de BizTalk, mediante el modelo de servicio WCF o mediante el modelo de canal WCF. Para obtener más información, consulte [información general sobre el adaptador de BizTalk para Oracle E-Business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e).  
  
## <a name="what-interfaces-are-supported-by-the-oracle-e-business-adapter-for-retrieving-metadata"></a>¿Qué interfaces son compatibles con el adaptador de Oracle E-Business para recuperar los metadatos?  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es compatible con dos interfaces para recuperar los metadatos:  
  
-   MetadataExchange proporcionada por WCF. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos de Oracle E-Business Suite.  
  
-   IMetadataRetrievalContract proporcionada por el SDK LOB de WCF adaptador, que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
## <a name="how-does-the-adapter-connect-to-oracle-e-business-suite"></a>¿Cómo se conecta el adaptador para Oracle E-Business Suite?  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza los componentes de acceso de datos de Oracle para los clientes de Oracle. [Los sistemas LOB](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) enumera las versiones de cliente. Para conectarse a Oracle E-Business Suite, los clientes de adaptador deben proporcionar una cadena de conexión, [conexión identificador uniforme de recursos (URI)](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md). Internamente, el adaptador asigna el URI de conexión a una cadena de conexión para conectarse a la base de datos subyacente en Oracle E-Business Suite. Vea [crear una conexión a Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).  
  
## <a name="does-the-oracle-e-business-adapter-provide-a-secure-way-of-communicating-with-the-oracle-e-business-suite--are-there-any-best-practices-to-ensure-data-security"></a>¿El adaptador de Oracle E-Business proporciona una forma segura de la comunicación con Oracle E-Business Suite?  ¿Existen las recomendaciones de seguridad para garantizar la seguridad de datos?  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite el inicio de sesión único (SSO) empresarial para la autenticación en las conexiones que establece con Oracle E-Business Suite. El SSO utiliza una base de datos y un secreto principal para cifrar y almacenar las credenciales de usuario. También proporciona servicios para asignar cuentas de Microsoft Windows a credenciales secundarias que se utilizan para tener acceso a un sistema back-end.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] también requiere que escriba las credenciales de nombre de usuario y contraseña para conectarse a Oracle E-Business Suite. Estas credenciales se utilizan para autenticar al usuario y, por tanto, proporcionar un nivel de autorización para las conexiones. El adaptador de Oracle E-Business proporciona una serie de métodos a través del cual se pueden proporcionar estas credenciales. Para obtener información sobre cómo proporcionar credenciales de Oracle en soluciones de BizTalk de forma segura, consulte [seguridad con el adaptador y el servidor BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/security-with-the-oracle-e-business-suite-adapter-and-biztalk-server.md). Para obtener información sobre cómo proporcionar credenciales de Oracle en soluciones de programación de forma segura, consulte [segura de programación con el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/secure-programming-with-the-oracle-ebs-adapter.md).  
  
 Para obtener más información:  
  
-   Seguridad de los datos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [proteger sus aplicaciones de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md).  
  
-   Prácticas recomendadas para garantizar la seguridad de datos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [prácticas recomendadas de seguridad](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md).  
  
## <a name="is-there-a-gui-provided-by-the-oracle-e-business-adapter-to-view-and-perform-operations-on-the-artifacts-in-oracle-e-business-suite"></a>¿Hay una GUI proporcionada por el adaptador de Oracle E-Business para ver y realizar operaciones en los artefactos en Oracle E-Business Suite?  
 El complemento de consumir un proyecto de BizTalk de servicio de adaptador y el agregar adaptador de servicio de referencia de complemento de Visual Studio proporcionan un cuadro de diálogo donde puede ver y realizar operaciones en los artefactos en Oracle E-Business Suite. Para obtener más información acerca de la interfaz gráfica de usuario proporcionada por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [exploración, búsqueda y metadatos de get para las operaciones de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
## <a name="what-are-binding-properties-in-the-oracle-e-business-adapter-where-can-i-find-information-about-all-the-binding-properties-in-the-oracle-e-business-adapter"></a>¿Qué son propiedades de enlace en el adaptador de Oracle E-Business? ¿Dónde puedo encontrar información sobre todas las propiedades de enlace en el adaptador de Oracle E-Business?  
 Los clientes de adaptador pueden usar propiedades de enlace en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para configurar y controlar el comportamiento del adaptador. Para obtener información sobre todas las propiedades de enlace aparece en la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [trabajar con las propiedades de enlace](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
## <a name="what-are-inbound-and-outbound-operations-in-the-oracle-e-business-adapter"></a>¿Cuáles son las operaciones de entrada y salidas en el adaptador de Oracle E-Business?  
 En las operaciones de entrada, el sistema LOB (Oracle E-Business Suite) es el cliente y los clientes de adaptador son el servicio, en el que se originan las transacciones en Oracle E-Business Suite. Por ejemplo, las operaciones sondeo y la notificación.  
  
 En las operaciones de salida, los clientes de adaptador son el cliente y el sistema LOB (Oracle E-Business Suite) se convierte en el servicio, en el que las transacciones se originan desde los clientes de adaptador. Por ejemplo, la inserción, Select, Update y operación Delete en tablas, operación en procedimientos almacenados y funciones y operaciones compuestas de interfaz.  
  
## <a name="where-can-i-find-information-about-the-oracle-data-types-that-are-supported-in-the-oracle-e-business-adapter"></a>¿Dónde puedo encontrar información sobre los tipos de datos de Oracle que se admiten en el adaptador de Oracle E-Business?  
 Para obtener información acerca de los tipos de datos de Oracle admitidos en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [tipos básicos de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md).  
  
## <a name="what-is-applications-context-how-can-i-set-applications-context-for-various-oracle-artifacts-in-the-oracle-e-business-adapter"></a>¿Cuál es el contexto de las aplicaciones? ¿Cómo puedo establecer el contexto de las aplicaciones para distintos artefactos de Oracle en el adaptador de Oracle E-Business?  
 Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-oracle-e-business-adapter"></a>Qué enfoque (BizTalk Server, modelo de servicio WCF o el modelo del canal WCF) ¿se puede usar para realizar varias operaciones mediante el adaptador de Oracle E-Business?  
 Para obtener información sobre el enfoque puede usar para realizar diversas operaciones mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [desarrollar sus aplicaciones de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md).  
  
## <a name="see-also"></a>Vea también  
[Preguntas más frecuentes para BizTalk Adapter Pack](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)