---
title: Invocar débilmente tipada procedimientos almacenados de SQL mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf74a40-4c03-4a4a-9b91-c21babe154fa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc2e477aaf5ee113f6479559c23d184e91d905f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012077"
---
# <a name="invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model"></a>Invocar débilmente tipada procedimientos almacenados de SQL mediante el modelo de servicio de WCF
Al invocar un procedimiento que aparece bajo el **procedimientos** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el resultado es en forma de una matriz de conjunto de datos. Este tema proporciona instrucciones sobre cómo crear un cliente WCF para invocar un procedimiento almacenado en SQL Server que devuelve una matriz de conjunto de datos.  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que se hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar su aplicación.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 El ejemplo de este tema usa el procedimiento almacenado de GET_EMP_DETAILS. Este procedimiento almacenado toma un identificador de empleado como parámetro de entrada y devuelve todas las columnas correspondientes para el empleado con ese identificador. El procedimiento almacenado de GET_EMP_DETAILS se crea mediante la ejecución de la secuencia de comandos SQL con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Un ejemplo, **Execute_StoredProc**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar procedimientos almacenados en el **procedimientos** nodo mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Procedimiento (bajo la **procedimientos** nodo)|Procedures_ cliente [esquema]|  
  
 [] es el esquema al que pertenece el procedimiento; Por ejemplo, "dbo".  
  
### <a name="method-signature-for-invoking-stored-procedures"></a>Firma de método para invocar procedimientos almacenados  
 En la tabla siguiente se muestra la firma del método que se exponen para invocar los procedimientos almacenados.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Nombre del procedimiento|[] System.Data.DataSet [procedure_name] (param1, param2...\)|  
  
 [procedure_name] es el nombre del procedimiento; Por ejemplo GET_EMP_DETAILS  
  
 Por ejemplo, la firma del método invocar el procedimiento GET_EMP_DETAILS se muestra en el siguiente fragmento de código.  
  
```  
public partial class Procedures_dboClient : System.ServiceModel.ClientBase<Procedures_dbo>, Procedures_dbo {  
  public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 En este fragmento de código  
  
-   `Procedures_dboClient` es el nombre de la clase de cliente WCF. En este ejemplo, utiliza esta clase para crear un cliente para invocar el procedimiento almacenado.  
  
-   `public System.Data.DataSet[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` es el método que invoque en este ejemplo para invocar el procedimiento almacenado. Este procedimiento almacenado toma un identificador de empleado y devuelve una matriz de conjunto de datos.  
  
## <a name="create-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a>Crear un cliente WCF para invocar un procedimiento almacenado en SQL Server  
 El conjunto genérico de las acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF implica un conjunto de tareas que se describen en [general del modelo de servicio WCF con el adaptador](overview-of-the-wcf-service-model-with-the-sql-adapter.md). En concreto, esta sección describe cómo crear a un cliente WCF que invoca un procedimiento almacenado, el conjunto de resultados para que es una matriz de conjunto de datos. En este tema, por ejemplo, se invoca el procedimiento almacenado de GET_EMP_DETAILS. Este procedimiento almacenado se crea al ejecutar el script SQL proporcionado con cada ejemplo.  
  
  
1. Cree un proyecto de Visual C# en Visual Studio. Este tema, cree una aplicación de consola.  
  
2. Generar la clase de cliente WCF para el procedimiento almacenado de GET_EMP_DETAILS. Asegúrese de seleccionar el procedimiento en el **procedimientos** nodo. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
   > [!IMPORTANT]
   >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.  
  
4. Abra el archivo Program.cs y cree a un cliente como se describe en el siguiente fragmento.  
  
   ```  
  
             Procedures_dboClient client = new Procedures_dboClient("SqlAdapterBinding_Procedures_dbo");  
  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    En este fragmento de código, `Procedures_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_Procedures_dbo` es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
   > [!NOTE]
   >  En este fragmento de código, utilice el enlace y dirección de punto de conexión del archivo de configuración. Puede especificar también explícitamente estos valores en el código. Para obtener más información sobre las diferentes maneras de especificar el enlace del cliente, consulte [configurar un enlace de cliente para el adaptador de SQL](configure-a-client-binding-for-the-sql-adapter.md).  
  
5. Abra al cliente como se describe en el siguiente fragmento:  
  
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
  
6. Invocar el procedimiento almacenado de GET_EMP_DETAILS. Antes de invocar el procedimiento GET_EMP_DETAILS, debe agregar el `System.Data` espacio de nombres en el código.  
  
   ```  
   DataSet[] dataArray;  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      dataArray = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   foreach (DataSet dataSet in dataArray)  
   {  
      foreach (DataTable tab in dataArray[0].Tables)  
      {  
         foreach (DataRow row in tab.Rows)  
         {  
            for (int i = 0; i < tab.Columns.Count; i++)  
            {  
               Console.WriteLine(row[i]);  
            }  
         }  
      }  
   }  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. Cierre al cliente como se describe en el siguiente fragmento:  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. Compile el proyecto y, a continuación, ejecútelo. Los detalles del empleado, para qué pr
9. ovided el identificador, se muestran en la consola.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](develop-sql-applications-using-the-wcf-service-model.md)