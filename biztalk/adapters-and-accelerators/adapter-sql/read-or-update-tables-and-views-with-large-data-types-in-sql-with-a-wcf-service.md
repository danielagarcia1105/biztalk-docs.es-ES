---
title: Ejecutar operaciones en tablas y vistas con tipos de datos grandes en SQL mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d33e17c-e09e-4a57-9acc-43095e67ed8c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2bfb30c01113e868bd6a662d004639645e29746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992485"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a>Ejecutar operaciones en tablas y vistas con tipos de datos grandes en SQL mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes del adaptador para leer y actualizar datos en columnas de tipos de datos de gran tamaño, es decir, varchar (max), nvarchar (max) o varbinary (max). Para leer datos de esas columnas, los clientes del adaptador pueden usar la operación de selección. Para insertar o actualizar datos en dichas columnas, el adaptador expone un conjunto\<*column_name* \> operación, donde \< *column_name* \> es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max).  
  
 Además, en SQL Server, puede hacer que la columna varbinay(max) almacene datos no estructurados como documentos de texto e imágenes. Estos datos no estructurados se denominan datos FILESTREAM. Los datos de FILESTREAM se pueden almacenar como archivos en el sistema de archivos. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite al cliente especificar datos FILESTREAM en columnas de tipo varbinary (max). [Almacenamiento de FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) tiene más información. 
  
 Este tema proporciona información acerca de ciertas tareas que debe realizar en el equipo que ejecuta SQL Server y el equipo que ejecuta el cliente de adaptador para que pueda insertar o actualizar los datos FILESTREAM. En este tema también proporciona instrucciones sobre cómo realizar conjunto\<*column_name* \> operaciones para insertar datos FILESTREAM.  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que se hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe realizar las tareas siguientes en el equipo que ejecuta SQL Server y el equipo que ejecuta al cliente del adaptador.  
  
- **En el equipo que ejecuta SQL Server**  
  
  -   Debe habilitar FILESTREAM en la instancia de SQL Server. Consulte [habilitar y configurar FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).
  
  -   Debe crear una base de datos habilitada para FILESTREAM. Consulte [crear una base de datos habilitada para FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).
  
  -   Debe tener una tabla para almacenar datos FILESTREAM. Consulte [crear una tabla para almacenar datos FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),
  
- **En el equipo que ejecuta al cliente de adaptador**  
  
  -   Debe tener instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccione **SDK de conectividad de cliente SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  
  
  Después de completar estas tareas, ya está listo para insertar o actualizar los datos FILESTREAM en tablas de base de datos de SQL Server.  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>Cómo en este tema muestra las operaciones en tipos de datos de gran tamaño  
 Para demostrar cómo realizar conjunto\<*column_name* \> operaciones en tablas con tipos de datos de gran tamaño, toman una tabla, **registros**, que tiene columnas **Id** y **documento**:  
  
-   El **registros** tabla con todos los datos, se crea mediante la ejecución de la secuencia de comandos SQL con los ejemplos. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
-   El **Id** la columna es de tipo uniqueidentifier y toma un GUID. Suponga que el **Id** columna ya tiene un GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`'.  
  
-   El **documento** columna es de tipo varbinary (max). Para actualizar el **documento** expone el adaptador de columna, el **SetDocument** operación.  
  
> [!NOTE]
>  Para SQL Server, para demostrar operaciones de FILESTREAM, se asume que el **documento** columna puede almacenar datos FILESTREAM.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 El ejemplo de este tema realiza operaciones en el **registros** tabla. El **registros** se crea una tabla mediante la ejecución de la secuencia de comandos SQL con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Un ejemplo, **Records_FILESTREAM_Op**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para las operaciones en los datos de gran tamaño de los tipos que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta, se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Table|Cliente de TableOp_ [esquema] _ [NombreTabla]|  
|Ver|ViewOp_[Schema]_[VIEW_NAME]Client|  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a>Firma del método para invocar operaciones en las columnas de tipos de datos de gran tamaño  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre reemplazan las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Establecer\<*column_name*\>|Conjunto de void público\<*column_name*\>(filtro, byte [] datos de cadena);|  
  
 \<*column_name* \> = nombre de la columna de tipo de datos de gran tamaño.  
  
 Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para el **SetDocument** operación en el **registros** tabla bajo el esquema predeterminado de "dbo".  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 En este fragmento de código, **TableOp_dbo_RecordsClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a>Parámetros para las operaciones en las columnas de tipos de datos de gran tamaño  
 Esta sección proporcionan los parámetros requeridos por el conjunto\<*column_name* \> operación.  
  
|Nombre del parámetro|Descripción|  
|--------------------|-----------------|  
|cadena de filtro|Especifica la cláusula WHERE se basa en el que el adaptador actualiza el registro de la columna de tipo de datos de gran tamaño.|  
|Byte [] datos|Especifica el valor que se debe actualizar para la columna de tipo de datos de gran tamaño.|  
  
 El conjunto\<*column_name* \> operación no devuelve ningún valor.  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a>Creación de un cliente WCF para invocar operaciones en las columnas de tipos de datos de gran tamaño  
 El conjunto genérico de las acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF implica un conjunto de tareas que se describen en [general del modelo de servicio WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md). En esta sección se describe cómo crear un cliente WCF para invocar el **SetDocument** operación en el **registros** tabla. Expone el adaptador el **SetDocument** operación para actualizar datos en columnas de tipos de datos de gran tamaño.  
  
#### <a name="to-create-a-wcf-client"></a>Para crear a un cliente WCF  
  
1. Cree un proyecto de Visual C# en Visual Studio. Este tema, cree una aplicación de consola.  
  
2. Generar la clase de cliente WCF para la **SetDocument** operación en el **registros** tabla. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
3. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, y `System.Transactions`.  
  
4. Abra el archivo Program.cs y agregue el `System.Transactions` espacio de nombres.  
  
5. En el archivo Program.cs, cree a un cliente como se describe en el siguiente fragmento.  
  
   ```  
  
             TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
   client.ClientCredentials.UserName.UserName = "";  
   client.ClientCredentials.UserName.Password = "";  
  
   ```  
  
    En este fragmento de código, `TableOp_dbo_RecordsClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_TableOp_dbo_Records` es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
   > [!CAUTION]
   >  Para realizar operaciones en los datos FILESTREAM, siempre debe conectarse a SQL Server mediante la autenticación de Windows. Para conectarse mediante la autenticación de Windows, debe proporcionar un nombre de usuario vacío y una contraseña, como se muestra en el fragmento de código anterior. Además, antes de usar la autenticación de Windows para conectarse a SQL Server, debe haber realizado los pasos mencionados en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
   > [!NOTE]
   >  En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las diferentes maneras de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
6. Abra al cliente como se describe en el siguiente fragmento:  
  
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
  
7. Invocar el **SetDocument** operación en el **registros** tabla.  
  
   > [!CAUTION]
   >  El conjunto<em>< nombre_columna ></em> operaciones deben realizarse siempre en una transacción. Para asegurarse de esto, el conjunto<em>< nombre_columna ></em> se debe invocar la operación dentro de un ámbito de transacción y el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true**en el archivo app.config.  
  
   ```  
   using (TransactionScope tx = new TransactionScope())  
   {  
       string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
       byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
       client.SetDocument(filter, data);  
       tx.Complete();  
   }  
   ```  
  
    En este caso, la aplicación convierte la cadena "Datos de ejemplo" en una cadena codificada en base64 y lo actualiza en el registro que satisface los criterios de filtro.  
  
8. Cierre al cliente como se describe en el siguiente fragmento:  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
9. Compile el proyecto y, a continuación, ejecútelo. Las actualizaciones de la aplicación la **documento** columna en el **registros** tabla.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)