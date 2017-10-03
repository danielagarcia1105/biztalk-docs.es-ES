---
title: "Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3df95d78-3a9c-48c0-81ab-1f3206c5e3f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bceb236b660b80c1e46cb0410d799d994516c40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-an-insert-operation-on-a-table-in-sql-using-the-wcf-channel-model"></a>Ejecutar una operación de inserción en una tabla en SQL mediante el modelo de canal de WCF
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta un conjunto de operaciones básicas de Insert, Select, Update y Delete en vistas y tablas de base de datos de SQL Server. Mediante el uso de estas operaciones, puede realizar simple SQL Insert, Select, Update y eliminar instrucciones que califican Where cláusula en una tabla de destino o la vista. Este tema proporciona instrucciones sobre cómo realizar una operación de inserción en una tabla de base de datos de SQL Server mediante el modelo de canal WCF.  
  
 Para obtener más información sobre cómo el adaptador es compatible con estas operaciones, vea [Insert, Update, Delete y seleccione las operaciones en tablas y vistas con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md). Para obtener más información acerca de cómo realizar operaciones en SQL Server con el modelo del canal de WCF, vea [información general del modelo del canal WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema realiza operaciones en la tabla de empleados. La tabla de empleados se crea al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md). Obtener un ejemplo, **EmployeeInsertOp**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-insert-message"></a>El mensaje de inserción  
 Para realizar operaciones en la base de datos de SQL Server mediante el modelo de canal WCF, debe tener el mensaje de solicitud específico de la operación. El mensaje de solicitud para realizar una operación de inserción en la tabla de empleados en la base de datos de SQL Server es similar al siguiente:  
  
```  
<Insert xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
  <Rows>  
    <Employee xmlns="http://schemas.microsoft.com/Sql/2008/05/Types/Tables/dbo">  
      <Name>Tom Smith</Name>  
      <Designation>Manager</Designation>  
      <Salary>500000</Salary>  
   </Employee>  
  </Rows>  
</Insert>  
```  
  
 Este mensaje de solicitud inserta un registro con los detalles siguientes:  
  
```  
Name = Tom Smith  
Designation = Manager  
Salary = 500000  
```  
  
 Debe copiar el mensaje a un archivo, por ejemplo, InsertRequest.xml. Este archivo se usa en este ejemplo para enviar el mensaje de solicitud a SQL Server mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Para obtener más información acerca del esquema de mensaje para las operaciones en la tabla, vea [esquemas de mensaje para Insert, Update, Delete y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).  
  
## <a name="creating-a-wcf-channel-application"></a>Crear una aplicación de canal de WCF  
 Esta sección proporciona instrucciones sobre cómo crear una aplicación de canal WCF para realizar una operación de inserción en la tabla de empleados.  
  
#### <a name="to-create-a-wcf-channel-application-for-inserting-records-into-the-employee-table"></a>Para crear una aplicación de canal WCF para insertar registros en la tabla de empleados  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.  
  
3.  Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
    -   `Microsoft.Adapters.Sql`  
  
    -   `Microsoft.ServiceModel.Channels`  
  
    -   `System.ServiceModel`  
  
    -   `System.ServiceModel.Channels`  
  
    -   `System.Xml`  
  
4.  Crear el enlace y el punto de conexión.  
  
    ```  
    SqlAdapterBinding binding = new SqlAdapterBinding();  
    EndpointAddress address = new EndpointAddress("mssql://mysqlserver//mydatabase?");  
  
    ```  
  
5.  Cree y abra el generador de canales. Esta aplicación envía el mensaje de solicitud a SQL Server y recibe una respuesta, por lo tanto, debe implementar la interfaz IRequestChannel.  
  
    ```  
    ChannelFactory<IRequestChannel> factory = new ChannelFactory<IRequestChannel>(binding, address);  
    factory.Credentials.UserName.UserName = "<Enter user name here>";  
    factory.Credentials.UserName.Password = "<Enter password here>";  
    factory.Open();  
    ```  
  
6.  Crear y abrir el canal.  
  
    ```  
    IRequestChannel channel = factory.CreateChannel();  
    channel.Open();  
    ```  
  
7.  Crear y enviar el mensaje de solicitud.  
  
    ```  
    XmlReader readerIn;  
    Console.WriteLine("Creating the message");  
    try  
    {  
       readerIn = XmlReader.Create("InsertRequest.xml");  
       Console.WriteLine("Reader created");  
    }  
    catch (Exception ex)  
    {  
       Console.WriteLine("Exception: " + ex.Message);  
       throw;  
    }  
    Message messageIn = Message.CreateMessage(MessageVersion.Default, "TableOp/Insert/dbo/Employee", readerIn);  
    Message messageOut = channel.Request(messageIn);  
  
    ```  
  
     Al crear el mensaje de solicitud, debe especificar la acción de mensaje que indica la acción que realiza el adaptador en la tabla de SQL Server. Para llevar a cabo una operación de inserción en la tabla Employee, la acción de mensaje es `TableOp/Insert/dbo/Employee`. Para obtener información acerca de cómo se puede determinar la acción de mensaje para realizar diversas operaciones en tablas, vea [esquemas de mensaje para Insert, Update, Delete y seleccione las operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).  
  
8.  Obtiene el mensaje de respuesta.  
  
    ```  
    XmlReader readerOut = messageOut.GetReaderAtBodyContents();  
    XmlDocument doc = new XmlDocument();  
    doc.Load(readerOut);  
    doc.Save("C:\\Response.xml");  
    ```  
  
9. Cierre el mensaje, el canal y el generador de canales.  
  
    ```  
    messageOut.Close();  
    channel.Close();  
    factory.Close();  
    ```  
  
10. Generar el proyecto. Después de compilar el proyecto, debe realizar las siguientes tareas:  
  
    -   Copie el mensaje de solicitud, InsertRequest.xml, en la misma ubicación que el proyecto ejecutable. Normalmente, esta ubicación es \bin\Debug\ en el directorio del proyecto.  
  
    -   La tabla "Employee" utilizada en este ejemplo tiene una columna de tipo definido por el usuario Point (UDT). Por lo tanto, antes de ejecutar el proyecto, debe crear el ensamblado para el UDT Point tal y como se describe en [crear tipos](https://docs.microsoft.com/sql/relational-databases/clr-integration-database-objects-user-defined-types/creating-user-defined-types). También debe copiar la DLL en la misma ubicación que el proyecto ejecutable del ensamblado. Normalmente, esta ubicación es \bin\Debug\ en el directorio del proyecto.  
  
11. Ejecute la aplicación. El mensaje de respuesta, Response.xml, se guarda en la ubicación especificada en la aplicación. El mensaje de respuesta contiene el identificador del empleado recién agregado y es similar al siguiente:  
  
    ```  
    <InsertResponse xmlns="http://schemas.microsoft.com/Sql/2008/05/TableOp/dbo/Employee">  
      <InsertResult>  
        <long xmlns="http://schemas.microsoft.com/2003/10/Serialization/Arrays">10006</long>  
      </InsertResult>  
    </InsertResponse>  
    ```  
  
     Dado que la tabla Employee tiene la columna Id_Empleado como la columna de identidad, la operación de inserción devuelve el valor de la columna de identidad del registro recién insertado. Si no hay ninguna columna de identidad en una tabla, el valor devuelto es NULL.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)