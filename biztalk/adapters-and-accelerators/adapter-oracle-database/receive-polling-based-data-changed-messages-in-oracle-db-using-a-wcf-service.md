---
title: Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving polling-based messages
- how to, receive polling-based message
- polling-based messages, receiving by using the WCF service model
ms.assetid: 0324e8bf-d9d1-46f5-b896-b9fc8e61d514
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda98a1600df28fab476114e697cd47e24316251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012605"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-service-model"></a>Recibir mensajes de cambio de datos basados en sondeo de base de datos de Oracle mediante el modelo de servicio de WCF
Puede configurar el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] recibir datos basados en sondeos cambiado mensajes con respecto a una tabla de Oracle o la vista. Para recibir mensajes de cambio de datos, el adaptador ejecuta periódicamente una consulta SQL en una tabla de Oracle o la vista seguido de un bloque de código PL/SQL opcional. A continuación, se devuelven los resultados de la consulta SQL mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a la aplicación como un conjunto en una operación POLLINGSTMT entrante fuertemente tipada de resultados. Para obtener más información sobre el mecanismo utilizado para configurar y realizar el sondeo de Oracle database mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md). Se recomienda encarecidamente que lea este tema antes de continuar.  
  
 Para recibir la operación POLLINGSTMT cuando se usa el modelo de servicio WCF, debe:  
  
- Generar un contrato de servicio WCF (interfaz) para la operación POLLINGSTMT desde los metadatos expuestos por el adaptador. Para ello, usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o ServiceModel Metadata Utility Tool (svcutil.exe).  
  
- Implementar un servicio WCF desde esta interfaz.  
  
- Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  
  
  Los temas de esta sección proporcionan información y procedimientos que le ayudarán a realizar el sondeo en las tablas de base de datos de Oracle y las vistas en el modelo de servicio WCF.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos en este tema usan la tabla /SCOTT/ACCOUNTACTIVITY y la función /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY. Una secuencia de comandos para generar estos artefactos se suministra con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a>Configuración de sondeo en el modelo de servicio WCF  
 Configurar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para realizar el sondeo en vistas y tablas de base de datos de Oracle estableciendo las propiedades de enlace y una propiedad de conexión opcional (parámetro). Algunas de estas propiedades son obligatorias, y algunos, tener un efecto, deben establecerse en tiempo de diseño y en tiempo de ejecución.  
  
- En tiempo de diseño, se establecen los parámetros de conexión y las propiedades de enlace cuando se conecta a la base de datos de Oracle para generar un contrato de servicio WCF.  
  
- En tiempo de ejecución definir propiedades de enlace en el objeto OracleDBBinding que usó para crear el host del servicio. Establece el parámetro de conexión al agregar un agente de escucha del servicio al host de servicio.  
  
  En la lista siguiente proporciona una breve descripción de las propiedades de enlace y los parámetros de conexión utilizados para configurar sondeo:  
  
- El **PollingStatement** enlaza la propiedad. Debe establecer esta propiedad de enlace en tiempo de diseño y en tiempo de ejecución.  
  
- Propiedades de enlace opcional. Estos solo deben establecerse en tiempo de ejecución.  
  
- El **AcceptCredentialsInUri** enlaza la propiedad. Debe establecer esta propiedad de enlace en **true** durante el tiempo de ejecución si desea habilitar las credenciales en el URI de conexión. El nombre de usuario y la contraseña deben estar presentes en el URI de conexión cuando se agrega un extremo de servicio al host de servicio.  
  
- El **PollingId** parámetro de cadena en el URI de conexión de consulta. Si desea cambiar el espacio de nombres de la operación POLLINGSTMT, debe establecer esta propiedad de conexión en tiempo de diseño y en tiempo de ejecución.  
  
  Para obtener una descripción completa de las propiedades de enlace y los parámetros de conexión que se usa para configurar el sondeo, consulte [recibir mensajes de cambio de datos basados en sondeos en el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).  
  
## <a name="the-wcf-service-contract-and-class"></a>El contrato de servicio WCF y la clase  
 Usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para crear un WCF del servicio de contrato (interfaz) y clases auxiliares para la operación POLLINGSTMT.  
  
 Cuando se conecta a la base de datos de Oracle con cualquiera de estas herramientas para generar un contrato de servicio para la operación POLLINGSTMT:  
  
- Debe especificar el **PollingStatement** enlaza la propiedad. El adaptador utiliza la instrucción SELECT en esta propiedad de enlace para generar los metadatos correctos para el conjunto de resultados fuertemente tipado devuelto por la operación POLLINGSTMT.  
  
- También puede especificar un parámetro PollingId en el URI de conexión. El adaptador utiliza este parámetro para generar el espacio de nombres para la operación POLLINGSTMT.  
  
  En los ejemplos siguientes:  
  
- **PollingStatement** está establecido en "SELECT * desde ACCOUNTACTIVITY FOR UPDATE".  
  
- **PollingId** está establecido en "AcctActivity".  
  
### <a name="the-wcf-service-contract-interface"></a>El contrato de servicio WCF (interfaz)  
 El código siguiente muestra el contrato de servicio WCF (interfaz) generado para la operación POLLINGSTMT.  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="POLLINGSTMT_OperationGroup")]  
public interface POLLINGSTMT_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)  
    // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT")]  
    void POLLINGSTMT(POLLINGSTMT request);  
}  
```  
  
### <a name="the-message-contracts"></a>Los contratos de mensaje  
 El espacio de nombres de contrato de mensaje se modifica mediante el parámetro PollingId en el URI de conexión. El mensaje de solicitud devuelve un conjunto de registros fuertemente tipado.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="POLLINGSTMT", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", IsWrapped=true)]  
public partial class POLLINGSTMT {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD;  
  
    public POLLINGSTMT() {  
    }  
  
    public POLLINGSTMT(microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD) {  
        this.POLLINGSTMTRECORD = POLLINGSTMTRECORD;  
    }  
}  
```  
  
### <a name="the-data-contract-namespace"></a>El Namespace de contrato de datos  
 Un contrato de datos es un acuerdo formal entre un servicio y un cliente que abstractamente describe los datos que se van a intercambiar. Es decir, con el fin de comunicarse, el cliente y el servicio no debe compartir los mismos tipos, los mismos contratos de datos.  
  
 Mensajes de cambio en el caso de datos, el espacio de nombres de contrato de datos también se ha modificado por el parámetro PollingId (si se especifica) en el URI de conexión. El contrato de datos se compone de una clase que representa un registro en el conjunto de resultados de consulta fuertemente tipada. En este ejemplo, se omiten los detalles de la definición de clase. La clase contiene propiedades que representan las columnas del conjunto de resultados.  
  
 En el ejemplo siguiente, se usa el PollingId "AcctActivity".  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity {  
    using System.Runtime.Serialization;  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute(Name="POLLINGSTMTRECORD", Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity")]  
    public partial class POLLINGSTMTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
     }  
}  
```  
  
### <a name="wcf-service-class"></a>Clase de servicio WCF  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz). El nombre del archivo es OracleDBBindingService.cs. Puede insertar la lógica para procesar la operación POLLINGSTMT directamente en esta clase. Si utiliza svcutil.exe para generar la interfaz de contrato de servicio, debe implementar esta clase. El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : POLLINGSTMT_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)   
        // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void POLLINGSTMT(POLLINGSTMT request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-the-pollingstmt-operation"></a>Recepción de la operación POLLINGSTMT  
  
#### <a name="to-receive-polling-data-from-the-oracle-database-adapter"></a>Para recibir datos de sondeo del adaptador de base de datos de Oracle  
  
1. Use el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o svcutil.exe para generar un WCF service contrato (interfaz) y clases auxiliares para la operación POLLINGSTMT. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md). Como mínimo, debe establecer el **PollingStatement** enlaza la propiedad cuando se conecta al adaptador. También puede especificar un parámetro PollingId en el URI de conexión. Si usas el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], debe establecer todos los parámetros de enlace necesarios para la configuración. Esto garantiza que están establecidas correctamente en el archivo de configuración generado.  
  
2. Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1. El método POLLINGSTMT de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la operación POLLINGSTMT; en caso contrario, el método no devuelve nada. Debe atributo la clase de servicio WCF como sigue:  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. Si ha usado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar la interfaz, puede implementar la lógica directamente en el **POLLINGSTMT** método generado **OracleDBBindingService** clase. Esta clase puede encontrarse en OracleDBBindingService.cs. Este código en este ejemplo Sub clases el **OracleDBBindingService** clase.  
  
      ```  
      [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
      public class PollingStmtService : OracleDBBindingService  
      {  
          public override void POLLINGSTMT(POLLINGSTMT request)  
          {  
              Console.WriteLine("\nNew Polling Records Received");  
              Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
              for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
              {  
                  Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                      request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                      request.POLLINGSTMTRECORD[i].AMOUNT,  
                                      request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                      request.POLLINGSTMTRECORD[i].DESCRIPTION);  
              }  
          }  
      }  
      ```  
  
   2. Si utiliza svcutil.exe para generar la interfaz, debe crear un servicio WCF que implementa la interfaz e implementar la lógica en el **POLLINGSTMT** método de esta clase.  
  
3. Cree una instancia del servicio WCF que creó en el paso 2.  
  
   ```  
   // create service instance  
   PollingStmtService pollingInstance = new PollingStmtService();  
   ```  
  
4. Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base. El URI de conexión base no puede contener userinfoparams o un query_string.  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracledb://Adapter") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. Crear un **OracleDBBinding** y configurar la operación de sondeo estableciendo sus propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe especificar la instrucción de sondeo y el intervalo de sondeo. En este ejemplo, especifique las credenciales como parte del URI por lo que debe establecer también la **AcceptCredentialsInUri** a **true**.  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   OracleDBBinding binding = new OracleDBBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
  
   // Same as statement specified in Configure Adapter dialog box  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
   // Be sure to set the interval long enough to complete processing before  
   // the next poll  
   binding.PollingInterval = 15;  
   // Polling is transactional; be sure to set an adequate isolation level   
   // for your environment  
   binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
   ```  
  
6. Agregar un extremo de servicio al host de servicio. Para hacerlo:  
  
   -   Utilice el enlace creado en el paso 5.  
  
   -   Especifique un URI que contiene las credenciales de conexión y, si es necesario, un PollingId.  
  
   -   Especifique el contrato como "POLLINGSTMT_OperationGroup".  
  
   ```  
   // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
   Uri serviceUri = new Uri("oracledb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
   srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
   ```  
  
7. Para recibir datos de sondeo, abra el host de servicio. El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.  
  
   ```  
   // Open the service host to begin polling  
   srvHost.Open();  
   ```  
  
8. Para finalizar el sondeo, cierre el host de servicio.  
  
   > [!IMPORTANT]
   >  El adaptador seguirá sondeando hasta que se cierra el host de servicio.  
  
   ```  
   srvHost.Close();  
   ```  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una consulta de sondeo que se ejecuta en la tabla ACCOUNTACTIVITY/SCOTT /. La instrucción de sondeo posterior a la invoca una función de Oracle que mueve los registros procesados a /SCOTT/ACCOUNTHISTORY de otra tabla. El espacio de nombres de la operación POLLINGSTMT se modifica estableciendo el parámetro PollingId "AccountActivity" en el URI de conexión. En este ejemplo, se crea el servicio WCF para la operación POLLINGSTMT subclasificando generado **OracleDBBindingService** clase; sin embargo, puede implementar la lógica directamente en la clase generada.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add these three references to use the Oracle adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
using microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity;  
using OracleDBBindingNamespace;  
  
namespace OraclePollingSM  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingStmtService : OracleDBBindingService  
    {  
        public override void POLLINGSTMT(POLLINGSTMT request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
            for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                    request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                    request.POLLINGSTMTRECORD[i].AMOUNT,  
                                    request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                    request.POLLINGSTMTRECORD[i].DESCRIPTION);  
  
            }  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
         }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost srvHost = null;  
  
            // This URI is used to specify the address for the ServiceEndpoint  
            // It must contain credentials and the PollingId (if any) that was used to generate  
            // the WCF service callback interface  
            Uri serviceUri = new Uri("OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
  
            // This URI is used to initialize the ServiceHost. It cannot contain  
            // userinfoparms (credentials) or a query_string (PollingId); otherwise,  
            // an exception is thrown when the ServiceHost is initialized.  
            Uri[] baseUri = new Uri[] { new Uri("OracleDb://Adapter") };  
  
            Console.WriteLine("Sample started, initializing service host -- please wait");  
  
            // create an instanc of the WCF service callback class  
            PollingStmtService pollingInstance = new PollingStmtService();  
  
            try  
            {  
                // Create a ServiceHost with the service callback instance and a base URI (address)  
                srvHost = new ServiceHost(pollingInstance, baseUri);  
  
                // Create and configure a binding for the service endpoint. Note: binding  
                // parameters are set here for clarity but these are already set in the  
                // generated configuration file  
                //  
                // The following properties are set  
                //    AcceptCredentialsInUri (true) to enable credentials in the connection URI for AddServiceEndpoint  
                //    PollingStatement  
                //    PostPollStatement calls PROCESS_ACTIVITY on Oracle. This procedure moves the queried records to  
                //                      the ACCOUNTHISTORY table  
                //    PollingInterval (15 seconds)  
                //    TransactionIsolationLevel   
  
                OracleDBBinding binding = new OracleDBBinding();  
  
                // The Credentials are included in the Connection Uri so set this property true  
                binding.AcceptCredentialsInUri = true;  
  
                // Same as statement specified in Configure Adapter dialog box  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Be sure to set the interval long enough to complete processing before  
                // the next poll  
                binding.PollingInterval = 15;  
  
                // Polling is transactional, be sure to set an adequate isolation level   
                // for your environment  
                binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
  
                // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
                srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
  
                Console.WriteLine("Opening the service host");  
                // Open the service host to begin polling  
                srvHost.Open();  
  
                // Wait to receive request  
                Console.WriteLine("\nPolling started. Returned records will be written to the console.");  
                Console.WriteLine("Hit <RETURN> to stop polling");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an Oracle Error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (srvHost.State == CommunicationState.Opened)  
                    srvHost.Close();  
                else  
                    srvHost.Abort();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)