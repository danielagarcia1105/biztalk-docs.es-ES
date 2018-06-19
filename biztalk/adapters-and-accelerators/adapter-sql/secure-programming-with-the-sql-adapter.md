---
title: Programación segura con el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c84744a-6595-4d93-afe7-39a7ccf1b6a0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44886b490ce63e8c34e1a5bdb41554c96a0873ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224028"
---
# <a name="secure-programming-with-the-sql-adapter"></a>Programación segura con el adaptador de SQL
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?  
 Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, es posible que deba proporcionar un nombre de usuario y contraseña para la base de datos de SQL Server. Debe escribir las credenciales de la **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no proporciona una opción para especificar el nombre de usuario y la contraseña como parte del URI de conexión. Esto garantiza lo siguiente:  
  
-   Las credenciales no se mostrará en el **configurar un URI** campo de la **agregar un complemento de referencia de servicio de adaptador** cuadro de diálogo donde cualquier persona con acceso a la pantalla del equipo puede leer.  
  
-   Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
 Para obtener más información acerca de cómo generar un cliente de WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de escribir un nombre de usuario y una contraseña para la base de datos de SQL Server, consulte [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>¿Cuáles son las prácticas recomendadas para establecer credenciales en el código?  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]proporciona el **ClientCredentials** clase para ayudarle a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio. Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma los mecanismos de autenticación se especifican en la pila de canales de ese objeto y aplica en el intercambio entre el cliente y el servicio.  
  
 Dado que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se hospeda en proceso con su aplicación que consume, que no es necesario usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que utiliza la aplicación que consume. Sin embargo, se, considera recomendable hacerlo.  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] requiere el uso de la **ClientCredentials** clase para pasar mediante programación las credenciales. El **AcceptCredentialsInUri** propiedad de enlace pasa por alto el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para evitar la transferencia de credenciales en el URI.  
  
 En el ejemplo siguiente se muestra cómo utilizar el **credenciales** propiedad para establecer credenciales para la base de datos de SQL Server en un **ChannelFactory**.  
  
```  
// Create binding and endpoint  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 En el ejemplo siguiente se muestra cómo utilizar el **ClientCredentials** clase para establecer credenciales para la base de datos de SQL Server en un cliente WCF.  
  
```  
// Initialize a new client for the SELECT operation on the Employee table   
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient(binding,address);  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>¿Cómo puedo proporcionan para el intercambio de datos más segura a través de límites de proceso?  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa. Dado que el adaptador está alojado en el proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Sin embargo, si la aplicación o servicio usado envía los mensajes que contienen información confidencial de la base de datos en un límite de proceso para otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno. [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]proporciona muchas opciones para ayudar a proteger los mensajes enviados entre los clientes y servicios. Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre los clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte [protección de servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx). Para obtener más información general acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[Prácticas recomendadas para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)