---
title: Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c42db1-9a4d-4003-af69-f75ff48b575a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0286de636c2ad9fb50fabafe73b5257d18cf70b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993181"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-oracle-e-business-suite-using-the-wcf-service-model"></a>Operaciones ExecuteReader, ExecuteScalar o ExecuteNonQuery en Oracle E-Business Suite mediante el modelo de servicio WCF
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone operaciones genéricas como **ExecuteNonQuery**, **ExecuteReader**, y **ExecuteScalar**. Puede usar estas operaciones para ejecutar cualquier instrucción en Oracle E-Business Suite. Estas operaciones varían en función del tipo de respuesta que obtenga de la instrucción. Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, consulte [compatibilidad con ExecuteNonQuery, ExecuteReader y ExecuteScalar operaciones](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
 En este tema se muestra cómo realizar una **ExecuteReader** operación mediante la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante el modelo de servicio WCF. Puede seguir el mismo conjunto de procedimientos descritos en este tema para realizar **ExecuteNonQuery** y **ExecuteScalar** operaciones.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 El ejemplo de este tema se realiza una **ExecuteReader** operación que se realiza una operación de selección en la tabla de interfaz MS_SAMPLE_EMPLOYEE. La tabla se crea al ejecutar el script proporcionado con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Un ejemplo, **ExecuteReader**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar operaciones genéricas (ExecuteNonQuery, ExecuteReader y ExecuteScalar) utilizando el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] aparece en la tabla siguiente.  
  
|Operaciones|Nombre de cliente WCF|  
|----------------|---------------------|  
|ExecuteNonQuery, ExecuteReader y ExecuteScalar|GenericOperation_Client|  
  
### <a name="method-signature-for-invoking-generic-operations"></a>Firma de método para invocar operaciones genéricas  
 En la tabla siguiente se muestra la firma del método que se exponen para invocar las operaciones genéricas.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|ExecuteNonQuery|int ExecuteNonQuery (cadena de consulta, string [] OutputRefCursorNames, out System.Data.DataSet [] OutputRefCursors)|  
|ExecuteReader|System.Data.DataSet ExecuteReader(string Query)|  
|ExecuteScalar|cadena ExecuteScalar(string Query)|  
  
 Por ejemplo, la firma para los métodos de operación genérica se muestra en el siguiente fragmento de código.  
  
```  
public partial class GenericOperation_Client : System.ServiceModel.ClientBase<GenericOperation_>, GenericOperation_ {  
  public int ExecuteNonQuery(string Query, string[] OutputRefCursorNames, out System.Data.DataSet[] OutputRefCursors);  
  public System.Data.DataSet ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 En este fragmento de código  
  
-   `GenericOperation_Client` es el nombre de la clase. Esta clase se utiliza para crear un cliente para invocar la operación genérica, ExecuteReader.  
  
-   `public System.Data.DataSet ExecuteReader(string Query)` es el método que se invoca para llevar a cabo una instrucción SELECT en la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a>Creación de un cliente WCF para invocar la operación ExecuteReader  
 El conjunto genérico de las acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF implica un conjunto de tareas que se describen en [general del modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md). En esta sección se describe cómo crear un cliente WCF para invocar el **ExecuteReader** operación.  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a>Para crear un cliente WCF para invocar la operación ExecuteReader  
  
1. Cree un proyecto de Visual C# en Visual Studio. Este tema, cree una aplicación de consola.  
  
2. Generar la clase de cliente WCF para la **ExecuteReader** operación genérica. Esta operación está disponible bajo el nodo raíz al conectarse a Oracle E-Business Suite utilizando el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
   > [!IMPORTANT]
   >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`.  
  
4. Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
   -   `Microsoft.Adapters.OracleEBS`  
  
   -   `System.ServiceModel`  
  
5. En el archivo Program.cs, cree a un cliente como se describe en el siguiente fragmento.  
  
   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   EndpointAddress address = new EndpointAddress("oracleebs://ebs-72-11");  
   GenericOperation_Client client = new GenericOperation_Client(binding, address);  
   ```  
  
    En este fragmento de código, `GenericOperation_Client` es el cliente WCF definido en OracleEBSBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
   > [!NOTE]
   >  En este fragmento de código, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación. Puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información sobre las distintas maneras de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).  
  
6. Establecer las credenciales para el cliente.  
  
   ```  
   client.ClientCredentials.UserName.UserName = "myuser";  
   client.ClientCredentials.UserName.Password = "mypassword";  
   ```  
  
7. Dado que está realizando una operación en una tabla de interfaz, debe establecer el contexto de la aplicación. En este ejemplo, para establecer el contexto de la aplicación, especifica el **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
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
  
9. Invocar el **ExecuteReader** operación para realizar la operación de selección en la tabla MS_SAMPLE_EMPLOYEE. Antes de invocar la operación ExecuteReader, debe agregar el `System.Data` espacio de nombres en el código.  
  
    ```  
    string query = "SELECT * FROM MS_SAMPLE_EMPLOYEE";  
    DataSet ds = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the SELECT statement using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataTable tab in ds.Tables)  
    {  
       foreach (DataRow row in tab.Rows)  
       {  
          Console.WriteLine("The details of the employee are: ");  
          for (int i = 0; i < tab.Columns.Count; i++)  
          {  
             Console.WriteLine(row[i]);  
          }  
          Console.WriteLine();  
       }  
    }  
    Console.WriteLine("*****************************************************");  
    Console.ReadLine();  
  
    ```  
  
10. Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. Compile el proyecto y, a continuación, ejecútelo. Todos los registros de la tabla MS_SAMPLE_EMPLOYEE se muestran en la consola.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)