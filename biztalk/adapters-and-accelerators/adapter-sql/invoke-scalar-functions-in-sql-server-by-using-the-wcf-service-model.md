---
title: Invocar funciones escalares en SQL Server mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a331e275-3c81-41a8-9ba1-3a801ebc259a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a04904f1170644498d49670104a842b4c8f9dd2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model"></a>Invocar funciones escalares en SQL Server mediante el modelo de servicio WCF
Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una aplicación de .NET mediante el modelo de servicio WCF para invocar funciones escalares en SQL Server. El adaptador expone las funciones escalares como métodos que se pueden invocar directamente en SQL Server. Para obtener más información acerca del modo en que el adaptador admite funciones escalares, consulte [ejecutar funciones escalares en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/execute-scalar-functions-in-sql-server-using-the-sql-adapter.md).  
  
## <a name="how-this-topic-demonstrates-invoking-scalar-functions-using-the-wcf-service-model"></a>Cómo en este tema se muestra cómo invocar funciones escalares mediante el modelo de servicio WCF  
 Este tema muestra cómo invocar la función GET_EMP_ID en una base de datos de SQL Server. La función GET_EMP_ID toma la designación de un empleado en el **empleado** tabla y devuelve el identificador de empleado correspondiente. La función GET_EMP_ID y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema, invoca la función escalar GET_EMP_ID en la tabla de empleados. La función GET_EMP_ID y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos. Obtener un ejemplo, **ScalarFunction_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar la función escalar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Función escalar|Cliente ScalarFunctions_ [esquema]|  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
### <a name="method-signature-for-invoking-scalar-functions"></a>Firma de método para invocar funciones escalares  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Nombre de la función escalar|pública *< return_type >**< scalar_function_name >*(parámetro1, parámetro2,...)|  
  
 \<*retrun_type* \> = tipo de valor devuelto definido en la definición de función  
  
 \<*scalar_function_name* \> = nombre de la función escalar.  
  
 Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **GET_EMP_ID** funciones escalares, en el esquema dbo, que toma la designación de empleado como parámetro y devuelve un empleado (Id. valor entero).  
  
```  
public partial class ScalarFunctions_dboClient : System.ServiceModel.ClientBase<ScalarFunctions_dbo>, ScalarFunctions_dbo {      
    public System.Nullable<int> GET_EMP_ID(string emp_desig);  
}  
```  
  
 En este fragmento de código, **ScalarFunctions_dboClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
### <a name="parameters-for-invoking-scalar-functions"></a>Parámetros para invocar funciones escalares  
 Los parámetros para los métodos expuestos por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para invocar un valor escalar, función son los mismos que los parámetros definidos en la definición de función escalar en SQL Server. Por ejemplo, el parámetro para invocar la función escalar GET_EMP_ID es emp_desig y toma la designación de un empleado.  
  
 Una vez más, el valor devuelto para una función escalar es igual que el valor devuelto definido en la definición de función escalar en SQL Server. Por ejemplo, el valor devuelto para la función GET_EMP_ID es el identificador de un empleado de tipo entero.  
  
## <a name="creating-a-wcf-client-to-invoke-scalar-functions"></a>Creación de un cliente WCF para invocar funciones escalares  
 El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md). Esta sección describe cómo crear un cliente WCF para invocar la **GET_EMP_ID** función escalar.  
  
#### <a name="to-create-a-wcf-client"></a>Para crear a un cliente WCF  
  
1.  Crear un proyecto de Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la **GET_EMP_ID** función escalar. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.  
  
4.  Abra Program.cs y cree a un cliente tal y como se describe en el siguiente fragmento.  
  
    ```  
  
              ScalarFunctions_dboClient client = new ScalarFunctions_dboClient("SqlAdapterBinding_ScalarFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     En este fragmento de código, `ScalarFunctions_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_ScalarFunctions_dbo`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
    > [!NOTE]
    >  En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las distintas formas de especificar, a continuación, enlace de cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
5.  Abra al cliente como se describe en el siguiente fragmento:  
  
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
  
6.  Invocar la **GET_EMP_ID** función para recuperar el identificador de un empleado con la designación como "Administrador".  
  
    ```  
    Console.WriteLine("Invoking the GET_EMP_ID function");  
    string emp_designation = "Manager";  
    try  
    {  
          System.Nullable<int> emp_id = client.GET_EMP_ID(emp_designation);  
          Console.WriteLine("The Employee ID for the employee with 'Manager' designation is:" + emp_id);  
    }  
    catch (Exception e)  
    {  
          Console.WriteLine("Exception: " + e.Message);  
          throw;  
    }  
    ```  
  
    > [!NOTE]
    >  Por simplicidad, la **empleado** tabla tiene solo un empleado con la designación de "Administrador". Si la tabla de destino tiene más empleados con la designación del mismo, debe definir la función en consecuencia.  
  
7.  Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  Compile el proyecto y, a continuación, ejecútelo. La aplicación muestra el identificador de empleado del empleado con la designación de "Administrador".  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)