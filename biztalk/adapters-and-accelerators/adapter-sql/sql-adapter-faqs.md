---
title: Preguntas más frecuentes del adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25369e6b-d1f2-4abc-9ffc-4cb9aef1d3fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dee4b402e548f55dd8eab4583215d879c98186b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224868"
---
# <a name="sql-adapter-faqs"></a>Preguntas más frecuentes del adaptador de SQL
Los siguientes son algunas preguntas más frecuentes (P+f) relacionadas con [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en general.  
  
## <a name="how-can-i-use-the-sql-adapter-to-communicate-with-the-sql-server-database"></a>¿Cómo se puede usar el adaptador de SQL para comunicarse con la base de datos de SQL Server?  
 Puede usar el adaptador de SQL para comunicarse con la base de datos de SQL Server por desarrollar aplicaciones de BizTalk, mediante el modelo de servicio WCF o mediante el modelo de canal WCF. Para obtener más información, consulte [información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md).  
  
## <a name="what-interfaces-are-supported-by-the-sql-adapter-for-retrieving-metadata"></a>¿Qué interfaces son compatibles con el adaptador de SQL para recuperar los metadatos?  
 El adaptador de SQL admite dos interfaces para recuperar los metadatos:  
  
-   MetadataExchange proporcionada por WCF. WCF proporciona un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes obtener metadatos de la base de datos de SQL Server.  
  
-   IMetadataRetrievalContract proporcionada por el SDK LOB de WCF adaptador, que es compatible con los metadatos de exploración y búsqueda capacidades del adaptador.  
  
## <a name="how-does-the-sql-adapter-support-high-availability-of-data"></a>¿Cómo el adaptador de SQL admite alta disponibilidad de los datos?  
 Al especificar el [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md) para conectarse a una base de datos de SQL Server, el adaptador de SQL le permite especificar el nombre de una base de datos de SQL Server de conmutación por error para conectarse como si la base de datos principal de SQL Server no es está disponible. La base de datos de SQL Server de conmutación por error se especifica utilizando un parámetro opcional, FailoverPartner, en el URI de conexión.  
  
## <a name="can-i-migrate-biztalk-projects-created-using-the-previous-version-of-the-sql-adapter-to-use-the-wcf-based-sql-adapter-how"></a>¿Puedo migrar proyectos de BizTalk creados mediante la versión anterior del adaptador SQL para utilizar el adaptador de SQL basado en WCF? ¿Cómo?  
 Sí. Para conocer los pasos para migrar proyectos de BizTalk creados mediante la versión anterior del adaptador SQL para utilizar el adaptador de SQL basado en WCF, vea [tutoriales del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md).  
  
## <a name="does-the-sql-adapter-provide-a-secure-way-of-communicating-with-the-sql-server-database--are-there-any-best-practices-to-ensure-security-of-data"></a>¿El adaptador de SQL proporciona una forma segura de la comunicación con la base de datos de SQL Server?  ¿Existen las recomendaciones de seguridad para garantizar la seguridad de los datos?  
 El adaptador de SQL admite el inicio de sesión único (SSO) empresarial y la seguridad integrada para la autenticación en las conexiones que establece con la base de datos de SQL Server. Con SSO, las credenciales se cifran y almacenan en el registro. El sistema usa estas credenciales para determinar el acceso en lugar de requerir al usuario que escriba ellos donde podría verse por los actores no autorizados. La seguridad integrada utiliza las credenciales del usuario con sesión iniciada para tener acceso a SQL server. Esto también elimina la necesidad de los usuarios escriban las credenciales. El Administrador de base de datos debe configurar SQL para que acepte credenciales de los usuarios para la seguridad integrada para que funcione correctamente.  
  
 El adaptador de SQL también no permite especificar las credenciales de usuario en el URI de conexión para la base de datos de SQL Server mientras se trabaja con el agregar adaptador de servicio de referencia de complemento de Visual Studio y consumir un proyecto de BizTalk de servicio de adaptador de complementos para evitar credenciales que aparezcan en texto no cifrado. Además, la contraseña no se escribe en el archivo de configuración (generados por el agregar adaptador de servicio de referencia de complemento de Visual Studio) y el archivo de enlace (generados por el complemento de consumir un proyecto de BizTalk de servicio de adaptador).  
  
 Para obtener más información acerca de:  
  
-   Seguridad de los datos en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [proteger sus aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).  
  
-   Prácticas recomendadas para garantizar la seguridad de datos en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [las prácticas recomendadas para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).  
  
## <a name="is-there-a-gui-provided-by-the-sql-adapter-to-view-and-perform-operations-on-the-artifacts-in-my-underlying-sql-server-database"></a>¿Hay una GUI proporcionada por el adaptador de SQL para ver y realizar operaciones en los artefactos de mi base de datos de SQL Server subyacente?  
 El complemento de consumir un proyecto de BizTalk de servicio de adaptador y el agregar adaptador de servicio de referencia de complemento de Visual Studio proporcionan un cuadro de diálogo donde puede ver y realizar operaciones en los artefactos de la base de datos de SQL Server subyacente. Para obtener más información acerca de la interfaz gráfica de usuario proporcionada por el adaptador de SQL, consulte [exploración, búsqueda y metadatos de get para las operaciones de SQL con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md).  
  
## <a name="what-are-binding-properties-in-the-sql-adapter-where-can-i-find-information-about-all-the-binding-properties-in-sql-adapter"></a>¿Qué son propiedades de enlace en el adaptador de SQL? ¿Dónde puedo encontrar información sobre todas las propiedades de enlace en el adaptador de SQL?  
 Los clientes de adaptador pueden usar propiedades de enlace en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para configurar y controlar el comportamiento del adaptador. Para obtener información sobre todas las propiedades de enlace aparece en la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
## <a name="what-is-msdtc-do-i-need-to-bother-about-it-before-using-sql-adapter"></a>¿Qué es MSDTC? ¿Es necesario preocuparse antes de usar el adaptador de SQL?  
 MSDTC es el acrónimo Coordinador de transacciones distribuidas de Microsoft. MSDTC coordina varias transacciones entre varios administradores de recursos, como bases de datos y sistemas de archivos, colas de mensajes. Para usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe habilitar MSDTC. Para obtener información detallada acerca de cómo configurar MSDTC, vea [configurar MSDTC en el cliente de SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md).  
  
## <a name="where-can-i-find-information-about-the-sql-server-data-types-that-are-supported-in-the-sql-adapter"></a>¿Dónde puedo encontrar información sobre los tipos de datos de SQL Server que son compatibles con el adaptador de SQL?  
 Para conocer los tipos de datos de SQL Server que son compatibles con el adaptador de SQL, consulte [básica tipos de datos de SQL Server](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md).  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-sql-adapter"></a>Qué enfoque (BizTalk Server, modelo de servicio WCF o el modelo del canal WCF) ¿se puede usar para realizar diversas operaciones mediante el adaptador de SQL?  
 Para saber el enfoque que puede usar para realizar diversas operaciones mediante el adaptador de SQL, consulte [desarrollar las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md).  
  
 
## <a name="see-also"></a>Vea también  
 [Preguntas más frecuentes](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
 