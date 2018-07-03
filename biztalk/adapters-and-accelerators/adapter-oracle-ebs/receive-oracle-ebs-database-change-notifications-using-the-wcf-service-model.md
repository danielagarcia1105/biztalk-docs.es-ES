---
title: Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362193f5-2586-480f-a62e-1ed5e4ef342c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02ab0b1be9862557319197f609c37bb151675e54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988853"
---
# <a name="receive-oracle-e-business-suite-database-change-notifications-using-the-wcf-service-model"></a>Recibir notificaciones de cambio de base de datos de Oracle E-Business Suite mediante el modelo de servicio WCF
En este tema se muestra cómo configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de notificación de consulta de una base de datos de Oracle. Para demostrar las notificaciones, considere la posibilidad de una tabla, ACCOUNTACTIVITY, con una columna "Procesados". Cuando se inserta un nuevo registro a esta tabla, el valor de la columna de estado se establece en "n". Puede configurar el adaptador para recibir notificaciones mediante el registro para recibir notificaciones mediante una instrucción SQL que recupera todos los registros que tienen la columna "Procesados" como "n". Puede hacerlo mediante la especificación de la instrucción SQL para la **NotificationStatement** enlaza la propiedad. Una vez que el cliente del adaptador recibe la notificación, puede contener la lógica para realizar las tareas subsiguientes en la base de datos de Oracle. En este ejemplo, por simplicidad, el cliente del adaptador enumera todos los registros en la tabla que tienen la columna "Procesados" como "n".  
  
## <a name="configuring-notifications-with-the-oracle-e-business-adapter-binding-properties"></a>Configuración de notificaciones con el adaptador para Oracle E-Business propiedades de enlace  
 La tabla siguiente resume la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de Oracle E-Business Suite. Debe especificar estas propiedades de enlace al ejecutar la aplicación de .NET para recibir notificaciones.  
  
|Propiedad de enlace|Descripción|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica la operación de entrada que desea realizar. Para recibir mensajes de notificación, establezca esta opción en **notificación**.|  
|**NotificationPort**|Especifica el número de puerto que debe abrir ODP.NET para realizar escuchas para la notificación de cambio de base de datos de base de datos de Oracle.|  
|**NotificationStatement**|Especifica la instrucción Select que se usa para registrar las notificaciones de consulta. El adaptador obtiene un mensaje de notificación solo cuando el conjunto de resultados para que los cambios de la instrucción Select especificada.|  
|**NotifyOnListenerStart**|Especifica si el adaptador envía una notificación a los clientes del adaptador cuando se inicia el agente de escucha.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir notificaciones de Oracle E-Business Suite, lea el resto de este tema.  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a>Configuración de notificaciones mediante el modelo de servicio WCF  
 Para recibir las notificaciones mediante el modelo de servicio WCF, debe:  
  
- Generar un contrato de servicio WCF (interfaz) para el **notificación** operación desde los metadatos expuestos por el adaptador. Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
- Generar un cliente WCF para la **seleccione** operación en la tabla ACCOUNTACTIVITY. Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
- Implementar un servicio WCF desde esta interfaz.  
  
- Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema recibe la notificación de la tabla ACCOUNTACTIVITY. Se proporciona un script para generar la tabla con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Un ejemplo, **Notification_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
## <a name="the-wcf-service-contract-and-class"></a>El contrato de servicio WCF y la clase  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y la compatibilidad con las clases para el **notificación** operación. Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
### <a name="the-wcf-service-contract-interface"></a>El contrato de servicio WCF (interfaz)  
 El código siguiente muestra el contrato de servicio WCF (interfaz) generado para el **notificación** operación.  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="Notification_")]  
public interface Notification_ {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a>Los contratos de mensaje  
 Siguiente es el contrato de mensaje para la operación de notificación.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=1)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=2)]  
    public string[] ResourceNames;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=3)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/Notification/", Order=4)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(schemas.microsoft.com.OracleEBS._2008._05.Notification.NotificationDetails[] Details, string Info, string[] ResourceNames, string Source, string Type) {  
        this.Details = Details;  
        this.Info = Info;  
        this.ResourceNames = ResourceNames;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>Clase de servicio WCF  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz). El nombre del archivo es OracleEBSBindingService.cs. Puede insertar la lógica para procesar el **notificación** operación directamente en esta clase. El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : Notification_ {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/Notification/) of message Notification   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a>Recibir notificaciones de consulta mediante el modelo de servicio WCF  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir notificaciones de consulta mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
#### <a name="to-receive-query-notifications"></a>Para recibir notificaciones de consulta  
  
1. Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un cliente WCF para **seleccione** operación en el **ACCOUNTACTIVITY** tabla. Usará a este cliente para realizar las operaciones Select después de recibir un mensaje de notificación. Agregue una nueva clase, TableOperation.cs, al proyecto y agregue el siguiente fragmento de código para llevar a cabo una operación de selección.  
  
   ```  
   using System;  
   using System.Collections.Generic;  
   using System.Linq;  
   using System.Text;  
  
   namespace Notification_ServiceModel  
   {  
       class TableOperation  
       {  
           public void TableOp()  
           {  
               //////////////////////////////////////////////////////////////////////  
               // CREATING THE CLIENT AND SETTING CLIENT CREDENTIALS  
               //////////////////////////////////////////////////////////////////////  
  
               Tables_APPS_ACCOUNTACTIVITYClient client = new Tables_APPS_ACCOUNTACTIVITYClient();  
               client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
               client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
               ////////////////////////////////////////////////////////////////////  
               // OPENING THE CLIENT  
               //////////////////////////////////////////////////////////////////////  
               try  
               {  
                   Console.WriteLine("Opening the client ...");  
                   client.Open();  
               }  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               ////////////////////////////////////////////////////////////////////////////////////////  
               // SELECTING THE LAST INSERTED VALUES  
               ////////////////////////////////////////////////////////////////////////////////////////  
               Console.WriteLine("The application will now select the last inserted record");  
  
               schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.ACCOUNTACTIVITY.SelectRecord[] selectRecords;  
  
               try  
               {  
                   selectRecords = client.Select("*", "WHERE PROCESSED = 'n'");  
               }  
               catch (Exception ex)  
               {  
                   Console.WriteLine("Exception: " + ex.Message);  
                   throw;  
               }  
  
               Console.WriteLine("The details of the newly added records are:");  
               Console.WriteLine("********************************************");  
               for (int i = 0; i < selectRecords.Length; i++)  
               {  
                   Console.WriteLine("Transaction ID   : " + selectRecords[i].TID);  
                   Console.WriteLine("Account ID       : " + selectRecords[i].ACCOUNT);  
                   Console.WriteLine("Processed Status : " + selectRecords[i].PROCESSED);  
                   Console.WriteLine();  
               }  
               Console.WriteLine("********************************************");  
           }  
       }  
   }  
  
   ```  
  
2. Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y clases auxiliares para el **notificación** operación.  
  
    Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md). También puede especificar las propiedades de enlace al generar las clases auxiliares y de contrato de servicio. Esto garantiza que están establecidas correctamente en el archivo de configuración generado.  
  
3. Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 2. El **notificación** método de esta clase puede producir una excepción para anular la operación, si se produce un error de procesamiento de los datos recibidos desde el **notificación** operación; en caso contrario, el método no no devuelve nada. Debe atributo la clase de servicio WCF como sigue:  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
    Dentro de la **notificación** método, puede implementar la lógica de aplicación directamente. Esta clase puede encontrarse en OracleEBSBindingService.cs. Este código en este ejemplo Sub clases el **OracleEBSBindingService** clase. En este código, recibe el mensaje de notificación se escribe en la consola. Además, el **TableOp** método dentro de la **TableOperation** clase se invoca para llevar a cabo la operación de selección.  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
   public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void Notification(Notification request)  
       {  
           Console.WriteLine("\nNew Notification Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine(request.Info);  
           Console.WriteLine(request.Source);  
           Console.WriteLine(request.Type);  
           Console.WriteLine("*************************************************");  
  
           TableOperation Ops = new TableOperation();  
           Ops.TableOp();  
  
       }  
   }  
   ```  
  
4. Debe implementar la siguiente clase para pasar las credenciales para Oracle E-Business Suite. En la última parte de la aplicación, se creará instancias de esta clase para pasar las credenciales.  
  
   ```  
   class NotificationCredentials : ClientCredentials, IServiceBehavior  
   {  
       public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
       {  
           bindingParameters.Add(this);  
       }  
  
       public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
       { }  
  
       public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
       { }  
  
       protected override ClientCredentials CloneCore()  
       {  
           ClientCredentials clone = new NotificationCredentials();  
           clone.UserName.UserName = this.UserName.UserName;  
           clone.UserName.Password = this.UserName.Password;  
           return clone;  
       }  
   }  
   ```  
  
5. Crear un **OracleEBSBinding** y configurar el adaptador para recibir notificaciones de consulta mediante la especificación de las propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe especificar el **InboundOperationType** y **NotificationStatement** propiedades de enlace.  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Notification;  
   binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
   binding.NotifyOnListenerStart = true;  
   binding.NotificationPort = 10;  
   ```  
  
   > [!IMPORTANT]
   >  El valor de la **NotificationPort** enlaza la propiedad debe establecerse en el mismo número de puerto que debe haber agregado a la lista de excepciones de Firewall de Windows. Para obtener instrucciones sobre cómo agregar puertos a la lista de excepciones de Firewall de Windows, consulte [ http://go.microsoft.com/fwlink/?LinkID=196959 ](http://go.microsoft.com/fwlink/?LinkID=196959).  
  
   > [!IMPORTANT]
   >  Si no establece la **NotificationPort** propiedad de enlace, el adaptador asumirá el valor predeterminado de -1 para esta propiedad de enlace. En tal caso, tendrá que deshabilitar completamente el Firewall de Windows para recibir mensajes de notificación.  
  
6. Especifique las credenciales de Oracle E-Business Suite creando el **NotificationCredentials** clase creada en el paso 4.  
  
   ```  
   NotificationCredentials credentials = new NotificationCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  
  
7. Cree una instancia del servicio WCF que creó en el paso 3.  
  
   ```  
   // create service instance  
   NotificationService service = new NotificationService();  
   ```  
  
8. Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base. También debe especificar las credenciales aquí.  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  
  
   ```  
  
9. Agregar un extremo de servicio al host de servicio. Para hacerlo:  
  
   - Utilice el enlace creado en el paso 5.  
  
   - Especifique un URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.  
  
   - Especifique el contrato como "Notification_".  
  
     ```  
     // Add service endpoint: be sure to specify Notification_ as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  
     serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
     ```  
  
10. Para recibir el mensaje de notificación, abra el host de servicio.  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. Para dejar de recibir notificaciones, cierre el host de servicio.  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una aplicación .NET para recibir mensajes de notificación para la tabla ACCOUNTACTIVITY.  
  
> [!NOTE]
>  El fragmento de código siguiente crea una instancia de un **TableOperation.cs** clase e invoca el **TableOp** método. La clase y el método se describen en el paso 1.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.OracleEBS;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
  
        }  
    }  
  
    class NotificationCredentials : ClientCredentials, IServiceBehavior  
    {  
        public void AddBindingParameters(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase, Collection<ServiceEndpoint> endpoints, BindingParameterCollection bindingParameters)  
        {  
            bindingParameters.Add(this);  
        }  
  
        public void ApplyDispatchBehavior(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        public void Validate(ServiceDescription serviceDescription, ServiceHostBase serviceHostBase)  
        { }  
  
        protected override ClientCredentials CloneCore()  
        {  
            ClientCredentials clone = new NotificationCredentials();  
            clone.UserName.UserName = this.UserName.UserName;  
            clone.UserName.Password = this.UserName.Password;  
            return clone;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost serviceHost = null;  
            try  
            {  
                Console.WriteLine("Sample started...");  
                Console.WriteLine("Press any key to start receiving notifications...");  
                Console.ReadLine();  
  
                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT TID,ACCOUNT,PROCESSED FROM APPS.ACCOUNTACTIVITY WHERE PROCESSED = 'n'";  
                binding.NotifyOnListenerStart = true;  
                binding.NotificationPort = 10;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("Notification_", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Waiting for notification...");  
  
                Console.WriteLine("\nHit <RETURN> to stop receiving notification");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (serviceHost.State == CommunicationState.Opened)  
                    serviceHost.Close();  
                else  
                    serviceHost.Abort();  
            }  
  
        }  
    }  
}  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)