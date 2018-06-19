---
title: Las operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en SQL mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62f166af-b657-491b-b20d-1ae7886f27ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f886463e2b38b358e5f6a9da8b7e67aabdc9c3ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224652"
---
# <a name="executereader-executescalar-or-executenonquery-operations-in-sql-using-wcf-service-model"></a>Operaciones de ExecuteReader, ExecuteScalar o ExecuteNonQuery en SQL mediante el modelo de servicio de WCF
El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone las operaciones de SQL Server genéricas como **ExecuteNonQuery**, **ExecuteReader**, y **ExecuteScalar**. Puede utilizar estas operaciones para ejecutar cualquier instrucción SQL en una base de datos de SQL Server. Estas operaciones varían en función del tipo de respuesta que se obtiene de la instrucción SQL. Para obtener más información acerca del modo en que el adaptador admite estas operaciones, vea [soporte técnico para las operaciones de ExecuteScalar, ExecuteReader y ExecuteNonQuery](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).  
  
 En este tema se muestra cómo realizar una **ExecuteReader** operación mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] mediante el modelo de servicio WCF. Puede seguir el mismo conjunto de procedimientos que se describen en este tema para realizar **ExecuteNonQuery** y **ExecuteScalar** operaciones.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 El ejemplo de este tema usa el **ExecuteReader** operación para ejecutar el ADD_EMP_DETAILS procedimiento almacenado. Este procedimiento almacenado agrega un registro a la tabla de empleados y devuelve el identificador de empleado para el registro. El procedimiento almacenado de ADD_EMP_DETAILS se crea al ejecutar el script SQL que se proporciona con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Obtener un ejemplo, **Execute_Reader**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar operaciones genéricas (ExecuteNonQuery, ExecuteReader o ExecuteScalar) utilizando el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.  
  
|Operaciones|Nombre de cliente WCF|  
|----------------|---------------------|  
|ExecuteNonQuery, ExecuteReader o ExecuteScalar|GenericTableOpClient|  
  
### <a name="method-signature-for-invoking-generic-operations"></a>Firma de método para invocar operaciones genéricas  
 En la tabla siguiente se muestra la firma para el método expuesto para invocar las operaciones genéricas.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|ExecuteNonQuery|int ExecuteNonQuery (cadena de consulta)|  
|ExecuteReader|[] De System.Data.DataSet ExecuteReader (cadena de consulta)|  
|ExecuteScalar|cadena ExecuteScalar(string Query)|  
  
 Por ejemplo, la firma para los métodos de operación genérica se muestra en el siguiente fragmento de código.  
  
```  
public partial class GenericTableOpClient : System.ServiceModel.ClientBase<GenericTableOp>, GenericTableOp {  
  public int ExecuteNonQuery(string Query);  
  public System.Data.DataSet[] ExecuteReader(string Query);  
  public string ExecuteScalar(string Query);  
}  
```  
  
 En este fragmento de código  
  
-   `GenericTableOpClient`es el nombre de la clase. En este ejemplo, utilice esta clase para crear un cliente para invocar la operación genérica, ExecuteReader.  
  
-   `public System.Data.DataSet[] ExecuteReader(string Query)`es el método que se invoca en este ejemplo para invocar la ADD_EMP_DETAILS procedimiento almacenado.  
  
## <a name="creating-a-wcf-client-to-invoke-an-executereader-operation"></a>Creación de un cliente WCF para invocar la operación ExecuteReader  
 El conjunto de acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF genérico implica un conjunto de tareas que se describen en [información general del modelo del canal WCF con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-channel-model-with-the-sql-adapter.md). En concreto, en esta sección describe cómo crear un cliente WCF que invoca un **ExecuteReader** operación para ejecutar el ADD_EMP_DETAILS procedimiento almacenado. Este procedimiento almacenado se crea mediante la ejecución de la secuencia de comandos SQL proporcionado con cada ejemplo.  
  
#### <a name="to-create-a-wcf-client-to-invoke-executereader-operation"></a>Para crear un cliente WCF para invocar la operación ExecuteReader  
  
1.  Cree un proyecto de Visual C# en Visual Studio. De este tema, cree una aplicación de consola.  
  
2.  Generar la clase de cliente WCF para la **ExecuteReader** operación genérica. Esta operación está disponible bajo el nodo raíz cuando se conecta a la base de datos de SQL Server mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
    > [!IMPORTANT]
    >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3.  En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.  
  
4.  Abra el archivo Program.cs y crear a un cliente, como se describe en el siguiente fragmento.  
  
    ```  
  
            GenericTableOpClient client = new GenericTableOpClient("SqlAdapterBinding_GenericTableOp");  
    client.ClientCredentials.UserName.UserName = "<Enter username here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     En este fragmento de código, `GenericTableOpClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_GenericTableOp`es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
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
  
6.  Invocar la **ExecuteReader** operación para el ADD_EMP_DETAILS de procedimiento almacenado. Antes de invocar la operación ExecuteReader, debe agregar el `System.Data` espacio de nombres en el código.  
  
    ```  
    string query = "EXEC ADD_EMP_DETAILS 'Tom Smith', 'Manager', 500000";  
    DataSet[] dsArray = client.ExecuteReader(query);  
  
    Console.WriteLine("Invoking the ADD_EMP_DETAILS stored procedure using ExecuteReader");  
    Console.WriteLine("*****************************************************");  
    foreach (DataSet dataSet in dsArray)  
    {  
       foreach (DataTable tab in dsArray[0].Tables)  
       {  
           foreach (DataRow row in tab.Rows)  
           {  
              for (int i = 0; i < tab.Columns.Count; i++)  
              {  
                 Console.WriteLine("The ID for the newly added employee is : " + row[i]);  
              }  
           }  
        }  
    }  
    Console.WriteLine("*****************************************************");  
  
    ```  
  
7.  Cierre al cliente como se describe en el siguiente fragmento:  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  Compile el proyecto y, a continuación, ejecútelo. El identificador de empleado del empleado recién insertado se muestra en la consola.