---
title: Los procedimientos recomendados para proteger el adaptador de la base de datos de Oracle | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, best practices for connection between the Oracle Database adapter and the Oracle database
- security, best practices for WCF diagnostic tracing and message logging
- security, best practices for hosting the Oracle Database adapter in IIS
- credentials
- security, best practices
- security
- security, best practices for consuming the Oracle Database adapter with BizTalk Server
- security, protecting sensitive data
- user name password credential
- security, best practices for consuming the Oracle Database adapter with programming solutions
ms.assetid: 689e8442-91c9-4fe0-a0a0-ce5f5a98ab38
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7fcebeb32d4eee9d0e98367d6a852056fe5a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-to-secure-the-oracle-database-adapter"></a>Prácticas recomendadas para proteger el adaptador de la base de datos de Oracle
Esta sección proporciona prácticas recomendadas que debería seguir para proteger más completamente los datos confidenciales si utiliza o desarrollar aplicaciones que consumen la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  
  
## <a name="security-best-practices-for-the-connection-between-the-oracle-database-adapter-and-the-oracle-database"></a>Prácticas recomendadas de seguridad para la conexión entre el adaptador de la base de datos de Oracle y la base de datos de Oracle  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no proporciona compatibilidad con lo que ayuda a una comunicación segura entre ella y la base de datos de Oracle. Debe proporcionar un mecanismo para ayudar a garantizar un nivel adecuado de seguridad para los datos intercambiados entre el adaptador y la base de datos de Oracle.  
  
-   No se proporcionan credenciales de contraseña de nombre de usuario para la base de datos de Oracle en el URI de conexión. Vea las secciones siguientes para métodos alternativos de proporcionar credenciales para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también le permite usar la autenticación de Windows al conectarse a la base de datos de Oracle para generar los metadatos y realizar las operaciones, ya sea a través [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Antes de usar la autenticación de Windows, debe realizar los pasos enumerados en [conectarse a la base de datos de Oracle mediante autenticación Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).  
  
 Para obtener más información, consulte [seguridad entre la base de datos de Oracle y el adaptador](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md).  
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-biztalk-server"></a>Prácticas recomendadas de seguridad para utilizar el adaptador de la base de datos de Oracle con BizTalk Server  
  
-   No se proporcionan credenciales de contraseña de nombre de usuario para la base de datos de Oracle en el URI de conexión.  
  
-   Cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], escriba las credenciales de contraseña de nombre de usuario de la base de datos de Oracle desde la **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  
  
-   Al configurar el adaptador personalizado de WCF de BizTalk para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en un puerto de envío, escriba las credenciales de contraseña de nombre de usuario para la base de datos de Oracle desde la **credenciales** pestaña de la **Configurar transporte personalizado de WCF**  cuadro de diálogo.  
  
-   Al configurar el adaptador personalizado de WCF de BizTalk para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en una ubicación de recepción, escriba las credenciales de contraseña de nombre de usuario para la base de datos de Oracle desde la **otros** pestaña de la **Configurar transporte personalizado de WCF**  cuadro de diálogo.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también le permite usar la autenticación de Windows al conectarse a la base de datos de Oracle para generar los metadatos y realizar operaciones a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Antes de usar la autenticación de Windows, debe realizar los pasos enumerados en [conectarse a la base de datos de Oracle mediante autenticación Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).  
  
 Para obtener más información, consulte [seguridad con el adaptador de la base de datos de Oracle y BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md).
  
## <a name="security-best-practices-for-consuming-the-oracle-database-adapter-with-programming-solutions"></a>Prácticas recomendadas de seguridad para utilizar el adaptador de la base de datos de Oracle con las soluciones de programación  
  
-   A veces es necesario proporcionar al usuario las credenciales de contraseña de nombre de la base de datos de Oracle en la conexión URI; Sin embargo, si es posible, debe evitar hacerlo.  
  
-   Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], escriba las credenciales de contraseña de nombre de usuario de la base de datos de Oracle desde la **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  
  
-   En la programación de modelo del canal de WCF, use la **credenciales** propiedad en el generador de canales para establecer las credenciales de contraseña de nombre de usuario para la base de datos de Oracle.  
  
-   En la programación del modelo de servicio de WCF, use la **ClientCredentials** propiedad en el cliente WCF para establecer las credenciales de contraseña de nombre de usuario para la base de datos de Oracle.  
  
-   Si una aplicación que consume el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] envía los mensajes que contienen información confidencial de la base de datos en un límite de proceso para otro servicio o cliente, asegúrese de que estos mensajes tienen suficientes medidas de seguridad que se aplica para proporcionar datos adecuada protección de su entorno.  
  
-   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] también le permite usar la autenticación de Windows al conectarse a la base de datos de Oracle para generar los metadatos y realizar operaciones a través de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Antes de usar la autenticación de Windows, debe realizar los pasos enumerados en [conectarse a la base de datos de Oracle mediante autenticación Windows](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).  
  
 Para obtener más información, vea [segura de programación con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md).  
  
## <a name="security-best-practices-for-hosting-the-oracle-database-adapter-in-iis"></a>Prácticas recomendadas de seguridad para hospedar el adaptador de la base de datos de Oracle en IIS  
 Hospedar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en Microsoft Internet Information Services (IIS) como un sitio Web de servicio expone las operaciones obtenidas por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a los clientes Web. Estas operaciones podrían implicar intercambiar datos confidenciales a través de Internet, por lo que debe tomar medidas para ayudar a garantizar que estos datos son lo más seguros posible.  
  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]proporciona dos enlaces estándares para el transporte HTTP: el **BasicHttpBinding** proporciona el transporte HTTP básica con ningún mecanismo de seguridad; el **WSHttpBinding** admite tanto nivel de transporte y mecanismos de seguridad de nivel de mensaje.  
  
 Puede utilizar el **BasicHttpBinding** a través de una conexión HTTPS, o use el **WSHttpBinding** para ayudar a proteger los datos. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] incluye el [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)] para generar el servicio WCF para los artefactos LOB. Este asistente sólo admite el uso de **BasicHttpBinding**.  
  
 También puede desarrollar un enlace HTTP personalizado para aprovechar los mecanismos de seguridad adicional que proporciona el entorno. Para obtener más información acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [protección de servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx).  
  
## <a name="security-best-practices-for-wcf-diagnostic-tracing-and-message-logging"></a>Prácticas recomendadas de seguridad para el seguimiento de diagnóstico de WCF y el registro de mensajes  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]admite el seguimiento de diagnóstico y registro de mensajes. Configurar el seguimiento de diagnóstico y registro de mensajes a través de los archivos de configuración o mediante el uso de Windows Management Instrumentation (WMI). Según las opciones de configuración se establece, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] el seguimiento de diagnóstico o mensaje de registro puede emitir información confidencial para registrar los archivos, donde se podrían potencialmente exponerse a observación usuarios no autorizados.  
  
 Siga las recomendaciones proporcionadas en la documentación de WCF para mitigar posibles amenazas de seguridad que se muestran cuando se habilita estas características. Como mínimo, debe tener en cuenta las siguientes prácticas recomendadas para el seguimiento de diagnóstico y registro de mensajes:  
  
-   No habilite "detallado" o seguimiento de "información" en un entorno de producción. Esto puede provocar una degradación del rendimiento. Sin embargo, debe habilitar "Advertencia" y seguimiento de "error" en un entorno de producción. Si se habilita el seguimiento, debe tomar medidas de seguridad adecuadas para proteger los datos. Consulte la documentación de WCF para obtener más información.  
  
-   Asegúrese de que los archivos de registro y archivos de configuración están protegidos mediante listas de control de acceso (ACL).  
  
 Las advertencias siguientes se aplican específicamente a los mensajes que se intercambian entre una aplicación cliente y el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]seguimiento de diagnóstico puede iniciar el encabezado (pero no el cuerpo) de los mensajes intercambiados con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Dado que la acción del mensaje está en el encabezado del mensaje, de esta forma aparecen las operaciones invocadas en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] por el cliente.  
  
-   Si [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] está habilitado el registro de mensajes y `logMessagesAtServiceLevel` es `true`, el encabezado del mensaje (pero no el cuerpo del mensaje) de los mensajes intercambiados entre el cliente de adaptador y la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se registran. Dado que la acción del mensaje está en el encabezado del mensaje, de esta forma aparecen las operaciones que el cliente invoca en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Si `logEntireMessage` también es `true`, se registrará el cuerpo del mensaje. Esto puede revelar información confidencial de la base de datos.  
  
 Para obtener más información acerca de cómo mejorar la seguridad cuando se habilita el seguimiento de diagnóstico, vea [cuestiones de seguridad y sugerencias útiles para el seguimiento](https://msdn.microsoft.com/library/ms733053.aspx). Para obtener más información acerca de cómo mejorar la seguridad cuando se habilita el registro de mensajes, vea [cuestiones de seguridad para el registro de mensajes](https://msdn.microsoft.com/library/ms730318.aspx). 
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)