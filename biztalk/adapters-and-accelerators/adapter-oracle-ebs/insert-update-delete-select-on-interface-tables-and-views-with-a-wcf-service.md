---
title: Insertar, actualizar, eliminar o seleccionar operaciones en tablas de interfaz y vistas que usan el modelo de servicio WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae613c0e-4d9a-4c66-99e4-dd0443f1d495
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fc9e3968b760be10b428e39662ec3d09db490cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-or-select-operations-on-interface-tables-and-views-using-the-wcf-service-model"></a>Insertar, actualizar, eliminar o seleccionar operaciones en tablas de interfaz y vistas que usan el modelo de servicio WCF
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] detecta un conjunto de operaciones básicas de Insert, Select, Update y Delete en tablas de interfaz. Mediante el uso de estas operaciones, puede realizar simple Insert, Select, Update y eliminar instrucciones calificadas por una cláusula WHERE en una tabla de la interfaz de destino. Este tema proporciona instrucciones sobre cómo realizar estas operaciones mediante el modelo de servicio WCF.  
  
> [!NOTE]
>  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite solo las operaciones en las vistas de interfaz de selección.  
  
 Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [operaciones en tablas de interfaz y vistas de interfaz](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema realiza operaciones en la tabla de interfaz MS_SAMPLE_EMPLOYEE. La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Obtener un ejemplo, **Interface_Table_Ops**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF que se genera para las operaciones básicas que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] detecta se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.  
  
|Artefacto|Nombre de cliente WCF|  
|--------------|---------------------|  
|Tablas de interfaz|InterfaceTables_ [APP_NAME] _ [esquema]\_cliente [NombreTabla]|  
|Vistas de interfaz|InterfaceViews_ [APP_NAME] _ [esquema]\_cliente [VIEW_NAME]|  
  
 [APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, buscar.  
  
 [Esquema] = colección de artefactos; Por ejemplo, las aplicaciones.  
  
 [NombreTabla] = el nombre de la tabla. Por ejemplo, MS_SAMPLE_EMPLOYEE.  
  
 [VIEW_NAME] = el nombre de la vista; Por ejemplo, MS_SAMPLE_EMPLOYEE_View.  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>Firma de método para invocar operaciones en tablas  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Insert|cadena Insert (InsertRecord] conjunto de registros);|  
|Select|SelectRecord [] seleccione (string COLUMN_NAMES, cadena de filtro);|  
|Update|cadena Update (UpdateRecord RECORDSET, cadena de filtro);|  
|DELETE|cadena Delete (cadena de filtro);|  
  
 Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para la eliminación, inserción, seleccione y operaciones Update en la tabla de interfaz MS_SAMPLE_EMPLOYEE en el esquema de aplicaciones predeterminado.  
  
```  
public partial class InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient : System.ServiceModel.ClientBase<InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE>, InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEE {      
    public SelectRecord[] Select(string COLUMN_NAMES, string FILTER);  
  
    public string Insert(InsertRecord[] RECORDSET);  
  
    public string Update(UpdateRecord RECORDSET, string FILTER);  
  
    public string Delete(string FILTER);  
}  
```  
  
 En este fragmento de código, **InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
### <a name="parameters-for-table-operations"></a>Parámetros para las operaciones de tabla  
 Esta sección proporciona los parámetros requeridos por cada operación de tabla  
  
 **Seleccione la operación**  
  
|COLUMN_NAMES|FILTER|  
|-------------------|------------|  
|Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "EMP_NO, designación". La lista de columnas especifica las columnas de destino que se deben devolver en el conjunto de resultados. Las columnas no especificadas en la lista de columnas se establecerá con sus valores predeterminados de .NET en el conjunto de registros devuelto. Para las columnas nillable, este valor es **null**.|El contenido de una cláusula WHERE que especifica las filas de destino de la consulta; Por ejemplo, "designación = 'Administrador'". Puede establecer este parámetro en **null** para devolver todas las filas de destino.|  
  
 El valor devuelto para una operación de selección es un conjunto de resultados fuertemente tipadas que contiene las filas y columnas especificadas.  
  
 **Operación de inserción**  
  
|Insertar tipo de operación|CONJUNTO DE REGISTROS|  
|---------------------------|---------------|  
|Registro de varios|Una colección de INSERTRECORDS que se deben insertar en la tabla.|  
  
 El valor devuelto para una operación de inserción es el número de filas insertadas.  
  
 **La operación de actualización**  
  
|CONJUNTO DE REGISTROS|FILTER|  
|---------------|------------|  
|Una colección de registros que deben actualizarse en la tabla.|El contenido de una cláusula WHERE que especifica las filas de destino de la consulta; Por ejemplo, "designación = 'Administrador'". Puede establecer este parámetro en **null** para devolver todas las filas de destino.|  
  
 El valor devuelto para una operación de actualización es el número de filas actualizadas.  
  
 **La operación de eliminación**  
  
 La operación de Delete toma como entrada una cláusula WHERE que especifica las filas que se va a eliminar. El valor devuelto para una operación de eliminación es el número de filas eliminadas.  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-interface-tables-and-interface-views"></a>Creación de un cliente WCF para invocar operaciones en tablas de interfaz y vistas de la interfaz  
 El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general del modelo del canal WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md). En esta sección se describe cómo crear un cliente WCF para invocar básicas Insert, Select, Update, las operaciones Delete en una tabla de interfaz.  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a>Para crear un cliente WCF para llevar a cabo operaciones en tablas  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la inserción, Select, Update y, en la tabla de interfaz MS_SAMPLE_EMPLOYEE la operación de eliminación. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
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
    InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient client = new InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient(binding, address);  
    ```  
  
     En este fragmento de código, `InterfaceTables_FND_APPS_MS_SAMPLE_EMPLOYEEClient` es el cliente WCF definido en OracleEBSBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!NOTE]
    >  En este fragmento, especificar explícitamente la dirección de enlace y el punto de conexión en el código de aplicación. Puede utilizar estos valores desde el archivo de configuración del aplicación, app.config, también generado el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).  
  
6.  Establezca las credenciales para el cliente.  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
7.  Dado que está realizando una operación en una tabla de interfaz, debe establecer el contexto de la aplicación. En este ejemplo, para establecer el contexto de la aplicación, especifique la **OracleUserName**, **OraclePassword**, y **OracleEBSResponsibilityName** propiedades de enlace. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
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
  
9. Invocar la operación de inserción en la tabla MS_SAMPLE_EMPLOYEE.  
  
    ```  
    Console.WriteLine("The application will insert a record in the MS_SAMPLE_EMPLOYEE interface table");  
  
    // The date values cannot contain time zone information. Hence, you must use  
    // DateTimeKind.Unspecified to not include the time zone information.  
    DateTime date = new DateTime(DateTime.Now.Ticks, DateTimeKind.Unspecified);  
  
    string result;  
  
    InsertRecord[] recordSet = new InsertRecord[1];  
  
    EMP_NO__COMPLEX_TYPE emp_no = new EMP_NO__COMPLEX_TYPE();  
    emp_no.Value = "10007";  
  
    NAME__COMPLEX_TYPE name = new NAME__COMPLEX_TYPE();  
    name.Value = "John Smith";  
  
    DESIGNATION__COMPLEX_TYPE desig = new DESIGNATION__COMPLEX_TYPE();  
    desig.Value = "Manager";  
  
    SALARY__COMPLEX_TYPE salary = new SALARY__COMPLEX_TYPE();  
    salary.Value = "500000";  
  
    JOIN_DATE__COMPLEX_TYPE doj = new JOIN_DATE__COMPLEX_TYPE();  
    doj.Value = date;  
  
    recordSet[0] = new InsertRecord();  
    recordSet[0].EMP_NO = emp_no;  
    recordSet[0].NAME = name;  
    recordSet[0].DESIGNATION = desig;  
    recordSet[0].SALARY = salary;  
    recordSet[0].JOIN_DATE = doj;  
  
    try  
    {  
       result = client.Insert(recordSet);   
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
  
    Console.WriteLine("Number of records inserted= " + result);  
    Console.WriteLine("Press any key to continue...");  
    Console.ReadLine();  
  
    ```  
  
     Puede reemplazar el fragmento de código anterior para llevar a cabo Select, Update o Delete también las operaciones. También puede agregar los fragmentos de código para llevar a cabo todas las operaciones en una sola aplicación. Para fragmentos de código sobre cómo realizar estas operaciones, vea [Seleccionar operación](#BKMK_Select), [operación de actualización](#BKMK_Update), y [operación Delete](#BKMK_Delete) respectivamente.  
  
10. Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. Compile el proyecto y, a continuación, ejecútelo. La aplicación inserta un registro en la tabla MS_SAMPLE_EMPLOYEE.  
  
###  <a name="BKMK_Select"></a>Seleccione la operación  
 El código siguiente muestra una operación de selección que tenga como destino de la tabla de interfaz MS_SAMPLE_EMPLOYEE. La operación de selección, selecciona el último registro insertado en la tabla. El registro devuelto se escribe en la consola.  
  
```  
Console.WriteLine("The application will now select the last inserted record");  
SelectRecord[] selectRecords;  
try  
{  
   selectRecords = client.Select("*", "WHERE EMP_NO LIKE 10007");  
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
   Console.WriteLine("Employee ID         : " + selectRecords[i].EMP_NO);  
   Console.WriteLine("Employee Name       : " + selectRecords[i].NAME);  
   Console.WriteLine("Employee Desigation : " + selectRecords[i].DESIGNATION);  
   Console.WriteLine("Employee Salary     : " + selectRecords[i].SALARY);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###  <a name="BKMK_Update"></a>La operación de actualización  
 El código siguiente muestra una operación de actualización que tenga como destino de la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
```  
Console.WriteLine("The application will now update the employee name in the newly inserted record");  
string recordsUpdated;  
UpdateRecord updateRecordSet = new UpdateRecord();  
updateRecordSet.NAME = "Tom Smith";  
updateRecordSet.DESIGNATION = "Accountant";  
  
try  
{  
   recordsUpdated = client.Update(updateRecordSet, "WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("No of records updated: " + recordsUpdated);  
Console.WriteLine("Press any key to continue...");  
Console.ReadLine();  
```  
  
###  <a name="BKMK_Delete"></a>La operación de eliminación  
 El código siguiente muestra una operación de eliminación que tenga como destino de la tabla de interfaz MS_SAMPLE_EMPLOYEE.  
  
```  
Console.WriteLine("The sample will now delete the record that it first inserted");  
string deletedRecords;  
try  
{  
   deletedRecords = client.Delete("WHERE EMP_NO LIKE 10007");  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
Console.WriteLine("No of records deleted: " + deletedRecords);  
Console.WriteLine("Press any key to exit...");  
Console.ReadLine();  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)