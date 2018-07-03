---
title: Seguro de programación con el adaptador de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials
- adapter, security considerations when programming on
- credentials, setting in code
- credentials, protecting
- security
ms.assetid: 06213c14-42b8-4d4a-b238-0aedbc27ab6a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15860ad8a0e1f4417229da2a87c83b0a54ea0120
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008189"
---
# <a name="secure-programming-with-the-oracle-database-adapter"></a>Programación segura con el adaptador de base de datos de Oracle
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?  
 Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, debe proporcionar un nombre de usuario y una contraseña para la base de datos de Oracle. Debe hacerlo desde el **seguridad** ficha la **configurar el adaptador** cuadro de diálogo. Escribiendo el Oracle credenciales desde el **seguridad** pestaña en lugar de directamente en el **configurar un URI** campo, se asegura de lo siguiente:  
  
- Las credenciales no se mostrará en el **Uri** campo de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] donde cualquiera con acceso a la pantalla del equipo puede leer el cuadro de diálogo.  
  
- Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
  Para obtener más información acerca de cómo generar un cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para la base de datos de Oracle, vea [obtener metadatos para operaciones de base de datos de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>¿Cuáles son los procedimientos recomendados para la configuración de credenciales en el código?  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona el **ClientCredentials** clase que le ayudarán a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio. Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma cualquier mecanismo de autenticación se especifica en la pila de canales del objeto y aplica el intercambio entre el cliente y el servicio.  
  
 Dado que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se hospeda en proceso con su aplicación de consumo, no es imprescindible usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que usa la aplicación de consumo. Sin embargo, se, considera recomendable hacerlo.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] fomenta el uso de la **ClientCredentials** clase. Esta propiedad especifica si el adaptador aceptará el nombre de usuario y la contraseña para la base de datos de Oracle en el URI de conexión. **AcceptCredentialsInUri** el valor predeterminado es **false**, lo que significa que el adaptador iniciará una excepción si el URI de conexión contiene credenciales. Puede establecer **AcceptCredentialsInUri** a **true** que proporcione las credenciales en el URI de conexión.  
  
 El ejemplo siguiente muestra cómo usar el **credenciales** propiedad para establecer credenciales para la base de datos de Oracle en un **ChannelFactory**.  
  
```  
// Create binding and endpoint  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress endpointAddress = new EndpointAddress("oracleDB://Adapter");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, endpointAddress))  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
  
// Open the channel factory  
factory.Open();  
```  
  
 El ejemplo siguiente muestra cómo usar el **ClientCredentials** clase para establecer las credenciales para la base de datos de Oracle en un cliente WCF.  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
SQLEXECUTEClient sqlExecuteClient = new SQLEXECUTEClient("OracleDBBinding_SQLEXECUTE");  
  
// Set user name and password  
sqlExecuteClient.ClientCredentials.UserName.UserName = "SCOTT";  
sqlExecuteClient.ClientCredentials.UserName.Password = "TIGER";  
  
// Open the client  
sqlExecuteClient.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>¿Cómo proporcionar para el intercambio de datos más segura a través de los límites del proceso?  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa. Dado que el adaptador se hospeda en proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Sin embargo, si la aplicación o servicio envía los mensajes que contienen información confidencial de la base de datos a través de un límite de proceso a otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno. [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] proporciona muchas opciones para ayudar a proteger los mensajes enviados entre clientes y servicios. Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte [proteger servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx). Para obtener información general sobre seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [seguridad de Windows Communication Foundation](https://msdn.microsoft.com/library/ms732362.aspx). 
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[Procedimientos recomendados](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)