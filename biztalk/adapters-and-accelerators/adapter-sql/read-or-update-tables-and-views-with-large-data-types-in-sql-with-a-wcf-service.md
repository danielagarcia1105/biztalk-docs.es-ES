---
title: Ejecutar operaciones en tablas y vistas con los tipos de datos grandes en SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
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
ms.openlocfilehash: 1da0def828c1dbfa8511dc61b529fa02cb53ca5a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967130"
---
# <a name="run-operations-on-tables-and-views-with-large-data-types-in-sql-using-the-wcf-service-model"></a>Ejecutar operaciones en tablas y vistas con los tipos de datos grandes en SQL mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite a los clientes de adaptador para leer y actualizar datos en columnas de tipos de datos de gran tamaño, es decir, varchar (max), nvarchar (max) o varbinary (max). Para leer datos de esas columnas, los clientes de adaptador pueden usar la operación de selección. Para insertar o actualizar datos en estas columnas, el adaptador expone un conjunto\<*column_name* \> operación, donde \< *column_name* \> es el nombre de la columna de tipo varchar (max), nvarchar (max) o varbinary (max).  
  
 Además, en SQL Server, puede tener la columna varbinay(max) almacenar datos no estructurados, como documentos de texto e imágenes. Los datos no estructurados se denominan datos FILESTREAM. Los datos de FILESTREAM se pueden almacenar como archivos en el sistema de archivos. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] permite al cliente especificar datos FILESTREAM en columnas de tipo varbinary (max). [Almacenamiento de FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/filestream-sql-server) se proporciona más información. 
  
 Este tema proporciona información acerca de ciertas tareas que debe realizar en el equipo que ejecuta SQL Server y el equipo que ejecuta el cliente de adaptador para que pueda insertar o actualizar los datos FILESTREAM. Este tema también proporciona instrucciones acerca de cómo realizar conjunto\<*column_name* \> operaciones para insertar datos FILESTREAM.  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe realizar las siguientes tareas en el equipo que ejecuta SQL Server y el equipo que ejecuta al cliente de adaptador.  
  
-   **En el equipo que ejecuta SQL Server**  
  
    -   Debe habilitar FILESTREAM en la instancia de SQL Server. Vea [habilitar y configurar FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/enable-and-configure-filestream).
  
    -   Debe crear una base de datos habilitada para FILESTREAM. Vea [crear una base de datos habilitada para FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/create-a-filestream-enabled-database).
  
    -   Debe tener una tabla para almacenar datos FILESTREAM. Vea [crear una tabla para almacenar datos FILESTREAM](https://docs.microsoft.com/sql/relational-databases/blob/create-a-table-for-storing-filestream-data),
  
-   **En el equipo que ejecuta al cliente de adaptador**  
  
    -   Debe tener instalado el SDK de conectividad de cliente de SQL. Puede instalar el SDK de conectividad de cliente de SQL, ejecute el programa de instalación de SQL Server y seleccionar **SDK de conectividad de cliente de SQL** en el **selección de características** página del asistente. El adaptador utiliza el sqlncli10.dll, instalado con el SDK de conectividad de cliente de SQL, para realizar operaciones de FILESTREAM.  
  
 Después de completar estas tareas, está preparado para insertar o actualizar los datos FILESTREAM en tablas de base de datos de SQL Server.  
  
## <a name="how-this-topic-demonstrates-operations-on-large-data-types"></a>Cómo en este tema muestra las operaciones en tipos de datos de gran tamaño  
 Para demostrar cómo realizar conjunto\<*column_name* \> operaciones en tablas con tipos de datos de gran tamaño, usan una tabla, **registros**, que tiene columnas **deId.** y **documento**:  
  
-   El **registros** tabla, con todos los datos, se crea al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información, consulte [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
-   El **identificador** columna es de tipo uniqueidentifier y toma un GUID. Se asume que el **identificador** columna ya tiene un GUID '`438B7B4C-5491-409F-BCC1-78817C399EC3`'.  
  
-   El **documento** columna es de tipo varbinary (max). Para actualizar la **documento** columna, el adaptador expone la **SetDocument** operación.  
  
> [!NOTE]
>  Para SQL Server, para demostrar operaciones de FILESTREAM, se asume que el **documento** columna puede almacenar datos FILESTREAM.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema realiza operaciones en el **registros** tabla. El **registros** tabla se crea al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Obtener un ejemplo, **Records_FILESTREAM_Op**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para las operaciones en datos de gran tamaño de los tipos que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] detecta, se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Tabla|Cliente de TableOp_ [esquema] _ [NombreTabla]|  
|Ver|Cliente de ViewOp_ [esquema] _ [VIEW_NAME]|  
  
 [Esquema] = artefactos de la colección de SQL Server; Por ejemplo, dbo.  
  
### <a name="method-signature-for-invoking-operations-on-columns-of-large-data-types"></a>Firma de método para llamar a operaciones en las columnas de tipos de datos de gran tamaño  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Establecer\<*column_name*\>|Set void público\<*column_name*\>(cadena de filtro, byte [] datos;)|  
  
 \<*column_name* \> = nombre de la columna de tipo de datos de gran tamaño.  
  
 Por ejemplo, el código siguiente muestra las firmas de método para generar una clase de cliente WCF para la **SetDocument** operación en el **registros** tabla en el esquema predeterminado de "dbo".  
  
```  
public partial class TableOp_dbo_RecordsClient : System.ServiceModel.ClientBase<TableOp_dbo_Records>, TableOp_dbo_Records {      
    public void SetDocument (string Filter, byte[] Data);  
}  
```  
  
 En este fragmento de código, **TableOp_dbo_RecordsClient** es el nombre de la clase WCF en el SqlAdapterBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
### <a name="parameters-for-operations-on-columns-of-large-data-types"></a>Parámetros para las operaciones en las columnas de tipos de datos de gran tamaño  
 Esta sección proporciona los parámetros requeridos por el conjunto de\<*column_name* \> operación.  
  
|Nombre del parámetro|Description|  
|--------------------|-----------------|  
|cadena de filtro|Especifica la cláusula WHERE basada en el que el adaptador actualiza el registro de la columna de tipo de datos de gran tamaño.|  
|Byte [] datos|Especifica el valor que se debe actualizar para la columna de tipo de datos de gran tamaño.|  
  
 El conjunto de\<*column_name* \> operación no devuelve ningún valor.  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-columns-of-large-data-types"></a>Creación de un cliente WCF para invocar operaciones en las columnas de tipos de datos de gran tamaño  
 El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio de WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md). Esta sección describe cómo crear un cliente WCF para invocar la **SetDocument** operación en el **registros** tabla. El adaptador expone la **SetDocument** operación para actualizar los datos en columnas de tipos de datos de gran tamaño.  
  
#### <a name="to-create-a-wcf-client"></a>Para crear a un cliente WCF  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la **SetDocument** operación en el **registros** tabla. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, y `System.Transactions`.  
  
4.  Abra el archivo Program.cs y agregue el `System.Transactions` espacio de nombres.  
  
5.  En Program.cs, cree a un cliente tal y como se describe en el siguiente fragmento.  
  
    ```  
  
              TableOp_dbo_RecordsClient client = new TableOp_dbo_RecordsClient("SqlAdapterBinding_TableOp_dbo_Records");  
    client.ClientCredentials.UserName.UserName = "";  
    client.ClientCredentials.UserName.Password = "";  
  
    ```  
  
     En este fragmento de código, `TableOp_dbo_RecordsClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_TableOp_dbo_Records`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
    > [!CAUTION]
    >  Para llevar a cabo operaciones en los datos FILESTREAM, siempre debe conectarse a SQL Server mediante autenticación de Windows. Para conectarse mediante la autenticación de Windows, debe proporcionar un nombre de usuario vacío y una contraseña, tal y como se muestra en el fragmento de código anterior. Además, antes de usar la autenticación de Windows para conectarse a SQL Server, debe haber realizado los pasos mencionados en [conectar con SQL Server Using Windows Authentication con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-using-windows-authentication-with-the-sql-adapter.md).  
  
    > [!NOTE]
    >  En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).  
  
6.  Abra al cliente como se describe en el siguiente fragmento:  
  
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
  
7.  Invocar la **SetDocument** operación en el **registros** tabla.  
  
    > [!CAUTION]
    >  El conjunto de *< column_name >* siempre se deben realizar las operaciones en una transacción. Para asegurarse de esto, el conjunto de *< column_name >* se debe invocar la operación dentro de un ámbito de transacción y el **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true**en el archivo app.config.  
  
    ```  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Id='438B7B4C-5491-409F-BCC1-78817C399EC3'";  
        byte[] data = ASCIIEncoding.ASCII.GetBytes("Sample data");  
        client.SetDocument(filter, data);  
        tx.Complete();  
    }  
    ```  
  
     En este caso, la aplicación convierte la cadena "Datos de ejemplo" en una cadena codificada en base64 y se actualiza en el registro que satisface los criterios de filtro.  
  
8.  Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
9. Compile el proyecto y, a continuación, ejecútelo. Las actualizaciones de la aplicación la **documento** columna en el **registros** tabla.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)