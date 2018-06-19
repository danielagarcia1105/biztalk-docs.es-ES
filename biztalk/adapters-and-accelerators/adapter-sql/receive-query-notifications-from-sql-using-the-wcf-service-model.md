---
title: Recibir notificaciones de consulta de SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9def31-3c5a-4326-b798-31bde0ff2568
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b21d2123b646a02669a9da65efc5069931e64c69
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964090"
---
# <a name="receive-query-notifications-from-sql-using-the-wcf-service-model"></a>Recibir notificaciones de consulta de SQL mediante el modelo de servicio de WCF
Este tema muestra cómo configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de notificación de consulta de una base de datos de SQL Server. Para mostrar las notificaciones, considere la posibilidad de una tabla de empleados, con una columna de "Status". Cuando se inserta un nuevo registro en esta tabla, el valor de la columna de estado se establece en 0. Puede configurar el adaptador para recibir notificaciones por registrarse para recibir notificaciones mediante una instrucción SQL que recupera todos los registros que tienen la columna de estado como "0". Puede hacerlo mediante la especificación de la instrucción SQL para la **NotificationStatement** propiedad de enlace. Una vez que el cliente de adaptador recibe la notificación, puede contener la lógica para realizar las tareas siguientes en la base de datos de SQL Server. En este ejemplo, por simplicidad, el cliente de adaptador enumera todos los registros en la tabla que tienen la columna de estado como "0".  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) tema antes de empezar a desarrollar la aplicación .  
  
## <a name="configuring-notifications-with-the-sql-adapter-binding-properties"></a>Configuración de notificaciones con el adaptador SQL propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades de enlace que se utiliza para configurar la recepción de notificaciones de SQL Server. Debe especificar estas propiedades de enlace al ejecutar la aplicación .NET para recibir las notificaciones de una base de datos de SQL Server.  
  
|Propiedad de enlace|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica la operación de entrada que se desea realizar. Para recibir mensajes de notificación, establezca esta propiedad en **notificación**.|  
|**NotificationStatement**|Especifica la instrucción SQL (SELECT o EXEC \< *procedimiento almacenado*\>) usa para registrar las notificaciones de consulta. El adaptador obtiene un mensaje de notificación de SQL Server sólo cuando el conjunto de resultados para que los cambios de instrucción SQL especificados.|  
|**NotifyOnListenerStart**|Especifica si el adaptador envía una notificación a los clientes de adaptador cuando se inicia el agente de escucha.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir notificaciones de SQL Server, seguir leyendo.  
  
## <a name="configuring-notifications-using-the-wcf-service-model"></a>Configuración de notificaciones mediante el modelo de servicio WCF  
 Para recibir las notificaciones mediante el modelo de servicio WCF, debe:  
  
1.  Generar un contrato de servicio WCF (interfaz) para la **notificación** operación desde los metadatos expuestos por el adaptador. Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
2.  Generar un cliente WCF para la **seleccione** operación en la tabla de empleados. Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
3.  Implementar un servicio WCF de esta interfaz.  
  
4.  Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 Los ejemplos de este tema reciban una notificación para la tabla Employee. Una secuencia de comandos para generar la tabla se suministra con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md). Obtener un ejemplo, **Notification_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-service-contract-and-class"></a>El contrato de servicio WCF y la clase  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **notificación** operación. Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
### <a name="the-wcf-service-contract-interface"></a>El contrato de servicio WCF (interfaz)  
 El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **notificación** operación.  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="NotificationOperation")]  
public interface NotificationOperation {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/) of message  
    // Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="Notification")]  
    void Notification(Notification request);  
}  
```  
  
### <a name="the-message-contracts"></a>Los contratos de mensaje  
 Aquí te mostramos el contrato de mensaje para la operación de notificación.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Notification", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", IsWrapped=true)]  
public partial class Notification {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=0)]  
    public string Info;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=1)]  
    public string Source;  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/Notification/", Order=2)]  
    public string Type;  
  
    public Notification() {  
    }  
  
    public Notification(string Info, string Source, string Type) {  
        this.Info = Info;  
        this.Source = Source;  
        this.Type = Type;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>Clase de servicio WCF  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz). El nombre del archivo es SqlAdapterBindingService.cs. Puede insertar la lógica para procesar el **notificación** operación directamente en esta clase. El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
```  
namespace SqlAdapterBindingNamespace {  
  
    public class SqlAdapterBindingService : NotificationOperation {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/Notification/)   
        // of message Notification does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void Notification(Notification request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-query-notifications-using-wcf-service-model"></a>Recibir notificaciones de consulta mediante el modelo de servicio WCF  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir las notificaciones de consulta mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
#### <a name="to-receive-query-notifications"></a>Para recibir las notificaciones de consulta  
  
1.  Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un cliente WCF para **seleccione** operación en el **empleado** tabla. Usará a este cliente para realizar las operaciones Select después de recibir un mensaje de notificación. Agregue una nueva clase, TableOperation.cs al proyecto y agregue el siguiente fragmento de código para llevar a cabo una operación de selección.  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
  
    namespace Notification_ServiceModel  
    {  
        public class TableOperation  
        {  
            public void TableOp()  
            {  
                ///////////////////////////////////////////////////////////////////////  
                // CREATING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
                TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
  
                client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
                client.ClientCredentials.UserName.Password = "<Enter password here>";  
  
                ///////////////////////////////////////////////////////////////////////  
                // OPENING THE CLIENT  
                ///////////////////////////////////////////////////////////////////////  
  
                try  
                {  
                    Console.WriteLine("Opening Client...");  
                    client.Open();  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                ///////////////////////////////////////////////////////////////////////  
                // SELECTING THE LAST INSERTED RECORD FROM THE TABLE  
                ///////////////////////////////////////////////////////////////////////  
                schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
                try  
                {  
                    selectRecords = client.Select("*", "where Status=0");  
                }  
  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Exception: " + ex.Message);  
                    throw;  
                }  
  
                Console.WriteLine("The details of the newly added employee are:");  
                Console.WriteLine("********************************************");  
                for (int i = 0; i < selectRecords.Length; i++)  
                {  
                    Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
                    Console.WriteLine("Employee Designation: " + selectRecords[i].Designation);  
                    Console.WriteLine("Employee Status    : " + selectRecords[i].Status);  
                    Console.WriteLine();  
                }  
                Console.WriteLine("********************************************");  
  
    ```  
  
    > [!IMPORTANT]
    >  Dado que este fragmento de código realiza operaciones en la tabla de empleados que contiene una columna UDT Point, asegúrese de que colocar la DLL de UDT en la carpeta \bin\Debug del proyecto mientras se ejecuta la aplicación.  
  
2.  Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **notificación** operación.  
  
     Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md). También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio. Esto garantiza que están establecidas correctamente en el archivo de configuración generado.  
  
3.  Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 2. El **notificación** método de esta clase puede producir una excepción para anular la operación, si se produce un error de procesamiento de los datos recibidos de la **notificación** operación; en caso contrario, el método no no devuelve nada. La clase de servicio WCF debe atributo como se indica a continuación:  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     En el **notificación** método, puede implementar la lógica de aplicación directamente. Esta clase se puede encontrar en SqlAdapterBindingService.cs. Este código de este ejemplo Sub-clases el **SqlAdapterBindingService** clase. En este código, el mensaje de notificación recibido se escribe en la consola. Además, el **TableOp** método dentro de la **TableOperation** se invoca para llevar a cabo la operación de selección.  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void Notification(Notification request)  
        {  
            Console.WriteLine("\nNew Notification Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine(request.Info);  
            Console.WriteLine(request.Source);  
            Console.WriteLine(request.Type);  
            Console.WriteLine("*************************************************");  
  
            // Invoke th TableOp method in the TableOperation class  
            TableOperation Ops = new TableOperation();  
            Ops.TableOp();  
        }  
    }  
    ```  
  
4.  Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no acepta credenciales como parte del URI de conexión, debe implementar la clase siguiente para pasar las credenciales de la base de datos de SQL Server. En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales de SQL Server.  
  
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
  
5.  Crear un **SqlAdapterBinding** y configurar el adaptador para recibir las notificaciones de consulta mediante la especificación de las propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe especificar el **InboundOperationType** y **NotificationStatement** propiedades de enlace.  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    binding.InboundOperationType = InboundOperation.Notification;  
    binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
    binding.NotifyOnListenerStart = true;  
    ```  
  
6.  Especifique las credenciales de base de datos de SQL Server creando el **NotificationCredentials** clase creada en el paso 4.  
  
    ```  
    NotificationCredentials credentials = new NotificationCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
7.  Cree una instancia del servicio WCF que creó en el paso 3.  
  
    ```  
    // create service instance  
    NotificationService service = new NotificationService();  
    ```  
  
8.  Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base. También debe especificar las credenciales aquí.  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
9. Agregar un extremo de servicio al host de servicio. Para hacerlo:  
  
    -   Utilice el enlace creado en el paso 5.  
  
    -   Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.  
  
    -   Especifique el contrato como "NotificationOperation".  
  
    ```  
    // Add service endpoint: be sure to specify NotificationOperation as the contract  
    Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
    serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
    ```  
  
10. Para recibir el mensaje de notificación, abra el host del servicio.  
  
    ```  
    // Open the service host to begin receiving notifications  
    serviceHost.Open();  
    ```  
  
11. Para dejar de recibir notificaciones, cierre el host del servicio.  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una aplicación .NET para recibir mensajes de notificación para la tabla Employee.  
  
> [!NOTE]
>  El fragmento de código siguiente crea un **TableOperation.cs** clase e invoca el **TableOp** método. La clase y el método se describen en el paso 1.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
using Microsoft.Adapters.Sql;  
using Microsoft.ServiceModel.Channels;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Collections.ObjectModel;  
  
namespace Notification_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class NotificationService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
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
                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Notification;  
                binding.NotificationStatement = "SELECT Employee_ID, Name FROM dbo.Employee WHERE Status=0";  
                binding.NotifyOnListenerStart = true;  
  
                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId (if any) that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
  
                // This URI is used to initialize the ServiceHost. It cannot contain  
                // a query_string (InboundID); otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
  
                NotificationCredentials credentials = new NotificationCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  
  
                Console.WriteLine("Opening service host...");  
                NotificationService service = new NotificationService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("NotificationOperation", binding, ConnectionUri);  
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
  
                // If there is an error it will be specified in the inner exception   
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop receiving notifications  
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
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)