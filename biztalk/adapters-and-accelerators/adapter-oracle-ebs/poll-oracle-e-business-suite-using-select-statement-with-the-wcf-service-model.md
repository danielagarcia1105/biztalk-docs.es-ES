---
title: Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 521d58e4-73b1-48a8-9a0a-9e733386c1b5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8484acc15d2328ab444a8df6e55dc0ff952899a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000701"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model"></a>Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de servicio WCF
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódica mediante el uso de una instrucción SELECT para las tablas de interfaz un sondeo continuo, interfaz vistas, tablas y vistas de Oracle E-Business Suite. Puede especificar una instrucción SELECT como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear Oracle E-Business Suite. También puede especificar un bloque de código posterior a la encuesta PL/SQL que el adaptador se ejecuta después de ejecutar la instrucción de sondeo.  

 Para habilitar el sondeo, debe especificar ciertas propiedades de enlace como se describe en este tema.  Para obtener más información acerca de cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Configuración de una operación de sondeo con enlazar propiedades de adaptador para Oracle E-Business Suite  
 La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mensajes de cambio de propiedades de enlace que usan para configurar el adaptador para recibir datos. Debe especificar estas propiedades de enlace al ejecutar la aplicación de sondeo.  


|         Propiedad de enlace         |                                                                                                                                                                                                                            Descripción                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          Especifica si desea realizar **sondeo** o **notificación** operación entrante. El valor predeterminado es **sondeo**.                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. Solo si hay un registro, la instrucción SELECT especifique para la **PollingInput** se ejecutará el enlace de propiedad.                                                                                                              |
|       **PollingInterval**        | Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo. |
|         **PollingInput**         |                         Especifica la instrucción de sondeo. Para sondear con una instrucción SELECT, debe especificar una instrucción SELECT para esta propiedad de enlace. El valor predeterminado es null.<br /><br /> Debe especificar un valor para **PollingInput** enlace de propiedad para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad.                          |
|        **PollingAction**         |                                                                                                                Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo de la interfaz de servicio generada para la operación mediante la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].                                                                                                                |
|      **PostPollStatement**       |                                                                                                                                                                  Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y la instrucción de sondeo, se ejecuta continuamente si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado. El valor predeterminado es False.                                     |

 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle, siga leyendo.  

## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de datos cambia mensajes mediante las instrucciones SELECT, sondea la **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación**aplicación. Esta tabla se crea al ejecutar el script de create_apps_artifacts.sql proporcionado con los ejemplos para crear estos objetos en Oracle E-Business Suite.  

 Para demostrar una operación de sondeo, llevamos a cabo lo siguiente:  

-   Especifique una instrucción SELECT para la **PolledDataAvailableStatement** enlaza la propiedad para determinar donde la interfaz tabla sondea (MS_SAMPLE_EMPLOYEE) tiene los datos. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla de interfaz MS_SAMPLE_EMPLOYEE tiene algunos registros.  

-   Especifique una instrucción SELECT para la **PollingInput** enlaza la propiedad. Esta instrucción recupera todas las filas de la tabla de interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  Para obtener información acerca de la cláusula FOR UPDATE en la instrucción SELECT, vea [recibir los mensajes basados en sondeos de cambio de datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).  

-   Especifique una instrucción DELETE como parte de la **PostPollStatement** enlaza la propiedad. Esta instrucción eliminará todos los datos de tabla de la interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     Tras esto, la próxima vez que la instrucción especificada para **PollingInput** será ejecuta, no capturará todos los datos.  

-   Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo por lo que debe volver a llenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros. Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.  

## <a name="configuring-polling-in-the-wcf-service-model"></a>Configuración de sondeo en el modelo de servicio WCF  
 Para sondear una tabla de interfaz mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con el modelo de servicio WCF, debe:  

- Generar un contrato de servicio WCF (interfaz) para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE. Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

- Implementar un servicio WCF desde esta interfaz.  

- Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  

## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema sondean la tabla de interfaz MS_SAMPLE_EMPLOYEE. Se proporciona un script para generar la tabla con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Un ejemplo, **SelectPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  

## <a name="the-wcf-service-contract-and-class"></a>El contrato de servicio WCF y la clase  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y la compatibilidad con las clases para el **sondeo** operación. Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  

### <a name="the-wcf-service-contract-interface"></a>El contrato de servicio WCF (interfaz)  
 El código siguiente muestra el contrato de servicio WCF (interfaz) generado para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE.  

```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE")]  
public interface InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE")]  
    void Poll(Poll request);  
}  
```  

### <a name="the-message-contracts"></a>Los contratos de mensaje  
 La siguiente es el contrato de mensaje para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE.  

```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="Poll", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
    "_EMPLOYEE", IsWrapped=true)]  
public partial class Poll {  

    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE" +  
        "_EMPLOYEE", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA;  

    public Poll() {  
    }  

    public Poll(schemas.microsoft.com.OracleEBS._2008._05.TableViewRecord.APPS.MS_SAMPLE_EMPLOYEE.SelectRecord[] DATA) {  
        this.DATA = DATA;  
    }  
}  
```  

### <a name="wcf-service-class"></a>Clase de servicio WCF  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF implementa el contrato de servicio (interfaz). El nombre del archivo es OracleEBSBindingService.cs. Puede insertar la lógica para procesar el **sondeo** operación directamente en esta clase. El código siguiente muestra la clase de servicio WCF generada por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  

```  
namespace OracleEBSBindingNamespace {  

    public class OracleEBSBindingService : InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {  

        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE) of message Poll   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void Poll(Poll request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  

## <a name="receiving-inbound-messages-for-the-poll-operation-using-a-select-statement"></a>Recibir mensajes de entrada para la operación de sondeo con una instrucción SELECT  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación de .NET para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  

#### <a name="to-receive-polling-messages-using-a-select-statement"></a>Para recibir mensajes de sondeo mediante una instrucción SELECT  

1. Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y clases auxiliares para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md). También puede especificar las propiedades de enlace al generar las clases auxiliares y de contrato de servicio. Esto garantiza que están establecidas correctamente en el archivo de configuración generado.  

2. Implementar un servicio WCF desde las clases auxiliares y la interfaz generada en el paso 1. El **sondeo** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **sondeo** operación; en caso contrario, el método no lo hace devolver nada. Debe atributo la clase de servicio WCF como sigue:  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  

    Dentro de la **sondeo** método, puede implementar la lógica de aplicación directamente. Esta clase puede encontrarse en OracleEBSBindingService.cs. Este código en este ejemplo Sub clases el **OracleEBSBindingService** clase. En este código, el mensaje de sondeo recibe y se escribe en la consola.  

   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

   public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
   {  
       public override void Poll(Poll request)  
       {  
           Console.WriteLine("\nNew Polling Records Received");  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
           for (int i = 0; i < request.DATA.Length; i++)  
           {  
               Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
               request.DATA[i].EMP_NO,  
               request.DATA[i].NAME,  
               request.DATA[i].DESIGNATION,  
               request.DATA[i].SALARY);  
           }  
           Console.WriteLine("*************************************************");  
           Console.WriteLine("\nHit <RETURN> to stop polling");  
       }  
   }  
   ```  

3. Debe implementar la clase siguiente para evitar pasar las credenciales como parte del URI. En la última parte de la aplicación, se creará instancias de esta clase para pasar las credenciales.  

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

4. Crear un **OracleEBSBinding** y configurar la operación de sondeo mediante la especificación de las propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, y **PollingAction**propiedades de enlace.  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

5. Dado que sondean una tabla de interfaz, también debe establecer el contexto de las aplicaciones. Para obtener más información sobre el contexto de la aplicación y las propiedades de enlace necesarias para el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  

6. Especifique las credenciales de Oracle E-Business Suite creando el **PollingCredentials** clase creada en el paso 3.  

   ```  
   PollingCredentials credentials = new PollingCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  
   ```  

7. Cree una instancia del servicio WCF que creó en el paso 2.  

   ```  
   // create service instance  
   PollingService service = new PollingService();  
   ```  

8. Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio de WCF y un URI de conexión de base. El URI de conexión base no puede contener el identificador de entrada, si se especifica. También se deben pasar las credenciales aquí.  

   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
   ServiceHost serviceHost = new ServiceHost(service, baseUri);  
   serviceHost.Description.Behaviors.Add(credentials);  

   ```  

9. Agregar un extremo de servicio al host de servicio. Para hacerlo:  

   - Utilice el enlace creado en el paso 4.  

   - Especifique un URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.  

   - Especifique el contrato como "InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE" para sondear la tabla de interfaz MS_SAMPLE_EMPLOYEE.  

     ```  
     // Add service endpoint: be sure to specify InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE as the contract  
     Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
     serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
     ```  

10. Para recibir datos de sondeo, abra el host de servicio. El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.  

    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  

11. Para finalizar el sondeo, cierre el host de servicio.  

    > [!IMPORTANT]
    >  El adaptador seguirá sondeando hasta que se cierra el host de servicio.  

    ```  
    serviceHost.Close();  
    ```  

### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una aplicación de sondeo que sondea la tabla de interfaz MS_SAMPLE_EMPLOYEE. El **PollingInput** propiedad contiene la instrucción select que lee todos los datos de la tabla MS_SAMPLE_EMPLOYEE y la instrucción de sondeo de envío, elimina todos los datos de la misma tabla. El primer mensaje de sondeo proporciona todos los registros de la tabla de interfaz MS_SAMPLE_EMPLOYEE. Mensajes de sondeo subsiguiente no contendrá ningún registro porque la instrucción de sondeo de envío elimina los registros. Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo. Por lo tanto, debe volver a llenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros. Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla. El adaptador seguirá sondeando hasta que cierre el host de servicio presionando `<RETURN>`.  

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

namespace SelectPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  

    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void Poll(Poll request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Emp No\tName\tDesignation\tSalary");  
            for (int i = 0; i < request.DATA.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.DATA[i].EMP_NO,  
                request.DATA[i].NAME,  
                request.DATA[i].DESIGNATION,  
                request.DATA[i].SALARY);  
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

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "myOracleEBSUserName";  
                binding.OraclePassword = "myOracleEBSPassword";  
                binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  

                // This URI is used to specify the address for the ServiceEndpoint  
                // It must contain the InboundId that was used to generate  
                // the WCF service callback interface  
                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  

                // This URI is used to initialize the ServiceHost. It cannot contain  
                // an InboundID; otherwise,an exception is thrown when  
                // the ServiceHost is initialized.  
                Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  

                PollingCredentials credentials = new PollingCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                Console.WriteLine("Opening service host...");  
                PollingService service = new PollingService();  
                serviceHost = new ServiceHost(service, baseUri);  
                serviceHost.Description.Behaviors.Add(credentials);  
                serviceHost.AddServiceEndpoint("InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE", binding, ConnectionUri);  
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
 [Sondear Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)