---
title: Preguntas más frecuentes del adaptador de SQL | Microsoft Docs
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
ms.openlocfilehash: 83d94b47a7475e53d15e4f7866dea36bf1fcf08b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978485"
---
# <a name="sql-adapter-faqs"></a>Preguntas más frecuentes del adaptador de SQL
Los siguientes son algunas preguntas frecuentes (P+f) relacionadas con [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] en general.  
  
## <a name="how-can-i-use-the-sql-adapter-to-communicate-with-the-sql-server-database"></a>¿Cómo se puede usar el adaptador de SQL para comunicarse con la base de datos de SQL Server?  
 Puede usar el adaptador de SQL para comunicarse con la base de datos de SQL Server mediante el desarrollo de aplicaciones de BizTalk, mediante el modelo de servicio WCF o mediante el modelo de canal WCF. Para obtener más información, consulte [información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md).  
  
## <a name="what-interfaces-are-supported-by-the-sql-adapter-for-retrieving-metadata"></a>¿Qué interfaces son compatibles con el adaptador de SQL para recuperar los metadatos?  
 El adaptador de SQL es compatible con dos interfaces para recuperar los metadatos:  
  
-   MetadataExchange proporcionada por WCF. WCF ofrece un punto de conexión de intercambio de metadatos para todos los enlaces de WCF, que permite a los clientes a obtener los metadatos de la base de datos de SQL Server.  
  
-   IMetadataRetrievalContract proporcionada por el SDK LOB de WCF adaptador, que es compatible con los metadatos de examinar y buscar las capacidades del adaptador.  
  
## <a name="how-does-the-sql-adapter-support-high-availability-of-data"></a>¿Cómo admite alta disponibilidad de datos el adaptador de SQL?  
 Al especificar el [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md) para conectarse a una base de datos de SQL Server, el adaptador de SQL le permite especificar el nombre de una base de datos de SQL Server de conmutación por error para conectarse como si la base de datos principal de SQL Server no es está disponible. La base de datos de SQL Server de conmutación por error se especifica mediante un parámetro opcional, FailoverPartner, en el URI de conexión.  
  
## <a name="can-i-migrate-biztalk-projects-created-using-the-previous-version-of-the-sql-adapter-to-use-the-wcf-based-sql-adapter-how"></a>¿Puedo migrar proyectos de BizTalk creados mediante la versión anterior del adaptador SQL para utilizar el adaptador de SQL basados en WCF? ¿Cómo?  
 Sí. Para conocer los pasos para migrar los proyectos de BizTalk creados mediante la versión anterior del adaptador SQL para utilizar el adaptador de SQL basados en WCF, vea [tutoriales del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md).  
  
## <a name="does-the-sql-adapter-provide-a-secure-way-of-communicating-with-the-sql-server-database--are-there-any-best-practices-to-ensure-security-of-data"></a>¿El adaptador de SQL proporciona una forma segura de comunicarse con la base de datos de SQL Server?  ¿Existen los procedimientos recomendados para garantizar la seguridad de datos?  
 El adaptador de SQL admite el inicio de sesión único (SSO) empresarial y la seguridad integrada para la autenticación en las conexiones que establece con la base de datos de SQL Server. Con SSO, las credenciales se cifran y almacenan en el registro. El sistema usa estas credenciales para determinar el acceso en lugar de requerir al usuario que escriba ellos donde podría verse actores no autorizado. La seguridad integrada utiliza las credenciales del usuario con sesión iniciada para acceder a SQL server. Esto también elimina la necesidad de los usuarios escriban las credenciales. El Administrador de base de datos debe configurar SQL para aceptar las credenciales de usuarios para la seguridad integrada para que funcione correctamente.  
  
 El adaptador de SQL también no permiten especificar las credenciales de usuario en el URI de conexión para la base de datos de SQL Server mientras se trabaja con el complemento Add Adapter Service Reference Visual Studio y el complemento Consume un proyecto de BizTalk de servicio de adaptador para evitar credenciales que aparezca en texto no cifrado. Además, la contraseña no se escribe en el archivo de configuración (generados por el complemento Add Adapter Service Reference Visual Studio) y el archivo de enlace (generados por el proyecto de BizTalk de servicio de adaptador de consumir complemento).  
  
 Para obtener más información acerca de:  
  
- Seguridad de los datos en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [proteger las aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).  
  
- Procedimientos recomendados para garantizar la seguridad de datos en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [procedimientos recomendados para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md).  
  
## <a name="is-there-a-gui-provided-by-the-sql-adapter-to-view-and-perform-operations-on-the-artifacts-in-my-underlying-sql-server-database"></a>¿Hay una GUI proporcionada por el adaptador de SQL para ver y realizar operaciones en los artefactos de mi base de datos de SQL Server subyacente?  
 El complemento Consume un proyecto de BizTalk de servicio de adaptador y el complemento Add Adapter Service Reference Visual Studio proporcionan un cuadro de diálogo donde puede ver y realizar operaciones en los artefactos de la base de datos de SQL Server subyacente. Para obtener más información acerca de la interfaz gráfica de usuario proporcionada por el adaptador de SQL, consulte [examinar, buscar y obtener metadatos para operaciones de SQL mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md).  
  
## <a name="what-are-binding-properties-in-the-sql-adapter-where-can-i-find-information-about-all-the-binding-properties-in-sql-adapter"></a>¿Qué son propiedades de enlace en el adaptador de SQL? ¿Dónde puedo encontrar información sobre todas las propiedades de enlace en el adaptador de SQL?  
 Los clientes del adaptador pueden usar las propiedades de enlace en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para configurar y controlar el comportamiento del adaptador. Para obtener información sobre todas las propiedades de enlace aparece en la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
## <a name="what-is-msdtc-do-i-need-to-bother-about-it-before-using-sql-adapter"></a>¿Qué es MSDTC? ¿Es necesario preocuparse antes de usar el adaptador de SQL?  
 Microsoft Distributed Transaction Coordinator significa MSDTC. MSDTC coordina varias transacciones entre varios administradores de recursos como bases de datos, sistemas de archivos y las colas de mensajes. Para usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], debe habilitar MSDTC. Para obtener información detallada acerca de cómo configurar MSDTC, vea [configurar MSDTC en el cliente de SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md).  
  
## <a name="where-can-i-find-information-about-the-sql-server-data-types-that-are-supported-in-the-sql-adapter"></a>¿Dónde puedo encontrar información sobre los tipos de datos de SQL Server que se admiten en el adaptador de SQL?  
 Para conocer los tipos de datos de SQL Server que se admiten en el adaptador de SQL, consulte [tipos de datos de SQL Server básicas](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md).  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-sql-adapter"></a>¿El enfoque (BizTalk Server, modelo de servicio WCF o el modelo del canal WCF) puedo usar para realizar diversas operaciones mediante el adaptador de SQL?  
 Para obtener información sobre el enfoque que puede usar para realizar diversas operaciones mediante el adaptador de SQL, consulte [desarrollar aplicaciones SQL](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md).  
  
 
## <a name="see-also"></a>Vea también  
 [Preguntas más frecuentes](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
 