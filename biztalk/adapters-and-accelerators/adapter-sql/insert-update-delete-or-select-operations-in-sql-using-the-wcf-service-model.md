---
title: Insertar, actualizar, eliminar o seleccionar las operaciones de SQL mediante el modelo de servicio WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2bc522a1b0b60a9ba0b8407228dd1db65c4e6f0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a>Insertar, actualizar, eliminar o seleccionar las operaciones de SQL mediante el modelo de servicio WCF
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] detecta un conjunto de operaciones básicas de Insert, Select, Update y Delete en vistas y tablas de base de datos de SQL Server. Mediante el uso de estas operaciones, puede realizar simple SQL Insert, Select, Update y eliminar instrucciones que califican Where cláusula en una tabla de destino o la vista. Este tema proporciona instrucciones sobre cómo realizar estas operaciones mediante el modelo de servicio WCF.  
  
 Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, vea [Insert, Update, Delete y seleccione las operaciones en tablas y vistas con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar la aplicación.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema realiza operaciones en la tabla de empleados. La tabla de empleados se crea al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Obtener un ejemplo, **EmployeeBasicOps**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF que se genera para las operaciones básicas de SQL que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Table|TableOp_[Schema]_[TABLE_NAME]Client|  
|Ver|ViewOp_[Schema]_[VIEW_NAME]Client|  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
 [NombreTabla] = el nombre de la tabla. Por ejemplo, el empleado.  
  
 [VIEW_NAME] = el nombre de la vista; Por ejemplo, Employee_View.  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>Firma de método para invocar operaciones en tablas  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Insert|long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);|  
|Select|[TABLE_NS]. [NOMBRETABLA] [] Seleccione (cadena de columnas, la cadena de consulta);|  
|Update|int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);|  
|Delete|int Delete ([TABLE_NS]. [ Filas NombreTabla] []);|  
  
 [TABLE_NS] = el nombre del espacio de nombres de tabla; Por ejemplo, schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee.  
  
 [NombreTabla] = el nombre de la tabla. Por ejemplo, el empleado.  
  
 Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para las operaciones Delete, Insert, Select y Update en la tabla de empleados en el esquema predeterminado "dbo".  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 En este fragmento de código, TableOp_dbo_EmployeeClient es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
### <a name="parameters-for-table-operations"></a>Parámetros para las operaciones de tabla  
 Esta sección proporciona los parámetros requeridos por cada operación de tabla  
  
 **Operación de inserción**  
  
|Insertar tipo de operación|CONJUNTO DE REGISTROS|  
|---------------------------|---------------|  
|Registro de varios|Una colección de INSERTRECORDS que se deben insertar en la tabla.|  
  
 La operación de inserción devuelve una matriz de tipo de datos Long y almacena los valores de identidad de las filas insertadas, si lo hay. Si no hay ninguna columna de identidad en una tabla, el valor devuelto es NULL.  
  
 **Seleccione la operación**  
  
|COLUMN_NAMES|QUERY|  
|-------------------|-----------|  
|Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "IdDeEmpleado, designación". La lista de columnas especifica las columnas de destino que se deben devolver en el conjunto de resultados. Las columnas no especificadas en la lista de columnas se establecerá con sus valores predeterminados de .NET en el conjunto de registros devuelto. Para las columnas nillable, este valor es **null**.|El contenido de una cláusula WHERE de SQL que especifica las filas de destino de la consulta; Por ejemplo, "designación = 'Administrador'". Puede establecer este parámetro en **null** para devolver todas las filas de destino.|  
  
 El valor devuelto de la operación seleccionada es un conjunto de resultados fuertemente tipadas que contiene las columnas especificadas y las filas de la tabla de destino o la vista.  
  
 **La operación de actualización**  
  
|Primera fila del par|Segunda fila del par|  
|---------------------------|----------------------------|  
|El primer registro del registro par corresponde a los nuevos valores que deben actualizarse, es decir, se corresponde con la cláusula SET de la instrucción UPDATE. Esto se puede establecer utilizando `RowPair.After`.|El segundo registro del par de registro corresponde a los valores anteriores de las filas, es decir, corresponde a la cláusula WHERE de la instrucción UPDATE. Esto se puede establecer utilizando `RowPair.Before`.|  
  
 El valor devuelto de la operación de actualización es de tipo de dato Int32 e indica el número de filas actualizadas.  
  
> [!IMPORTANT]
>  Al especificar el registro que debe actualizarse, debe proporcionar valores para todas las columnas, incluso si no se actualizan todos los valores. Por ejemplo, si una fila tiene cinco columnas y la operación de actualización actualiza solo 2 columnas, como parte de RowPair.Before, debe pasar todos los valores de 5 columna. Sin embargo, para RowPair.After, puede especificar solo las columnas que se actualizará.  
  
 **La operación de eliminación**  
  
 La operación de eliminación se toma como matriz de entrada fuertemente tipada de registros. El valor devuelto de la operación de eliminación es del tipo de dato Int32 e indica el número de filas eliminadas.  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a>Creación de un cliente WCF para invocar operaciones en tablas y vistas  
 El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md). En esta sección se describe cómo crear un cliente WCF para invocar básicas Insert, Select, Update, las operaciones Delete en una tabla.  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>Para crear un cliente WCF para llevar a cabo operaciones en tablas  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la inserción, Select, Update y, en la tabla de empleados de la operación de eliminación. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
    > [!IMPORTANT]
    >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.  
  
4.  Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.  
  
    ```  
  
              TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     En este fragmento de código, `TableOp_dbo_EmployeeClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_TableOp_dbo_Employee` es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
    > [!NOTE]
    >  En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
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
  
6.  Invocar la operación de inserción en la tabla de empleados.  
  
    ```  
    long[] recordsInserted;  
  
    schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] insertRecord =  
    new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
    insertRecord[0] = new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
    insertRecord[0].Name = "John Smith";  
    insertRecord[0].Designation = "Manager";  
    insertRecord[0].Salary = 500000;  
  
    try  
    {  
       Console.WriteLine("Inserting new table entry...");  
       recordsInserted = client.Insert(insertRecord);  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Record inserted");  
    Console.WriteLine("Press any key to continue ...");  
    Console.ReadLine();  
    ```  
  
     Puede reemplazar el fragmento de código anterior para llevar a cabo Select, Update o Delete también las operaciones. También puede agregar los fragmentos de código para llevar a cabo todas las operaciones en una sola aplicación. Para fragmentos de código sobre cómo realizar estas operaciones.  
  
7.  Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  Compile el proyecto y, a continuación, ejecútelo. La aplicación inserta un registro en la tabla de empleados.  
  
###   <a name="select-operation"></a>Seleccione la operación  
 El código siguiente muestra una operación de selección que tenga como destino de la tabla de empleados. La operación de selección, selecciona el último registro insertado en la tabla. Los registros devueltos se escriben en la consola.  
  
```  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
try  
{  
   Console.WriteLine("Selecting Row...");  
   selectRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
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
   Console.WriteLine("Employee ID        : " + selectRecords[i].Employee_ID);  
   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
   Console.WriteLine("Employee Desigation: " + selectRecords[i].Designation);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="update-operation"></a>La operación de actualización  
 El código siguiente muestra una operación de actualización que tenga como destino de la tabla de empleados.  
  
```  
int result;  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair updateRecordPair =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair();  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee updateRecord =   
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] updateArray =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[1];  
  
updateRecord = insertRecord[0];  
updateRecord.Name = "Jeff Smith";  
  
updateRecordPair.After = updateRecord;  
updateRecordPair.Before = selectRecords[0];  
  
updateArray[0] = updateRecordPair;  
  
try  
{  
   Console.WriteLine("Updating the database...");  
   result = client.Update(updateArray);  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("Updated Record for {0}", updateRecordPair.Before.Name);  
Console.WriteLine("The new name for the employee is {0}", updateRecordPair.After.Name);  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="delete-operation"></a>Operación de eliminación  
 El código siguiente muestra una operación de eliminación que tenga como destino de la tabla de empleados.  
  
```  
int deleteSuccess;  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] deleteRecords =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
deleteRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
  
Console.WriteLine("Following employees will be deleted from the database:");  
for (int i = 0; i < deleteRecords.Length; i++)  
{  
   Console.WriteLine("Name: {0}", deleteRecords[i].Name);  
}  
Console.WriteLine("Press any key to begin deletion...");  
Console.ReadLine();  
  
try  
{  
   Console.WriteLine("Deleting employee record...");  
   deleteSuccess = client.Delete(deleteRecords);  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
```  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)