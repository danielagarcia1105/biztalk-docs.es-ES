---
title: "Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e227c60f-f6fe-40bf-bf41-2784a4428ad0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9ff6b37f2e18c03a364e3f584ea9f79b547f1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-concurrent-programs-in-oracle-e-business-suite-using-the-wcf-service-model"></a>Invocar programas simultáneos en Oracle E-Business Suite mediante el modelo de servicio WCF
Oracle E-Business Suite expone programas simultáneos que se pueden ejecutar para realizar operaciones específicas en las aplicaciones de Oracle. Cada aplicación de Oracle tiene un conjunto de programas simultáneos estándares (que son los mismos en todas las operaciones) y determinados programas simultáneos que son específicos de una aplicación de Oracle. La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone todos los programas simultáneos como las operaciones que los clientes de adaptador pueden invocar. Para obtener más información acerca del modo en que el adaptador admite programas simultáneos, consulte [operaciones en programas simultáneos](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md).  
  
> [!NOTE]
>  Para los programas simultáneos que no exponen sus metadatos, el adaptador de Oracle E-Business expone 100 parámetros opcionales para cada uno de estos programas simultáneos. Para invocar correctamente estos programas simultáneos, el usuario debe consultar la documentación de Oracle E-Business Suite para averiguar los parámetros de un programa simultáneo que requieren un valor y especifíquelos. Un ejemplo de este tipo de programa simultánea es **importación de Journal** (nombre real: **GLLEZL**) en el **contabilidad** aplicación.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema, se invoca el **MS_SAMPLE_COPY_EMP_DATA** programa simultáneo, seguido por el **Get_Status** programa simultáneo para conocer el estado del primer programa simultáneo. Estos programas simultáneos se invocan desde el **biblioteca de objetos de aplicación** aplicación. El **MS_SAMPLE_COPY_EMP_DATA** se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Obtener un ejemplo, **ConcurrentProgram_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF que se genera para llamar a los programas simultáneos por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] aparece en la tabla siguiente.  
  
|Artefacto|Nombre de cliente WCF|  
|--------------|---------------------|  
|Programa simultáneo|Cliente ConcurrentPrograms_ [APP_NAME]|  
  
 [APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, buscar.  
  
### <a name="method-signature-for-invoking-concurrent-programs"></a>Firma de método para invocar programas simultáneos  
 En la tabla siguiente se muestra la firma del método para los programas simultáneos.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Programa simultáneo|pública \<tipo de valor devuelto\> < Concurrent_program_name > (parámetro 1, el parámetro 2,...)|  
  
 Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.  
  
```  
public partial class ConcurrentPrograms_FNDClient : System.ServiceModel.ClientBase<ConcurrentPrograms_FND>, ConcurrentPrograms_FND {      
  
    public string MS_SAMPLE_COPY_EMP_DATA(schemas.microsoft.com.OracleEBS._2008._05.Options.SetOptions SetOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,  
      string Description, string StartTime);  
  
    public bool GetStatusForConcurrentProgram(string RequestId, out string Phase, out string Status,  
      out string DevPhase, out string DevStatus, out string Message);  
}  
```  
  
 En este fragmento de código, **ConcurrentPrograms_FNDClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. **MS_SAMPLE_COPY_EMP_DATA** es el nombre del método para invocar el programa simultáneo. **GetStatusForConcurrentProgram** es el nombre del método para invocar el programa simultáneo para obtener el estado del primer programa simultáneo.  
  
> [!NOTE]
>  **GetStatusForConcurrentProgram** es el nombre real de la **Get_Status** programa simultáneo.  
  
## <a name="creating-a-wcf-client-to-invoke-concurrent-programs"></a>Creación de un cliente WCF para invocar programas simultáneos  
 El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md). Esta sección describe cómo crear un cliente WCF para invocar la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.  
  
#### <a name="to-create-a-wcf-client"></a>Para crear a un cliente WCF  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
    > [!IMPORTANT]
    >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.  
  
4.  Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
5.  Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.  
  
    ```  
    OracleEBSBinding binding = new OracleEBSBinding();  
    EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
    ConcurrentPrograms_FNDClient client = new ConcurrentPrograms_FNDClient(binding, address);  
    ```  
  
     En este fragmento de código, `ConcurrentPrograms_FNDClient` es el cliente WCF definido en OracleEBSBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!NOTE]
    >  En este fragmento, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación. También puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).  
  
6.  Establezca las credenciales para el cliente.  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  Dado que va a invocar programas simultáneos en una aplicación de Oracle E-Business Suite, debe establecer el contexto de la aplicación. En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
    ```  
    binding.OracleUserName = "myOracleEBSUserName";  
    binding.OraclePassword = "myOracleEBSPassword";  
    binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
    ```  
  
8.  Abra al cliente como se describe en el siguiente fragmento:  
  
    ```  
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
    ```  
  
9. Invocar la **MS_SAMPLE_COPY_EMP_DATA** y **Get_Status** programas simultáneos.  
  
    ```  
    string RequestID;  
    bool Result;  
    string Phase;  
    string Status;  
    string DevPhase;  
    string DevStatus;  
    string Message;  
  
    try  
    {  
        Console.WriteLine("Invoking the MS_SAMPLE_COPY_EMP_DATA concurrent program");  
        RequestID = client.MS_SAMPLE_COPY_EMP_DATA(null, null, null, null, null);  
        Console.WriteLine("The request ID generated for the concurrent program is : " + RequestID);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nWaiting for 60 seconds for the concurrent program to be complete");  
        System.Threading.Thread.Sleep(60000);  
        Console.WriteLine("\nInvoking the Get_Status concurrent program");  
        Result = client.GetStatusForConcurrentProgram(RequestID, out Phase, out Status, out DevPhase, out DevStatus, out Message);  
        Console.WriteLine("\nResult is  : " + Result);  
        Console.WriteLine("Phase is     : " + Phase);  
        Console.WriteLine("Status is    : " + Status);  
        Console.WriteLine("DevPhase is  : " + DevPhase);  
        Console.WriteLine("DevStatus is : " + DevStatus);  
        Console.WriteLine("Message is   : " + Message);  
        Console.WriteLine("********************************************************");  
        Console.WriteLine("\nHit <RETURN> to end");  
        Console.ReadLine();  
    }  
    catch (Exception ex)  
    {  
        Console.WriteLine("Exception : " + ex);  
        throw;                 
    }  
    ```  
  
10. Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    ```  
  
11. Compile el proyecto y, a continuación, ejecútelo. La aplicación invoca el **MS_SAMPLE_COPY_EMP_DATA** y devuelve un identificador de solicitud. El identificador se pasa a continuación el **Get_Status** programa simultánea, lo que finalmente proporciona el estado de la **MS_SAMPLE_COPY_EMP_DATA** programa de columna.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)