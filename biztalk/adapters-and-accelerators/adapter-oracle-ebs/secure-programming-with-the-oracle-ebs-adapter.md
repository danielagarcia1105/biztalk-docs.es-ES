---
title: Seguro de programación con el adaptador de Oracle EBS | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35b494f8-cb21-45c2-9bb4-097ba59ec52c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eae7e2c1be56a886578f7bba83901f218c42b94e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972181"
---
# <a name="secure-programming-with-the-oracle-ebs-adapter"></a>Programación segura con el adaptador de Oracle EBS
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?  
 Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, debe proporcionar un nombre de usuario y una contraseña para Oracle E-Business Suite. Debe hacerlo desde el **seguridad** ficha la **configurar el adaptador** cuadro de diálogo. Escribiendo el Oracle credenciales desde el **seguridad** pestaña en lugar de directamente en el **configurar un URI** campo, se asegura de lo siguiente:  
  
- Las credenciales no se mostrará en el **configurar un URI** campo de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] donde cualquiera con acceso a la pantalla del equipo puede leer el cuadro de diálogo.  
  
- Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
  Para obtener más información acerca de cómo generar un cliente WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para Oracle E-Business Suite, consulte [obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>¿Cuáles son los procedimientos recomendados para la configuración de credenciales en el código?  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona el **ClientCredentials** clase que le ayudarán a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio. Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma cualquier mecanismo de autenticación se especifica en la pila de canales del objeto y aplica el intercambio entre el cliente y el servicio.  
  
 Dado que el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] se hospeda en proceso con su aplicación de consumo, no es imprescindible usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que usa la aplicación de consumo. Sin embargo, se, considera recomendable hacerlo.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] fomenta el uso de la **ClientCredentials** clase. Esta propiedad especifica si el adaptador aceptará el nombre de usuario y la contraseña para la base de datos de Oracle en el URI de conexión. **AcceptCredentialsInUri** el valor predeterminado es **false**, lo que significa que el adaptador iniciará una excepción si el URI de conexión contiene credenciales. Puede establecer **AcceptCredentialsInUri** a **true** que proporcione las credenciales en la conexión URI, si es necesario en la aplicación cliente.  
  
 El ejemplo siguiente muestra cómo usar el **credenciales** propiedad para establecer credenciales para Oracle E-Business Suite en un **ChannelFactory**.  
  
```  
// Create binding and endpoint  
OracleEBSBinding binding = new OracleEBSBinding();  
EndpointAddress address = new EndpointAddress("oracleebs://ebs-instance");  
  
// Create the channel factory   
ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
  
// Set user name and password  
factory.Credentials.UserName.UserName = "myuser";  
factory.Credentials.UserName.Password = "mypassword";  
  
// Open the channel factory  
factory.Open();  
```  
  
 El ejemplo siguiente muestra cómo usar el **ClientCredentials** clase para establecer credenciales para Oracle E-Business Suite en un cliente de WCF.  
  
```  
// Initialize a new client for the SQLEXECUTE operation from configuration   
ConcurrentPrograms_ARClient client =   
  new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
// Set user name and password  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
// Open the client  
client.Open();  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>¿Cómo proporcionar para el intercambio de datos más segura a través de los límites del proceso?  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa. Dado que el adaptador se hospeda en proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Sin embargo, si la aplicación o servicio envía los mensajes que contienen información confidencial de la base de datos a través de un límite de proceso a otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno. [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] proporciona muchas opciones para ayudar a proteger los mensajes enviados entre clientes y servicios. Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte "Protección de servicios y clientes" en [ http://go.microsoft.com/fwlink/?LinkId=89725 ](http://go.microsoft.com/fwlink/?LinkId=89725). Para obtener información general sobre seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, vea "Seguridad de Windows Communication Foundation" en [ http://go.microsoft.com/fwlink/?LinkId=89726 ](http://go.microsoft.com/fwlink/?LinkId=89726).  
  
## <a name="see-also"></a>Vea también  
 [Proteger las aplicaciones de Oracle EBS](secure-your-oracle-ebs-applications.md)