---
title: Los procedimientos recomendados para proteger el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e32379d7-800a-49b7-a09a-6b3f04a6e5ef
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd3f60d95c7e642dc456b6e860b3cde32ab9f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225556"
---
# <a name="best-practices-to-secure-the-sql-adapter"></a>Prácticas recomendadas para proteger el adaptador de SQL
Prácticas recomendadas que debería seguir más completamente protección los datos confidenciales si utiliza o desarrollar aplicaciones que consumen la [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].  
  
## <a name="security-best-practices-for-the-connection-between-the-sql-adapter-and-the-sql-server-database"></a>Prácticas recomendadas de seguridad para la conexión entre el adaptador de SQL y la base de datos SQL Server  
  
-   El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no proporciona compatibilidad con lo que ayuda a una comunicación segura entre ella y la base de datos de SQL Server. Debe proporcionar un mecanismo para ayudar a garantizar un nivel adecuado de seguridad para los datos intercambiados entre el adaptador y la base de datos de SQL Server.  
  
-   Por motivos de seguridad, la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no permite proporcionar credenciales de contraseña de nombre de usuario para la base de datos de SQL Server en el URI de conexión. Vea el resto de este tema para métodos alternativos de proporcionar credenciales para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
-   El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] también le permite usar la autenticación de Windows al conectarse a SQL Server para generar los metadatos y realizar las operaciones, ya sea a través [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Antes de usar la autenticación de Windows, debe agregar el usuario de Windows como un usuario en SQL Server Management Studio. Para obtener más información, consulte [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
 Para obtener más información, consulte [seguridad entre el servidor SQL Server y el adaptador](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md).
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-biztalk-server"></a>Prácticas recomendadas de seguridad para utilizar el adaptador de SQL con BizTalk Server  
  
-   El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no permite proporcionar credenciales de contraseña de nombre de usuario para la base de datos de SQL Server en el URI de conexión.  
  
-   Cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], escriba las credenciales de contraseña de nombre de usuario de la base de datos de SQL Server desde el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  
  
-   Al configurar el adaptador personalizado de WCF de BizTalk para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en un puerto de envío, escriba las credenciales de contraseña de nombre de usuario para la base de datos de SQL Server desde el **credenciales** pestaña de la **transporte WCF-Custom Propiedades** cuadro de diálogo.  
  
-   Al configurar el adaptador personalizado de WCF de BizTalk para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una ubicación de recepción, escriba las credenciales de contraseña de nombre de usuario para la base de datos de SQL Server desde el **otros** pestaña de la **transporte WCF-Custom Propiedades** cuadro de diálogo.  
  
-   Al usar [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar los metadatos, configuración de puerto de envío, o configurar el puerto de recepción, también puede utilizar la autenticación de Windows. Antes de usar la autenticación de Windows, debe agregar el usuario de Windows como un usuario en SQL Server Management Studio. Para obtener más información, consulte [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
 Para obtener más información, consulte [seguridad con el adaptador de SQL y BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md).
  
## <a name="security-best-practices-for-consuming-the-sql-adapter-with-programming-solutions"></a>Prácticas recomendadas de seguridad para utilizar el adaptador de SQL con las soluciones de programación  
  
-   A veces es necesario proporcionar al usuario las credenciales de contraseña de nombre de la base de datos de SQL Server en la conexión URI; Sin embargo, si es posible, debe evitar hacerlo.  
  
-   Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], escriba las credenciales de contraseña de nombre de usuario de la base de datos de SQL Server desde el **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  
  
-   En la programación del modelo de canal WCF, use la **credenciales** propiedad en el generador de canales para establecer las credenciales de contraseña de nombre de usuario para la base de datos de SQL Server.  
  
-   En la programación del modelo de servicio WCF, use la **ClientCredentials** propiedad en el cliente WCF para establecer las credenciales de contraseña de nombre de usuario para la base de datos de SQL Server.  
  
-   Si una aplicación que consume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] envía los mensajes que contienen información confidencial de la base de datos en un límite de proceso para otro servicio o cliente, asegúrese de que estos mensajes tienen suficientes medidas de seguridad que se aplica para proporcionar datos adecuada protección de su entorno.  
  
-   Al usar [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o conectarse a SQL Server desde una aplicación. NET, también puede utilizar la autenticación de Windows. Antes de usar la autenticación de Windows, debe agregar el usuario de Windows como un usuario en SQL Server Management Studio. Para obtener más información, consulte [conectar con SQL Server mediante la autenticación de Windows con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
 Para obtener más información, consulte [programación segura con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md). 
  
## <a name="security-best-practices-for-hosting-the-sql-adapter-in-iis"></a>Prácticas recomendadas de seguridad para hospedar el adaptador de SQL en IIS  
 Hospedar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en Microsoft Internet Information Services (IIS) como un sitio Web de servicio expone las operaciones obtenidas por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a los clientes Web. Estas operaciones podrían implicar intercambiar datos confidenciales a través de Internet, por lo que debe tomar medidas para ayudar a garantizar que estos datos son lo más seguros posible.  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]proporciona dos enlaces estándares para el transporte HTTP: el **BasicHttpBinding** proporciona el transporte HTTP básica con ningún mecanismo de seguridad; el **WSHttpBinding** admite tanto nivel de transporte y mecanismos de seguridad de nivel de mensaje.  
  
 Puede utilizar el **BasicHttpBinding** a través de una conexión HTTPS, o use el **WSHttpBinding** para ayudar a proteger los datos. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] incluye el [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)] para generar el servicio WCF para los artefactos LOB. Este asistente sólo admite el uso de **BasicHttpBinding**.  
  
 También puede desarrollar un enlace HTTP personalizado para aprovechar los mecanismos de seguridad adicional que proporciona el entorno. Para obtener más información acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [protección de servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx). 
  
 Al hospedar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] como un servicio Web, los desarrolladores Web deben tomar medidas para evitar las cadenas que se especifican en los usuarios de que se pasan directamente a la base de datos de SQL Server. Por ejemplo, si un sitio Web permite al usuario especificar un valor que se va a formar parte de una cláusula WHERE en una instrucción SELECT, la cadena de entrada se debe examinar para impedir la adición de otros comandos a la instrucción.  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>Prácticas recomendadas de seguridad para el seguimiento de diagnóstico de WCF y el registro de mensajes  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]admite el seguimiento de diagnóstico y registro de mensajes. Configurar el seguimiento de diagnóstico y registro de mensajes a través de los archivos de configuración o mediante el uso de Windows Management Instrumentation (WMI). Según las opciones de configuración se establece, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] el seguimiento de diagnóstico o mensaje de registro puede emitir información confidencial para registrar los archivos, donde se podrían potencialmente exponerse a observación usuarios no autorizados.  
  
 Siga las recomendaciones proporcionadas en la documentación de WCF para mitigar posibles amenazas de seguridad que se muestran cuando se habilita estas características. Como mínimo, debe tener en cuenta las siguientes prácticas recomendadas para el seguimiento de diagnóstico y registro de mensajes:  
  
-   No habilite "detallado" o seguimiento de "información" en un entorno de producción. Esto puede provocar una degradación del rendimiento. Sin embargo, debe habilitar "Advertencia" y seguimiento de "error" en un entorno de producción. Si se habilita el seguimiento, debe tomar medidas de seguridad adecuadas para proteger los datos. Consulte la documentación de WCF para obtener más información.  
  
-   Asegúrese de que los archivos de registro y archivos de configuración están protegidos mediante listas de control de acceso (ACL).  
  
 Las advertencias siguientes se aplican específicamente a los mensajes que se intercambian entre una aplicación cliente y el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]seguimiento de diagnóstico puede iniciar el encabezado (pero no el cuerpo) de los mensajes intercambiados con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Dado que la acción del mensaje está en el encabezado del mensaje, de esta forma aparecen las operaciones invocadas en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] por el cliente.  
  
-   Si [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] está habilitado el registro de mensajes y `logMessagesAtServiceLevel` es `true`, el encabezado del mensaje (pero no el cuerpo del mensaje) de los mensajes intercambiados entre el cliente de adaptador y la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se registran. Dado que la acción del mensaje está en el encabezado del mensaje, de esta forma aparecen las operaciones que el cliente invoca en el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Si `logEntireMessage` también es `true`, se registrará el cuerpo del mensaje. Esto puede revelar información confidencial de la base de datos.  
  
 Para obtener más información acerca de cómo mejorar la seguridad cuando se habilita el seguimiento de diagnóstico, vea [cuestiones de seguridad y sugerencias útiles para el seguimiento](https://msdn.microsoft.com/library/ms733053.aspx). Para obtener más información acerca de cómo mejorar la seguridad cuando se habilita el registro de mensajes, vea [cuestiones de seguridad para el registro de mensajes](https://msdn.microsoft.com/library/ms730318.aspx).
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)