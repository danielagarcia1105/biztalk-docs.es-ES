---
title: Invocar funciones con valores de tabla en SQL Server mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48688bcc-36b4-4cc1-b078-17e7a5e1cf8c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a736a82e57f71568f8718a6e4d41e7b649004120
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model"></a>Invocar funciones con valores de tabla en SQL Server mediante el modelo de servicio WCF
Puede usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en una aplicación de .NET mediante el modelo de servicio WCF para invocar funciones con valores de tabla en SQL Server. El adaptador expone las funciones con valores de tabla como métodos que se pueden invocar directamente en SQL Server. Para obtener más información acerca del modo en que el adaptador admite funciones escalares, consulte [Execute Table-Valued funciones en SQL Server mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/execute-table-valued-functions-in-sql-server-using-the-sql-adapter.md).  
  
 Este tema muestra cómo invocar la función TVF_EMPLOYEE en una base de datos de SQL Server. La función TVF_EMPLOYEE toma la designación de un empleado en el **empleado** tabla y devuelve el registro del empleado. La función TVF_EMPLOYEE y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema, invoca la función con valores de tabla TVF_EMPLOYEE en el **empleado** tabla. Función TVF_EMPLOYEE y **empleado** tabla se crean al ejecutar el script SQL que se proporciona con los ejemplos. Obtener un ejemplo, **TableFunction_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar la función escalar en SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Función con valores de tabla|Cliente TableValuedFunctions_ [esquema]|  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
### <a name="method-signature-for-invoking-table-valued-functions"></a>Firma de método para llamar a funciones con valores de tabla  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Nombre de la función con valores de tabla|público [NAMESPACE] [nombre_función] [] [nombre_función] (parámetro1, parámetro2,...\)|  
  
 [NAMESPACE] = el espacio de nombres, por ejemplo, schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE  
  
 [Nombre_función] = nombre de la función con valores de tabla.  
  
 Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **TVF_EMPLOYEE** funciones escalares, en el esquema dbo, que toma la designación de empleado como parámetro y devuelve el empleado registro.  
  
```  
public partial class TableValuedFunctions_dboClient : System.ServiceModel.ClientBase<TableValuedFunctions_dbo>, TableValuedFunctions_dbo {      
    public schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] TVF_EMPLOYEE(string emp_desig);  
}  
```  
  
 En este fragmento de código, **TableValuedFunctions_dboClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
### <a name="parameters-for-invoking-table-valued-functions"></a>Parámetros para llamar a funciones con valores de tabla  
 Los parámetros para los métodos expuestos por el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para invocar una función con valores de tabla son los mismos que los parámetros definidos en la definición de función en SQL Server. Por ejemplo, el parámetro para invocar una función con valores de tabla de TVF_EMPLOYEE es emp_desig y toma la designación de un empleado.  
  
 Una vez más, el valor devuelto para una función con valores de tabla es igual que el valor devuelto definido en la definición de función en SQL Server. Por ejemplo, el valor devuelto para la función TVF_EMPLOYEE es una matriz de registros de tipo schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE [].  
  
## <a name="creating-a-wcf-client-to-invoke-table-valued-functions"></a>Creación de un cliente WCF para invocar funciones con valores de tabla  
 El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](overview-of-the-wcf-service-model-with-the-sql-adapter.md). Esta sección describe cómo crear un cliente WCF para invocar la **TVF_EMPLOYEE** función con valores de tabla.  
  
 
1.  Crear un proyecto de Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsVStudioNoVersion-md.md)]. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la **TVF_EMPLOYEE** función escalar. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.  
  
4.  Abra Program.cs y cree a un cliente tal y como se describe en el siguiente fragmento.  
  
    ```  
  
              TableValuedFunctions_dboClient client = new TableValuedFunctions_dboClient("SqlAdapterBinding_TableValuedFunctions_dbo");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     En este fragmento de código, `TableValuedFunctions_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_TableValuedFunctions_dbo`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
    > [!NOTE]
    >  En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las distintas formas de especificar, a continuación, enlace de cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](configure-a-client-binding-for-the-sql-adapter.md).  
  
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
  
6.  Invocar la **TVF_EMPLOYEE** función para recuperar todos los registros de empleados con la designación "Administrador".  
  
    ```  
    Console.WriteLine("Invoking the TVF_EMPLOYEE function");  
    schemas.microsoft.com.Sql._2008._05.Types.TableFunctionReturnTables.dbo.TVF_EMPLOYEE[] emp_details;  
    string emp_designation = "Manager";  
  
    try  
    {  
        emp_details = client.TVF_EMPLOYEE(emp_designation);  
    }  
    catch (Exception e)  
    {  
        Console.WriteLine("Exception: " + e.Message);  
        throw;  
    }  
    Console.WriteLine("The details for the employee with the 'Manager' designation are:");  
    Console.WriteLine("*******************************************************************");  
    for (int i = 0; i < emp_details.Length; i++)  
    {  
        Console.WriteLine("Employee ID        : " + emp_details[i].Employee_ID);  
        Console.WriteLine("Employee Name      : " + emp_details[i].Name);  
        Console.WriteLine("Employee Desigation: " + emp_details[i].Designation);  
        Console.WriteLine("Employee Salary    : " + emp_details[i].Salary);  
        Console.WriteLine();  
    }  
    ```  
  
7.  Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  Compile el proyecto y, a continuación, ejecútelo. La aplicación muestra el identificador de empleado, el nombre y el salario de todos los empleados con una designación de "Administrador".  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio de WCF](develop-sql-applications-using-the-wcf-service-model.md)