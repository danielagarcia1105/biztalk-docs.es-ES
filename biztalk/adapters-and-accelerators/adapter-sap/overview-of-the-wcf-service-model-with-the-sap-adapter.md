---
title: Información general sobre el modelo de servicio WCF con el adaptador de SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, overview of using
ms.assetid: 02a4b43e-ade0-4dba-b8f6-074bca7cbe5c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd204cc7ad0b588a778fdbbbb6e4a61d884da231
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967491"
---
# <a name="overview-of-the-wcf-service-model-with-the-sap-adapter"></a>Información general sobre el modelo de servicio WCF con el adaptador de SAP
Cuando se consumen las operaciones que el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] superficies, el código actúa como un cliente o un servicio para el adaptador.  
  
 El código actúa como un cliente para invocar los siguientes tipos de operaciones en el sistema SAP:  
  
- Invocar una llamada a función remota (RFC).  
  
- Invocar un Transactional Remote Function Call (tRFC).  
  
- Invocar una aplicación de negocios (BAPI) de la interfaz de programación.  
  
- Enviar un documento intermedio (IDOC)  
  
  El código actúa como un servicio para recibir los siguientes tipos de operaciones:  
  
- Recibir una solicitud de cambio (servidor RFC)  
  
- Recibir un tRFC (tRFC server)  
  
- Recibir un IDOC.  
  
> [!NOTE]
>  Dado que BAPI es los métodos expuestos por el sistema SAP en los objetos de negocio ubicados en el repositorio de objeto de negocio (BOR), no puede recibir BAPI.  
  
 En el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio, el contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y WCF proporcionan herramientas que permiten generar esta interfaz para las operaciones de destino de los metadatos que expone el adaptador. Estas herramientas también crean una clase de cliente WCF que puede usarse para invocar las operaciones expuestas en la interfaz de servicio. Una aplicación cliente puede llamar a los métodos de la clase de cliente WCF para invocar operaciones en el adaptador. Para implementar un servicio para recibir operaciones desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], implemente la interfaz generada para la operación de destino.  
  
 Las siguientes secciones explican cómo usar el modelo de servicio WCF para crear código de cliente y servicio para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
## <a name="creating-a-wcf-client-and-invoking-operations-on-sap"></a>Crear a un cliente de WCF e invocar operaciones en SAP  
 Para usar el modelo de servicio WCF para invocar operaciones en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], primero debe generar una clase de cliente WCF para las operaciones de destino. A continuación, puede crear una instancia de esta clase, un cliente de WCF y llamar a sus métodos para llevar a cabo operaciones en el sistema SAP.  
  
#### <a name="to-invoke-operations-on-the-sap-adapter"></a>Para invocar operaciones en el adaptador de SAP  
  
1. Generar un código de clase y la aplicación auxiliar de cliente WCF. Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para generar una clase de cliente WCF dirigida a los artefactos del sistema SAP con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
2. Cree una instancia de cliente WCF mediante la especificación de un enlace de cliente. Especificar un enlace de cliente implica especificar el enlace y dirección de punto de conexión que va a usar el cliente de WCF. Puede hacerlo imperativamente en código o mediante declaración en configuración. Para obtener más información sobre cómo especificar un enlace de cliente, consulte [configurar un enlace para el sistema SAP de cliente](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md). El código siguiente crea a un cliente WCF que puede usarse para invocar una solicitud de cambio en el sistema SAP. También establece las credenciales para el sistema SAP. El cliente de WCF se inicializa a partir de la configuración.  
  
   ```  
   RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
   rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
   rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. Abra al cliente de WCF.  
  
   ```  
   rfcClient.Open();  
   ```  
  
4. Invocar métodos en el cliente de WCF que creó en el paso 2 para realizar operaciones en el sistema SAP. El código siguiente invoca el **SD_RFC_CUSTOMER_GET** método del cliente WCF para invocar la solicitud de cambio en el sistema SAP.  
  
   ```  
   microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[] customers =   
       new microsoft.lobservices.sap._2007._03.Types.Rfc.RFCCUST[0];  
  
   rfcClient.SD_RFC_CUSTOMER_GET(string.Empty, "AB*", ref customers);  
   ```  
  
5. Cierre al cliente WCF.  
  
   ```  
   rfcClient.Close();  
  
   ```  
  
## <a name="creating-and-implementing-a-wcf-service-by-using-the-sap-adapter"></a>Creación e implementación de un servicio WCF mediante el adaptador SAP  
 Para usar el modelo de servicio WCF para recibir operaciones desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], primero debe generar la interfaz de .NET (también denominada el contrato de servicio WCF) que representa el contrato de servicio expuesto por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para la operación. Para obtener más información acerca de cómo hacerlo, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
 A continuación, implementa un servicio de WCF mediante la implementación de la interfaz generada. Esta clase contiene la lógica de negocios para procesar la operación y devolver una respuesta al adaptador. A continuación, usar un host de servicio (**System.ServiceModel.ServiceHost**) para hospedar una instancia de este servicio.  
  
#### <a name="to-create-and-implement-a-wcf-service"></a>Para crear e implementar un servicio WCF  
  
1. Generar un clases auxiliares y el contrato del servicio WCF. Use el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o svcutil.exe para generar un contrato de servicio WCF (interfaz) dirigido a los artefactos del sistema SAP con el que desea trabajar. Para obtener más información sobre cómo generar un cliente de WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución SAP](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
2. Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1. Si se produce un error, los datos para la operación de procesamiento, el método que controla esa operación puede producir una excepción para devolver un error con el sistema SAP. en caso contrario, el método debe devolver una instancia de la clase de respuesta (generada) adecuada para la operación. Debe atributo la clase de servicio WCF como sigue:  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. Si ha usado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar la interfaz, puede implementar su lógica directamente en el método adecuado en generado **SAPBindingService** clase. Esta clase puede encontrarse en SAPBindingService.cs. El siguiente código subclases el **SAPBindingService** clase.  
  
      ```  
      [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single,UseSynchronizationContext = false)]  
      class RfcServerClass : SAPBindingNamespace.SAPBindingService  
      {  
          public override Z_RFC_MKD_ADDResponse Z_RFC_MKD_ADD(Z_RFC_MKD_ADDRequest request)  
          {  
              // If either parameter is null throw an exception   
              if (request.X == null || request.Y == null)  
                  throw new System.ArgumentNullException();  
  
              // Add the two operands  
              int result = (int) (request.X + request.Y);  
  
              return new Z_RFC_MKD_ADDResponse(result);  
          }  
      }  
      ```  
  
   2. Si utiliza svcutil.exe para generar la interfaz, debe crear una clase que implementa la interfaz e implementar la lógica en el appropriatemethod de esta clase.  
  
3. Cree una instancia del servicio WCF que creó en el paso 2.  
  
   ```  
   // create service instance  
   RfcServerClass rfcServerInstance = new RfcServerClass();  
   ```  
  
4. Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base. El URI de conexión base no puede contener userinfoparams o un query_string.  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("sap://a/YourSAPHost/00") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. Crear un **SAPBinding** y configurarlo para la operación estableciendo sus propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe establecer **AcceptCredentialsInUri** a **true**.  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   SAPBinding binding = new SAPBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
   ```  
  
6. Agregar un extremo de servicio al host de servicio. Para hacerlo:  
  
   -   Utilice el enlace creado en el paso 5.  
  
   -   Especifique un URI que contiene las credenciales y especifica una conexión de agente de escucha de conexión (puerta de enlace de servicio de puerta de enlace de SAP y el Id. de programa) en el query_string. Para obtener más información sobre el URI de conexión de SAP, consulte [crear la conexión del sistema SAP URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).  
  
   -   Especifique el contrato de servicio. Este es el nombre de la interfaz que representa el contrato de servicio WCF. Para las solicitudes de cambio, es "Rfc".  
  
   ```  
   // Add service endpoint   
   // NOTE: The contract for the service endpoint is "Rfc".  
   //       This is the generated WCF service contract (interface) -- see SAPBindingInterface.cs.  
   Uri serviceUri = new Uri("sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?ListenerGwServ=SAPGW00&ListenerGwHost=YourSapHost&ListenerProgramId=SAPAdapter");  
   srvHost.AddServiceEndpoint("Rfc", binding, serviceUri);  
   ```  
  
7. Para la operación de recepción desde el sistema SAP, abra el host de servicio. El servicio WCF se invocará siempre que el sistema SAP invoca la operación en el Id. de programa y el sistema especificado en el URI del servicio en el paso 6.  
  
   ```  
   // Open the service host to begin receiving the operation.  
   srvHost.Open();  
   ```  
  
8. Para dejar de recibir la operación, cierre el host de servicio.  
  
   > [!IMPORTANT]
   >  El adaptador seguirá recibiendo la operación hasta que se cierra el host de servicio. Siempre debería cerrar el host de servicio cuando ya no desea la operación de recepción.  
  
   ```  
   srvHost.Close();  
   ```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)