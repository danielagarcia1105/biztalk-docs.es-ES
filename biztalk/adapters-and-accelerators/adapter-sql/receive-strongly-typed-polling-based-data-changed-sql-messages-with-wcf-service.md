---
title: Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante el modelo de servicio WCF | Microsoft Docs
description: Usar una aplicación .NET para configurar el sondeo con tipo o sondeo fuertemente tipado mediante el servicio WCF con el adaptador de WCF-SQL en BizTalk Server
ms.custom: ''
ms.date: 10/09/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55eda71-1226-43f2-bc2f-e6b35563210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf6f1e322485521504259f24dade00bb33a4539
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012653"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-wcf-service-model"></a>Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante el modelo de servicio WCF
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de sondeo fuertemente tipado de SQL Server. Puede especificar una instrucción de sondeo que se ejecuta el adaptador para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados. Debe usar sondeo fuertemente tipado en un escenario donde desea que reciban un conjunto de resultados fuertemente tipado. Para obtener más información sobre cómo el adaptador admite el sondeo fuertemente tipado, vea [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  

> [!IMPORTANT]
>  Si desea tener más de un sondeo operación en una sola aplicación, debe especificar un **InboundID** propiedad de conexión como parte de la conexión URI para que sea único. Especifica el identificador de entrada se agrega al espacio de nombres de operación para que sea único.  

## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos fuertemente tipados mensajes de cambio, cree una aplicación .NET y generar el contrato de servicio WCF para la **TypedPolling** operación. Asegúrese de que se especifique lo siguiente al generar el contrato de servicio WCF:  

- Debe especificar un **InboundID** como parte de la URI de conexión.  

- Debe especificar una instrucción de sondeo para el **PollingStatement** enlaza la propiedad.  

  Además, si desea especificar otro sondeo relacionados con la propiedades de enlace al generar la clase de proxy, especifique el **PolledDataAvailableStatement** como:  

```  
SELECT COUNT(*) FROM Employee  
```  

 El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo. Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.  

 Como parte de la instrucción de sondeo, realice las siguientes operaciones:  

1. Seleccione todas las filas de la tabla Employee.  

2. Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.  

3. Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla Employee. Este procedimiento toma el nombre de empleado, designación y salario como parámetros.  

   Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** enlaza la propiedad al generar las clases de aplicación auxiliar de contrato del servicio WCF:  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 Después de ejecutar la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se recibe el mensaje de SQL Server. Después de ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados. A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla Employee. La siguiente ejecución de sondeo solo devolverá un único registro. Este ciclo continúa hasta que cierre el host de servicio.  

## <a name="configuring-typed-polling-with-the-sql-adapter-binding-properties"></a>Configuración de sondeo con tipo con el adaptador de SQL, las propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades que usan para configurar el adaptador para recibir mensajes de cambio de datos de enlace. No sea el **PollingStatement** propiedad de enlace, todas las demás propiedades de enlace enumerados en esta sección son necesarios al ejecutar la aplicación. NET. Debe especificar el **PollingStatement** enlaza la propiedad antes de generar el contrato de servicio WCF **TypedPolling** operación.  


|         Propiedad de enlace         |                                                                                                                                                                                                                                                                                              Descripción                                                                                                                                                                                                                                                                                              |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                             Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante. El valor predeterminado es **sondeo**. Para recibir mensajes de sondeo fuertemente tipado, establezca esta opción en **TypedPolling**.                                                                                                                                                                                             |
| **PolledDataAvailableStatement** |                                                                                                                                           Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados. Solo si hay una fila, la instrucción SQL especificada para el **PollingStatement** se ejecutará el enlace de propiedad.                                                                                                                                            |
|   **PollingIntervalInSeconds**   |                                                                              Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.                                                                              |
|       **PollingStatement**       | Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server. Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo. El valor predeterminado es null. Debe especificar un valor para **PollingStatement** para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad. Puede especificar cualquier número de instrucciones SQL separadas por punto y coma. **Importante:** para **TypedPolling**, debe especificar esta propiedad de enlace antes de generar los metadatos. |
|      **PollWhileDataFound**      |                                                                                 Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y continuamente se ejecuta la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado. El valor predeterminado es **false**.                                                                                 |

 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, siga leyendo.  

## <a name="configure-strongly-typed-polling-in-the-wcf-service-model"></a>Configuración de sondeo fuertemente tipado en el modelo de servicio WCF  
 Para recibir el **sondeo** operación cuando se usa el modelo de servicio WCF, debe:  

1. Generar un contrato de servicio WCF (interfaz) para el **TypedPolling** operación desde los metadatos expuestos por el adaptador. Para ello, puede usar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. Al generar el contrato de servicio WCF para este ejemplo, asegúrese de que:  

   -   Especifique el **InboundID** como **empleado**.  

   -   Especifique una instrucción de sondeo para el **PollingStatement** enlaza la propiedad. En este ejemplo, especifique la instrucción de sondeo como:  

       ```  
       SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
       ```  

2. Implementar un servicio WCF desde esta interfaz.  

3. Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  

## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema sondean la tabla de empleados. El ejemplo también usa el MOVE_EMP_DATA y ADD_EMP_DETAILS procedimiento almacenado. Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md). Un ejemplo, **TypedPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  

## <a name="the-wcf-service-contract-and-class"></a>El contrato de servicio WCF y la clase  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y la compatibilidad con las clases para el **TypedPolling** operación. Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  

### <a name="the-wcf-service-contract-interface"></a>El contrato de servicio WCF (interfaz)  
 El código siguiente muestra el contrato de servicio WCF (interfaz) generado para el **TypedPolling** operación.  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/", ConfigurationName="TypedPolling_Employee")]  
public interface TypedPolling_Employee {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
    // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="TypedPolling")]  
    void TypedPolling(TypedPolling request);  
}  
```  

### <a name="the-message-contracts"></a>Los contratos de mensaje  
 El espacio de nombres de contrato de mensaje se modifica mediante la **InboundID** parámetro en la conexión URI, si se especifica. En este ejemplo, se especifica el identificador de entrada como **empleado**. El mensaje de solicitud devuelve un conjunto de resultados fuertemente tipado.  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="TypedPolling", WrapperNamespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", IsWrapped=true)]  
public partial class TypedPolling {  

[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=0)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0;  

[System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee", Order=1)]  
    public schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1;  

    public TypedPolling() {  
    }  

    public TypedPolling(schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet0[] TypedPollingResultSet0, schemas.microsoft.com.Sql._2008._05.TypedPolling.Employee.TypedPollingResultSet1[] TypedPollingResultSet1) {  
        this.TypedPollingResultSet0 = TypedPollingResultSet0;  
        this.TypedPollingResultSet1 = TypedPollingResultSet1;  
    }  
}  
```  

### <a name="wcf-service-class"></a>Clase de servicio WCF  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz). El nombre del archivo es SqlAdapterBindingService.cs. Puede insertar la lógica para procesar el **TypedPolling** operación directamente en esta clase. El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

```  
namespace SqlAdapterBindingNamespace {  

    public class SqlAdapterBindingService : TypedPolling_Employee {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/Sql/2008/05/TypedPolling/Employee) of message TypedPolling  
        // does not match the default value (http://schemas.microsoft.com/Sql/2008/05/)  
        public virtual void TypedPolling(TypedPolling request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receive-strongly-typed-inbound-messages-for-polling-operation"></a>Recibir los mensajes entrantes fuertemente tipados para la operación de sondeo  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir mensajes de entrada de sondeo fuertemente tipado mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

1. Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y clases auxiliares para el **TypedPolling** operación. Asegúrese de que se especifique lo siguiente al generar el contrato de servicio WCF para este ejemplo:  

   - Debe especificar el **InboundID** como **empleado**.  

   - Debe especificar una instrucción de sondeo para el **PollingStatement** enlaza la propiedad. En este ejemplo, especifique la instrucción de sondeo como:  

     ```  
     SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000  
     ```  

     Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md). También puede especificar las propiedades de enlace al generar las clases auxiliares y de contrato de servicio. Esto garantiza que están establecidas correctamente en el archivo de configuración generado.  

2. Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1. El **TypedPolling** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **TypedPolling** operación; de lo contrario el método no devuelve nada. Debe atributo la clase de servicio WCF como sigue:  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    Dentro de la **TypedPolling** método, puede implementar la lógica de aplicación directamente. Esta clase puede encontrarse en SqlAdapterBindingService.cs. Este código en este ejemplo Sub clases el **SqlAdapterBindingService** clase. En este código, se escribe el mensaje de sondeo recibido como un conjunto de resultados fuertemente tipados a la consola.  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
   {  
       public override void TypedPolling(TypedPolling request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  

           for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.TypedPollingResultSet0[i].Employee_ID,  
               request.TypedPollingResultSet0[i].Name,  
               request.TypedPollingResultSet0[i].Designation,  
               request.TypedPollingResultSet0[i].Salary);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. Dado que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no acepta credenciales como parte de la URI de conexión, debe implementar la siguiente clase para pasar las credenciales para la base de datos de SQL Server. En la última parte de la aplicación, se creará instancias de esta clase para pasar las credenciales de SQL Server.  

   ```  
   class PollingCredentials : ClientCredentials, IServiceBehavior  
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
           ClientCredentials clone = new PollingCredentials();  
           clone.UserName.UserName = this.UserName.UserName;  
           clone.UserName.Password = this.UserName.Password;  
           return clone;  
       }  
   }  
   ```  

4. Crear un **SqlAdapterBinding** y configurar la operación de sondeo mediante la especificación de las propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, y **PollingStatement**.  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.TypedPolling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

5. Especifique las credenciales de base de datos de SQL Server creando el **PollingCredentials** clase creada en el paso 3.  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

6. Cree una instancia del servicio WCF que creó en el paso 2.  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

7. Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base. El URI de conexión base no puede contener el identificador entrante. También debe especificar las credenciales aquí.  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

8. Agregar un extremo de servicio al host de servicio. Para hacerlo:  

   -   Utilice el enlace creado en el paso 4.  

   -   Especifique un URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.  

   -   Especifique el contrato como "TypedPolling_Employee".  

   ```  
   // Add service endpoint: be sure to specify TypedPolling_Employee as the contract  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundID=Employee");  
   serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
   ```  

9. Para recibir datos de sondeo, abra el host de servicio. El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

10. Para finalizar el sondeo, cierre el host de servicio.  

    > [!IMPORTANT]
    >  El adaptador seguirá sondeando hasta que se cierra el host de servicio.  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una consulta de sondeo que se ejecuta en la tabla Employee. La instrucción de sondeo lleva a cabo las siguientes tareas:  

1. Selecciona todos los registros de la tabla Employee.  

2. Ejecuta el procedimiento MOVE_EMP_DATA almacenado para mover todos los registros de la tabla Employee a HistorialEmpleados tabla.  

3. Ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un único registro a la tabla Employee.  

   El primer mensaje de sondeo contendrá todos los registros de la tabla Employee. Los mensajes de sondeo subsiguiente contendrá solo el último registro insertado por el procedimiento almacenado de ADD_EMP_DETAILS. El adaptador seguirá sondeando hasta que cierre el host de servicio presionando `<RETURN>`.  

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

namespace TypedPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : SqlAdapterBindingNamespace.SqlAdapterBindingService  
    {  
        public override void TypedPolling(TypedPolling request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Employee ID\tName\tDesignation\tSalary");  

            for (int i = 0; i < request.TypedPollingResultSet0.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.TypedPollingResultSet0[i].Employee_ID,  
                request.TypedPollingResultSet0[i].Name,  
                request.TypedPollingResultSet0[i].Designation,  
                request.TypedPollingResultSet0[i].Salary);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  

    class PollingCredentials : ClientCredentials, IServiceBehavior  
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
            ClientCredentials clone = new PollingCredentials();  
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
                Console.WriteLine("Press any key to start polling...");  
                Console.ReadLine();  

                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.TypedPolling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
                Console.WriteLine("Binding properties assigned...");  

                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?InboundId=Employee");  

                // This URI is used to initialize the ServiceHost. It cannot contain  
                // the InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("mssql://mysqlserver//mydatabase") };  

                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("TypedPolling_Employee", binding, ConnectionUri);  
                serviceHost.Open();  
                Console.WriteLine("Service host opened...");  
                Console.WriteLine("Polling started...");  
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
 [Sondear el servidor SQL mediante el adaptador de SQL con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)
