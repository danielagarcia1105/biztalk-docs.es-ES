---
title: Utilizar procedimientos almacenados con el modelo de servicio WCF de sondeo Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47dcb866-9161-4b28-9481-2761794ce805
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3fb7ebcbccb1f0edb3370176192f55f0db4985a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model"></a>Sondeo Oracle E-Business Suite mediante procedimientos almacenados con el modelo de servicio WCF
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódicos mediante procedimientos almacenados que éstos sondeen periódicamente la base de datos de Oracle. Puede especificar un procedimiento almacenado como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear la base de datos de Oracle.  
  
 Para habilitar el sondeo, debe especificar ciertas propiedades de enlace como se describe en este tema.  Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  
  
## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a>Configuración de una operación de sondeo con propiedades de enlace adaptador para Oracle E-Business  
 La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades de enlace que se utiliza para configurar el adaptador para recibir mensajes de cambio de datos. Debe especificar estas propiedades de enlace al ejecutar la aplicación de sondeo.  
  
|Propiedad de enlace|Description|  
|----------------------|-----------------|  
|**InboundOperationType**|Especifica si desea realizar un **sondeo** o **notificación** operación entrante. Valor predeterminado es **sondeo**.|  
|**PolledDataAvailableStatement**|Especifica la instrucción SQL que se ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. Sólo si hay un registro, el procedimiento almacenado que especificó para la **PollingInput** se va a ejecutar la propiedad de enlace.|  
|**PollingInterval**|Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se ejecuta la instrucción especificada para la **PolledDataAvailableStatement** propiedad de enlace. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo.|  
|**PollingInput**|Especifica la instrucción de sondeo. Para sondear mediante un procedimiento almacenado, debe especificar el mensaje de solicitud completo para esta propiedad de enlace. El mensaje de solicitud debe ser el mismo que envíe al adaptador para invocar el procedimiento almacenado como una operación de salida. El valor predeterminado es null.<br /><br /> Debe especificar un valor para **PollingInput** propiedad para habilitar el sondeo de enlace. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** propiedad de enlace.|  
|**PollingAction**|Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo de la interfaz de servicio generada para la operación con el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].|  
|**PostPollStatement**|Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.|  
|**PollWhileDataFound**|Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y ejecuta continuamente la instrucción de sondeo, si los datos están disponibles en la tabla que se va a sondear. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado. El valor predeterminado es False.|  
  
 Para obtener una descripción más completa de estas propiedades, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] sondear, lea las secciones siguientes.  
  
## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de mensajes mediante procedimientos almacenados, usas la GET_ACTIVITYS de cambio de datos procedimiento almacenado para sondear la tabla ACCOUNTACTIVITY en la base de datos de Oracle. Este procedimiento almacenado está disponible con el paquete ACCOUNT_PKG. Puede ejecutar los scripts SQL que se proporciona con los ejemplos para crear estos objetos en la base de datos.  
  
> [!NOTE]
>  El ejemplo de sondeos de este tema la ACCOUNTACTIVITY de tabla, que es una tabla de base de datos creada mediante la ejecución de las secuencias de comandos que se proporciona con los ejemplos. Debe realizar procesos similares tal como se describe en este tema para sondear cualquier otra tabla, incluidas las tablas de interfaz.  
  
 Para mostrar una operación de sondeo, llevamos a cabo lo siguiente:  
  
-   Especifique una instrucción SELECT para la **PolledDataAvailableStatement** propiedad para determinar donde la tabla se sondea, (ACCOUNTACTIVITY) de enlace tiene los datos. En este ejemplo, puede establecer esta propiedad de enlace como:  
  
    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  
  
     Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla ACCOUNTACTIVITY tiene algunos registros.  
  
-   Ejecutar un procedimiento almacenado, GET_ACTIVITYS, proporcionando el mensaje de solicitud como parte de la **PollingInput** propiedad de enlace. Este procedimiento almacenado recuperará todas las filas de la tabla ACCOUNTACTIVITY y aparecerá un mensaje de respuesta desde el adaptador.  
  
-   Ejecutar un bloque de PL/SQL como parte de la **PostPollStatement** propiedad de enlace. Esta instrucción moverá todos los datos de tabla ACCOUNTACTIVITY a otra tabla en la base de datos. Cuando esto ocurra, la próxima vez que **PollingInput** es ejecutar, no capturará los datos y, por tanto, el procedimiento almacenado de GET_ACTIVITYS devolverá un mensaje de respuesta vacío.  
  
-   Hasta que se agregan más datos a la tabla ACCOUNTACTIVITY, se seguirá pudiendo obtener mensajes de respuesta vacío por lo que debe volver a rellenar la tabla ACCOUNTACTIVITY con nuevos registros. Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a>Configuración de sondeo en el modelo de servicio WCF  
 Para sondear mediante procedimientos almacenados con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con el modelo de servicio WCF, debe:  
  
-   Generar un contrato de servicio WCF (interfaz) para el procedimiento almacenado con la que se va a sondear. En este ejemplo, debe generar el contrato de servicio WCF para la **GET_ACTIVITYS** procedimiento almacenado como una operación de entrada. Para ello, puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
-   Implementar un servicio WCF de esta interfaz.  
  
-   Hospedar este servicio WCF mediante un host de servicio (**System.ServiceModel.ServiceHost**).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 Los ejemplos de este sondeo tema la tabla de base de datos ACCOUNTACTIVITY mediante el GET_ACTIVITYS el procedimiento almacenan. Una secuencia de comandos para generar la tabla y el procedimiento almacenado se suministra con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Obtener un ejemplo, **StoredProcPolling_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
## <a name="the-wcf-service-contract-and-class"></a>El contrato de servicio WCF y la clase  
 Puede usar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para crear un contrato de servicio WCF (interfaz) y las clases para que admite la **GET_ACTIVITYS** operación entrante. Para obtener más información acerca de cómo generar un contrato de servicio WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
### <a name="the-wcf-service-contract-interface"></a>El contrato de servicio WCF (interfaz)  
 El código siguiente muestra el contrato de servicio WCF (interfaz) que se genera para la **GET_ACTIVITYS** operación entrante.  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/", ConfigurationName="PollingPackageApis_APPS_ACCOUNT_PKG")]  
public interface PollingPackageApis_APPS_ACCOUNT_PKG {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
    // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS")]  
    void GET_ACTIVITYS(GET_ACTIVITYS request);  
}  
```  
  
### <a name="the-message-contracts"></a>Los contratos de mensaje  
 Aquí te mostramos el contrato de mensaje para la **GET_ACTIVITYS** operación entrante.  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="GET_ACTIVITYS", WrapperNamespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
    "G", IsWrapped=true)]  
public partial class GET_ACTIVITYS {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PK" +  
        "G", Order=0)]  
    public schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS;  
  
    public GET_ACTIVITYS() {  
    }  
  
    public GET_ACTIVITYS(schemas.microsoft.com.OracleEBS._2008._05.RecordTypes.APPS.ACCOUNT_PKG.GET_ACTIVITYS.OUTRECSRecord[] OUTRECS) {  
        this.OUTRECS = OUTRECS;  
    }  
}  
```  
  
### <a name="wcf-service-class"></a>Clase de servicio WCF  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] también genera un archivo que tiene un código auxiliar para la clase de servicio WCF que implementa el contrato de servicio (interfaz). El nombre del archivo es OracleEBSBindingService.cs. Puede insertar la lógica para procesar el **GET_ACTIVITYS** operación directamente en esta clase. El código siguiente muestra la clase de servicio WCF generada por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
```  
namespace OracleEBSBindingNamespace {  
  
    public class OracleEBSBindingService : PollingPackageApis_APPS_ACCOUNT_PKG {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG) of message GET_ACTIVITYS   
        // does not match the default value (http://schemas.microsoft.com/OracleEBS/)  
        public virtual void GET_ACTIVITYS(GET_ACTIVITYS request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-inbound-messages-for-polling-using-a-stored-procedure"></a>Recibir mensajes de entrada para el sondeo de mediante un procedimiento almacenado  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación .NET para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
#### <a name="to-receive-polling-messages-using-a-stored-procedure"></a>Para recibir mensajes de sondeo mediante un procedimiento almacenado  
  
1.  Use la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar un contrato de servicio WCF (interfaz) y las clases auxiliares para el **GET_ACTIVITYS** operación entrante. Para obtener más información, consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md). También puede especificar las propiedades de enlace al generar las clases de contrato y el Ayudante de servicio. Esto garantiza que están establecidas correctamente en el archivo de configuración generado.  
  
2.  Implementar un servicio WCF desde las clases de interfaz y auxiliar generado en el paso 1. El **GET_ACTIVITYS** método de esta clase puede producir una excepción para anular la transacción de sondeo, si se produce un error de procesamiento de los datos recibidos de la **GET_ACTIVITYS** operación; en caso contrario el método no devuelve nada. La clase de servicio WCF debe atributo como se indica a continuación:  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    ```  
  
     En el **GET_ACTIVITYS** método, puede implementar la lógica de aplicación directamente. Esta clase se puede encontrar en OracleEBSBindingService.cs. Este código de este ejemplo Sub-clases el **OracleEBSBindingService** clase. En este código, el mensaje de sondeo recibe y se escribe en la consola.  
  
    ```  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
            }  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
        }  
    }  
    ```  
  
3.  Debe implementar la clase siguiente para evitar pasar las credenciales como parte del URI. En la última parte de la aplicación, se creará una instancia de esta clase para pasar las credenciales.  
  
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
  
4.  Crear un **OracleEBSBinding** y configure la operación de sondeo mediante la especificación de las propiedades de enlace. Puede hacerlo explícitamente en el código o mediante declaración en configuración. Como mínimo, debe especificar el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, y **PollingAction**propiedades de enlace.  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    binding.InboundOperationType = InboundOperation.Polling;  
    binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
    binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
    binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
    binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
    ```  
  
    > [!NOTE]
    >  Tenga en cuenta que el valor de la **PollingInput** propiedad de enlace contiene el mensaje de solicitud para invocar la **GET_ACTIVITYS** procedimiento almacenado como una operación de salida.  
  
    > [!IMPORTANT]
    >  En este ejemplo, porque se sondear una tabla de base de datos, es necesario establecer el contexto de las aplicaciones. Sin embargo, si se sondear una tabla de interfaz, debe establecer el contexto de las aplicaciones mediante la especificación de la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
5.  Especifique las credenciales de Oracle E-Business Suite creando el **PollingCredentials** clase creada en el paso 3.  
  
    ```  
    PollingCredentials credentials = new PollingCredentials();  
    credentials.UserName.UserName = "<Enter user name here>";  
    credentials.UserName.Password = "<Enter password here>";  
    ```  
  
6.  Cree una instancia del servicio WCF que creó en el paso 2.  
  
    ```  
    // create service instance  
    PollingService service = new PollingService();  
    ```  
  
7.  Cree una instancia de **System.ServiceModel.ServiceHost** mediante el servicio WCF y un URI de conexión base. El URI de conexión base no puede contener el identificador de entrada, si se especifica. También debe pasar las credenciales aquí.  
  
    ```  
    // Enable service host  
    Uri[] baseUri = new Uri[] { new Uri("oracleebs://ebs_instance_name") };  
    ServiceHost serviceHost = new ServiceHost(service, baseUri);  
    serviceHost.Description.Behaviors.Add(credentials);  
  
    ```  
  
8.  Agregar un extremo de servicio al host de servicio. Para hacerlo:  
  
    -   Utilice el enlace creado en el paso 4.  
  
    -   Especifica una URI que contiene las credenciales de conexión y, si es necesario, un identificador de entrada.  
  
    -   Especifique el contrato como "PollingPackageApis_APPS_ACCOUNT_PKG" para sondear la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
    ```  
    // Add service endpoint: be sure to specify PollingPackageApis_APPS_ACCOUNT_PKG as the contract  
    Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
    serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
    ```  
  
9. Para recibir datos de sondeo, abra el host del servicio. El adaptador devolverá datos cada vez que la consulta devuelve un conjunto de resultados.  
  
    ```  
    // Open the service host to begin polling  
    serviceHost.Open();  
    ```  
  
10. Para finalizar el sondeo, cierre el host del servicio.  
  
    > [!IMPORTANT]
    >  El adaptador seguirá sondea hasta que se cierra el host de servicio.  
  
    ```  
    serviceHost.Close();  
    ```  
  
### <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una aplicación de sondeo que sondea la tabla de base de datos ACCOUNTACTIVITY mediante el GET_ACTIVITYS de procedimiento almacenado. El **PollingInput** propiedad de enlace contiene el mensaje de solicitud para invocar el procedimiento almacenado de GET_ACTIVITYS que lee todos los datos de la tabla ACCOUNTACTIVITY y la instrucción de sondeo de envío pasa todos los datos de ACCOUNTACTIVITY en la tabla ACTIVITYHISTORY.  
  
 El primer mensaje de sondeo proporciona todos los registros de la tabla ACCOUNTACTIVITY. Mensajes de sondeo subsiguiente no contendrá ningún registro porque la instrucción de sondeo de envío elimina los registros. Hasta que se agregan más datos a la tabla ACCOUNTACTIVITY, no obtendrá ningún mensaje de sondeo por lo que debe volver a rellenar la tabla ACCOUNTACTIVITY con nuevos registros. Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos.  
  
 Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla. El adaptador seguirá sondea hasta que cierre el host de servicio presionando `<RETURN>`.  
  
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
  
namespace StoredProcPolling_ServiceModel  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingService : OracleEBSBindingNamespace.OracleEBSBindingService  
    {  
        public override void  GET_ACTIVITYS(GET_ACTIVITYS request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("*************************************************");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tProcessed");  
            for (int i = 0; i < request.OUTRECS.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}",  
                request.OUTRECS[i].TID,  
                request.OUTRECS[i].ACCOUNT,  
                request.OUTRECS[i].AMOUNT,  
                request.OUTRECS[i].PROCESSED);  
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
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM ACCOUNTACTIVITY";  
                binding.PollingInput = "<GET_ACTIVITYS xmlns='http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG'><INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS></GET_ACTIVITYS>";  
                binding.PollingAction = "PollingPackageApis/APPS/ACCOUNT_PKG/GET_ACTIVITYS";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
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
                serviceHost.AddServiceEndpoint("PollingPackageApis_APPS_ACCOUNT_PKG", binding, ConnectionUri);  
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
 [Sondeo Oracle E-Business Suite mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-the-wcf-service-model.md)