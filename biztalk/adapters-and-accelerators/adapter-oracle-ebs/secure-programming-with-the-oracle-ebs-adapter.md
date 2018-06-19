---
title: Programar con el adaptador de Oracle EBS segura | Documentos de Microsoft
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
ms.openlocfilehash: 89a51a163c12a14fc58bdcefc5ffe6aab7df6d9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218140"
---
# <a name="secure-programming-with-the-oracle-ebs-adapter"></a>Programación segura con el adaptador de Oracle EBS
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?  
 Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, debe proporcionar un nombre de usuario y una contraseña para Oracle E-Business Suite. Debe hacerlo desde el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Escribiendo el Oracle credenciales desde el **seguridad** ficha en lugar de directamente en el **configurar un URI** campo Asegúrese de lo siguiente:  
  
-   Las credenciales no se mostrará en el **configurar un URI** campo de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] cuadro de diálogo donde cualquier persona con acceso a la pantalla del equipo puede leer.  
  
-   Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
 Para obtener más información acerca de cómo generar un cliente de WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de escribir un nombre de usuario y una contraseña para Oracle E-Business Suite, consulte [obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>¿Cuáles son las prácticas recomendadas para establecer credenciales en el código?  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]proporciona el **ClientCredentials** clase para ayudarle a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio. Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma los mecanismos de autenticación se especifican en la pila de canales de ese objeto y aplica en el intercambio entre el cliente y el servicio.  
  
 Dado que la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] se hospeda en proceso con su aplicación que consume, que no es necesario usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que utiliza la aplicación que consume. Sin embargo, se, considera recomendable hacerlo.  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] recomienda el uso de la **ClientCredentials** clase. Esta propiedad especifica si el adaptador aceptará el nombre de usuario y la contraseña para la base de datos de Oracle en el URI de conexión. **AcceptCredentialsInUri** tiene como valor predeterminado **false**, lo que significa que el adaptador iniciará una excepción si el URI de conexión contiene credenciales. Puede establecer **AcceptCredentialsInUri** a **true** para proporcionar credenciales en la conexión de URI, si es necesario en la aplicación cliente.  
  
 En el ejemplo siguiente se muestra cómo utilizar el **credenciales** propiedad para establecer las credenciales para Oracle E-Business Suite en un **ChannelFactory**.  
  
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
  
 En el ejemplo siguiente se muestra cómo utilizar el **ClientCredentials** clase para establecer credenciales para Oracle E-Business Suite en un cliente de WCF.  
  
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
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>¿Cómo puedo proporcionan para el intercambio de datos más segura a través de límites de proceso?  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa. Dado que el adaptador está alojado en el proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Sin embargo, si la aplicación o servicio usado envía los mensajes que contienen información confidencial de la base de datos en un límite de proceso para otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno. [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]proporciona muchas opciones para ayudar a proteger los mensajes enviados entre los clientes y servicios. Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre los clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], vea "Seguridad de servicios y clientes" en [http://go.microsoft.com/fwlink/?LinkId=89725](http://go.microsoft.com/fwlink/?LinkId=89725). Para obtener más información general acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, vea "Seguridad de Windows Communication Foundation" en [http://go.microsoft.com/fwlink/?LinkId=89726](http://go.microsoft.com/fwlink/?LinkId=89726).  
  
## <a name="see-also"></a>Vea también  
 [Proteger las aplicaciones de Oracle EBS](secure-your-oracle-ebs-applications.md)