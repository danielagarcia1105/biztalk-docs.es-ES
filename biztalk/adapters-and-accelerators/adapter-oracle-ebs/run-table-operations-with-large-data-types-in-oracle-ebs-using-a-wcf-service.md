---
title: "Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93ba3191-d234-424a-b2da-dcf384df4985
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b671f8fc124875eb5eadf119188d0ffe4c1a2a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="complete-operations-on-tables-with-large-data-types-in-oracle-e-business-suite-using-the-wcf-service-model"></a>Completar las operaciones en tablas con tipos de datos de gran tamaño en Oracle E-Business Suite mediante el modelo de servicio WCF
El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] permite a los clientes de adaptador realizar operaciones en tablas de interfaz y las vistas con tipos de datos de gran tamaño como BLOB, CLOB, NCLOB y BFILE.  
  
-   Para las columnas de tipo BLOB, CLOB y NCLOB, el adaptador permite a los clientes leer, así como actualizar los datos. El adaptador expone Read_\<*LOBColName*> y Update_\<*LOBColName*> operations para leer y actualizar datos respectivamente, donde \< *LOBColName*> es el nombre de columna con el tipo de datos de gran tamaño. Si hay más de una columna con el tipo de datos de gran tamaño en una tabla única interfaz, el adaptador expone muchas leerán y actualización operaciones para esa tabla de interfaz.  
  
-   Para las columnas de tipo BFILE, los clientes de adaptador solo pueden leer los datos. El adaptador expone Read_\<*LOBColName*> operación para leer datos de las columnas de tipo BFILE. Si hay más de una columna con el tipo de datos de gran tamaño en una tabla única interfaz, el adaptador se expone como muchas operaciones de la tabla de interfaz de lectura.  
  
 Para obtener más información acerca de estas operaciones, vea [operaciones en tablas de interfaz, vistas de interfaz, tablas y vistas que contienen LOB datos](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema actualiza una columna BLOB (fotografía) en la tabla de base de datos de cliente y, a continuación, recupera los datos de la misma columna. La tabla se crea mediante la ejecución de la secuencia de comandos que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Obtener un ejemplo, **LargeDataTypes_ServiceModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  
  
> [!NOTE]
>  Este tema enumeran las tareas detalladas de actualización y la lectura de las columnas de tipos de datos de gran tamaño en una tabla de base de datos. Debe realizar el mismo conjunto de tareas para actualizar y leer las columnas de tipos de datos de gran tamaño en una tabla de interfaz.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para las operaciones en tablas con tipos de datos de gran tamaño mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se basa en el nombre de la tabla, como se muestra en la tabla siguiente.  
  
|Artefacto|Nombre de cliente WCF|  
|--------------|---------------------|  
|Tablas de interfaz|InterfaceTables_ [APP_NAME] _ [esquema]\_cliente [NombreTabla]|  
  
 [APP_NAME] = nombre real de la aplicación de Oracle E-Business Suite; Por ejemplo, buscar.  
  
 [Esquema] = colección de artefactos; Por ejemplo, las aplicaciones.  
  
 [NombreTabla] = el nombre de la tabla. Por ejemplo, MS_SAMPLE_EMPLOYEE.  
  
 [VIEW_NAME] = el nombre de la vista; Por ejemplo, MS_SAMPLE_EMPLOYEE_View.  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a>Firma de método para invocar operaciones en tablas  
 La siguiente tabla muestra las firmas de método para las operaciones básicas en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Update_\<*column_name*>|Update_ void público\<*column_name*> (cadena de filtro, byte [] datos;)|  
|Read_\<*column_name*>|pública System.IO.Stream Read_\<*column_name*>(string FILTER);|  
  
 Por ejemplo, el código siguiente muestra las firmas de método para una clase de cliente WCF generado para las operaciones de Update_PHOTO y Read_PHOTO en la tabla de base de datos de cliente en el esquema de aplicaciones.  
  
```  
public partial class Tables_APPS_CUSTOMERClient : System.ServiceModel.ClientBase<Tables_APPS_CUSTOMER>, Tables_APPS_CUSTOMER {      
  
    public void Update_PHOTO(string FILTER, byte[] DATA);  
  
    public System.IO.Stream Read_PHOTO(string FILTER);  
}  
```  
  
 En este fragmento de código, **Tables_APPS_CUSTOMERClient** es el nombre de la clase WCF en el OracleEBSBindingClient.cs generado por la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Update_PHOTO y Read_PHOTO son métodos que se pueden invocar para actualizar y leer las columnas de tipos de datos de gran tamaño en una tabla.  
  
### <a name="parameters-for-table-operations"></a>Parámetros para las operaciones de tabla  
 Esta sección proporciona los parámetros requeridos por la Update_\<*column_name*> y Read_\<*column_name*> operación.  
  
|Nombre de la operación|Parámetros|  
|--------------------|----------------|  
|Update_\<*column_name*>|Necesita los siguientes parámetros:<br /><br /> -   `string FILTER`. Este parámetro debe contener where cláusula que denota el registro para el que se tienen que actualizar datos. Por ejemplo, `"WHERE Name='Mindy Martin'"`.<br />-   `byte[] DATA`. Contiene una matriz de bytes de datos que se van a actualizar en una columna de tipo de datos de gran tamaño.|  
|Read_\<*column_name*>|Necesita los siguientes parámetros:<br /><br /> -   `string FILTER`. Este parámetro debe contener where cláusula que denota el registro desde el que los datos tienen que debe leerse. Por ejemplo, `"WHERE Name='Mindy Martin'"`.|  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-with-columns-of-large-data-types"></a>Creación de un cliente WCF para invocar operaciones en tablas con columnas de tipos de datos de gran tamaño  
 El conjunto de acciones necesarias para realizar una operación en Oracle E-Business Suite mediante un cliente WCF genérico implica un conjunto de tareas que se describen en [información general sobre el modelo de servicio WCF con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-service-model-with-the-oracle-e-business-suite-adapter.md). En esta sección se describe cómo crear un cliente WCF para invocar operaciones Update_PHOTO y Read_PHOTO en una tabla de base de datos de clientes.  
  
#### <a name="to-create-a-wcf-client"></a>Para crear a un cliente WCF  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  Genere la clase de cliente WCF para las operaciones de Update_PHOTO y Read_PHOTO en la tabla de base de datos de cliente. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de la solución de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-wcf-client-or-wcf-service-contract-for-oracle-ebs-solution-artifacts.md).  
  
    > [!IMPORTANT]
    >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS` y `Microsoft.ServiceModel.Channels`, `System.Transactions`.  
  
4.  Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  
  
    -   `Microsoft.Adapters.OracleEBS`  
  
    -   `System.ServiceModel`  
  
    -   `System.Transactions`  
  
    -   `System.IO`  
  
5.  Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.  
  
    ```  
  
              Tables_APPS_CUSTOMERClient client = new Tables_APPS_CUSTOMERClient("OracleEBSBinding_Tables_APPS_CUSTOMER");  
  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     En este fragmento de código, `Tables_APPS_CUSTOMERClient` es el cliente WCF definido en OracleEBSBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  
  
    > [!NOTE]
    >  En este fragmento de código, se utiliza el enlace y la dirección del extremo de app.config de archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las distintas formas de especificar el enlace del cliente, consulte [configurar un cliente de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-client-binding-for-the-oracle-e-business-suite.md).  
  
6.  Establezca las credenciales para el cliente.  
  
    ```  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!IMPORTANT]
    >  En este ejemplo, que se están realizando operaciones en una tabla de base de datos. Sin embargo, si va a realizar las operaciones en una tabla de interfaz, debe establecer el contexto de la aplicación especificando los valores adecuados para el **OracleUserName**, **OraclePassword**, y  **OracleEBSResponsibilityName** propiedades de enlace. Debe especificar estas propiedades de enlace antes de abrir al cliente. Para obtener más información sobre el contexto de la aplicación, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
7.  Abra al cliente como se describe en el siguiente fragmento:  
  
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
  
8.  Invocar la operación Update_PHOTO en la tabla CUSTOMER.  
  
     La operación de Update_PHOTO requiere una matriz de bytes para los datos que se va a actualizar. En este fragmento de código, se utiliza la clase de FileStream para crear una matriz de bytes para una foto, SamplePhoto.jpg. Para que funcione la aplicación, el archivo debe copiarse al directorio bin del proyecto.  
  
    > [!IMPORTANT]
    >  La operación de Update_PHOTO se debe realizar en una transacción, por lo que la **UseAmbientTransaction** enlaza la propiedad debe establecerse en **true** y se debe realizar la operación de Update_PHOTO dentro de un ámbito de la transacción. Puede establecer la **UseAmbientTransaction** propiedad de enlace en el archivo app.config o si se establece explícitamente en la aplicación como `binding.UseAmbientTransaction = true`. Tenga en cuenta que si va a especificar explícitamente la propiedad de enlace en el código, debe hacerlo antes de abrir al cliente.  
  
    ```  
    byte[] photo;  
  
    using (FileStream fs = new FileStream("SamplePhoto.jpg", FileMode.Open))  
    {  
        try  
        {  
            Console.WriteLine("Reading the photo");  
            int count = 0;  
            photo = new byte[fs.Length];  
            while ((count += fs.Read(photo, count, (int)(((fs.Length - count) > 4096) ? 4096 : fs.Length - count))) \< fs.Length) ;  
        }  
        catch(Exception ex)  
        {  
            Console.WriteLine("Exception: " + ex.Message);  
            throw;  
        }  
    }  
  
    Console.WriteLine("Updating data for the 'PHOTO' column");  
    // Invoking the Update_PHOTO operation inside a transaction scope  
    using (TransactionScope tx = new TransactionScope())  
    {  
        string filter = "WHERE Name='Mindy Martin'";  
        client.Update_PHOTO(filter, photo);  
        tx.Complete();  
    }  
  
    ```  
  
9. Invocar la operación Read_PHOTO en la tabla CUSTOMER.  
  
     El Read_PHOTO da el resultado en forma de System.IO.Stream. El cliente de adaptador debe implementar la clase FileStream para leer los datos de la operación de Read_PHOTO. Una vez completada la operación de Read_PHOTO, un archivo PhotoCopy.jpg se copia en el directorio bin del proyecto.  
  
    ```  
    using (FileStream fs = new FileStream("PhotoCopy.jpg", FileMode.Create))  
    {  
        Console.WriteLine("Reading photo data");  
        String ReadFilter = "WHERE NAME='Mindy Martin'";  
        Stream photoStream = client.Read_PHOTO(ReadFilter);  
        Console.WriteLine("Photo data read -- writing to PhotoCopy.jpg");  
  
        int count;  
        int length = 0;  
        byte[] buffer = new byte[4096];  
        while ((count = photoStream.Read(buffer, 0, 4096)) > 0)  
        {  
            fs.Write(buffer, 0, count);  
            length+=count;  
        }  
        Console.WriteLine("{0} bytes written to PhotoCopy.jpg", length);  
    }  
  
    Console.WriteLine("Photo updated and read back -- Hit <RETURN> to end");  
    Console.ReadLine();  
    ```  
  
10. Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
11. Compile el proyecto y, a continuación, ejecútelo. La aplicación actualiza la columna PHOTO de la tabla CUSTOMER y, a continuación, lee el contenido de la columna PHOTO.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)