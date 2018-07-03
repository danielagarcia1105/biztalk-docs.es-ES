---
title: Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb6ec551-c069-4133-add5-2ba83d20405d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85ee6a77bcd93deaceafde03cec9fb8b1d4f6ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971053"
---
# <a name="invoke-request-sets-in-oracle-e-business-suite-using-the-wcf-service-model"></a>Invocar conjuntos de solicitudes en Oracle E-Business Suite mediante el modelo de servicio WCF
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] le permite ejecutar conjuntos de solicitudes en Oracle E-Business Suite. Solicitar conjuntos se dividen en una o varias fases y cada fase contiene un conjunto de informes y los programas simultáneos. Para obtener más información sobre cómo el adaptador es compatible con conjuntos de solicitudes, consulte [operaciones en la solicitud establece](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar la solicitud, se establece la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] aparece en la tabla siguiente.  
  
|Artefacto|Nombre de cliente WCF|  
|--------------|---------------------|  
|Conjunto de solicitud|Cliente RequestSets_ [APP_NAME]|  
  
 [APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite. Por ejemplo, SQLAP.  
  
### <a name="method-signature-for-invoking-request-sets"></a>Firma de método para invocar conjuntos de solicitudes  
 En la tabla siguiente se muestra la firma del método para conjuntos de solicitudes.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Conjunto de solicitud|pública \<tipo de valor devuelto\> \<nombre del conjunto de solicitud\>(parámetro 1, el parámetro 2,...)|  
  
 Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para el **reqset_singlestage** solicitar conjunto.  
  
> [!NOTE]
>  Esto es un conjunto de solicitudes personalizado y podría no estar disponible en la instancia de Oracle E-Business solución.  
  
```  
public partial class RequestSets_SQLAPClient : System.ServiceModel.ClientBase<RequestSets_SQLAP>, RequestSets_SQLAP{      
  
    public string REQSTG(  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRelClassOptions SetRelClassOptions,  
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetPrintOptions SetPrintOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetRepeatOptions SetRepeatOptions,   
      schemas.microsoft.com.OracleEBS._2008._05.Options.SetNlsOptions SetNlsOptions,  
      string StartTime,  
      schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 set1_set1);  
}  
```  
  
 En este fragmento de código, **RequestSets_SQLAPClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. **REQSTG** es el nombre del método para invocar el conjunto de solicitud.  
  
## <a name="creating-a-wcf-client-to-invoke-request-sets"></a>Creación de un cliente WCF para invocar conjuntos de solicitudes  
 El conjunto genérico de las acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF implica un conjunto de tareas que se describen en [general del modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md). En esta sección se describe cómo crear un cliente WCF para invocar el **reqset_singlestage** solicitar conjunto.  
  
#### <a name="to-create-a-wcf-client"></a>Para crear a un cliente WCF  
  
1. Cree un proyecto de Visual C# en Visual Studio. Este tema, cree una aplicación de consola.  
  
2. Generar la clase de cliente WCF para la **reqset_singlestage** solicitar conjunto. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
   > [!IMPORTANT]
   >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.  
  
4. Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. Abra el archivo Program.cs y cree a un cliente como se describe en el siguiente fragmento.  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs_instance_name");  
   RequestSets_SQLAPClient client = new RequestSets_SQLAPClient(binding, address);  
   ```  
  
    En este fragmento de código, `RequestSets_SQLAPClient` es el cliente WCF definido en OracleEBSBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
   > [!NOTE]
   >  En este fragmento de código, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación. También puede usar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información sobre las distintas maneras de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).  
  
6. Establecer las credenciales para el cliente.  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. Dado que va a invocar conjuntos de solicitudes en una aplicación de Oracle E-Business Suite, debe establecer el contexto de la aplicación. En este ejemplo, para establecer el contexto de la aplicación, especifica el **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
   ```  
   binding.OracleUserName = "myOracleEBSUserName";  
   binding.OraclePassword = "myOracleEBSPassword";  
   binding.OracleEBSResponsibilityName = "myOracleEBSResponsibility";  
   ```  
  
8. Abra al cliente como se describe en el siguiente fragmento:  
  
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
  
9. Invocar el **reqset_singlestage** solicitar conjunto.  
  
    ```  
    string RequestID;  
  
    schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1 param =  
        new schemas.microsoft.com.OracleEBS._2008._05.RequestSetStage.SQLAP.REQSTG.set1();  
  
    param.INSPARAMPROG = new schemas.microsoft.com.OracleEBS._2008._05.RequestSetConcurrentProgram.SQLAP.REQSTG.set1.SQLAP1.INSPARAMPROG();  
    param.INSPARAMPROG.p_id = "123";  
    param.INSPARAMPROG.p_name = "MyName";  
  
    try  
    {  
        Console.WriteLine("Invoking the reqset_singlestage request set");  
        RequestID = client.REQSTG(null, null, null, null, null, param);  
        Console.WriteLine("The request ID generated for the request set is : " + RequestID);  
        Console.WriteLine("*****************************************************************");  
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
  
11. Compile el proyecto y, a continuación, ejecútelo. La aplicación invoca el **reqset_singlestage** solicitud conjunto y devuelve un identificador de solicitud, que se escribe en la consola.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)