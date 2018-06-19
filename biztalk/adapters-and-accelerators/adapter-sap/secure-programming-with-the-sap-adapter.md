---
title: Programación segura con el adaptador SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, considerations when programming on the adapter
- security, secure data exchange
- security, setting credentials in code
ms.assetid: bd5da271-90f1-4a64-9138-a51048a16648
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2be84abdc7b645d9b2aaeea87e5ccabf0075e76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218028"
---
# <a name="secure-programming-with-the-sap-adapter"></a>Programación segura con el adaptador SAP
## <a name="how-do-i-protect-credentials-when-i-use-the-add-adapter-service-reference-visual-studio-plug-in"></a>¿Cómo proteger las credenciales cuando utilizo el agregar adaptador servicio referencia complemento de Visual Studio?  
 Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un cliente de WCF, debe proporcionar un nombre de usuario y una contraseña para el sistema SAP. Debe hacerlo desde el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Escribiendo el SAP credenciales desde el **seguridad** ficha en lugar de directamente en el **Uri** campo Asegúrese de lo siguiente:  
  
-   Las credenciales no se mostrará en el **Uri** campo de la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] cuadro de diálogo donde cualquier persona con acceso a la pantalla del equipo puede leer.  
  
-   Las credenciales no aparecerá en la configuración del archivo que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
 Para obtener más información acerca de cómo generar un cliente de WCF mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para el sistema SAP, consulte [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)  
  
## <a name="what-are-best-practices-for-setting-credentials-in-code"></a>¿Cuáles son las prácticas recomendadas para establecer credenciales en el código?  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]proporciona el **ClientCredentials** clase para ayudarle a configurar las credenciales que el objeto de una comunicación de cliente, como un **ChannelFactory**, utiliza para autenticarse con un servicio. Mediante el uso de la **ClientCredentials** (clase), se garantiza que WCF toma los mecanismos de autenticación se especifican en la pila de canales de ese objeto y aplica en el intercambio entre el cliente y el servicio.  
  
 Dado que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se hospeda en proceso con su aplicación que consume, que no es necesario usar el **ClientCredentials** clase para establecer credenciales en el cliente de los objetos de comunicación que utiliza la aplicación que consume. Sin embargo, se, considera recomendable hacerlo.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recomienda el uso de la **ClientCredentials** clase a través de la **AcceptCredentialsInUri** propiedad de enlace. Esta propiedad especifica si el adaptador aceptará el nombre de usuario y la contraseña para el sistema SAP en el URI de conexión. **AcceptCredentialsInUri** tiene como valor predeterminado **false**, lo que significa que el adaptador iniciará una excepción si el URI de conexión contiene credenciales. Puede establecer **AcceptCredentialsInUri** a **true** proporcione credenciales en el URI de conexión. De hecho, debe hacerlo en ciertos casos; Por ejemplo, cuando se especifica un URI de conexión para un punto de conexión de host de servicio o para un **IReplyChannel** en escenarios de entrada.  
  
 En el ejemplo siguiente se muestra cómo utilizar el **ClientCredentials** clase para establecer credenciales para el sistema SAP en un cliente de WCF.  
  
```  
SAPBinding binding = new SAPBinding();  
  
// Set endpoint address  
EndpointAddress endpointAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without");  
  
// Create client and set credentials  
RfcClient rfcClient = new RfcClient(binding, endpointAddress);  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
```  
  
## <a name="how-can-i-provide-for-more-secure-data-exchange-across-process-boundaries"></a>¿Cómo puedo proporcionan para el intercambio de datos más segura a través de límites de proceso?  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se hospeda en proceso con la aplicación o servicio que lo usa. Dado que el adaptador está alojado en el proceso con el consumidor, no es necesario para proporcionar seguridad en los mensajes intercambiados entre el consumidor y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Sin embargo, si la aplicación o servicio usado envía los mensajes que contienen información confidencial de la base de datos en un límite de proceso para otro servicio o cliente, debe tomar medidas para proporcionar una protección adecuada para estos datos en su entorno. [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]proporciona muchas opciones para ayudar a proteger los mensajes enviados entre los clientes y servicios. Para obtener más información sobre lo que ayuda a proteger los mensajes enviados entre los clientes y servicios en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)], consulte [protección de servicios y clientes](https://msdn.microsoft.com/library/ms734736.aspx). Para obtener más información general acerca de la seguridad que presenta [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proporciona, consulte [Windows Communication Foundation Security](https://msdn.microsoft.com/library/ms732362.aspx).  
  
## <a name="see-also"></a>Vea también  
[Prácticas recomendadas para proteger el adaptador SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[Proteger las aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   