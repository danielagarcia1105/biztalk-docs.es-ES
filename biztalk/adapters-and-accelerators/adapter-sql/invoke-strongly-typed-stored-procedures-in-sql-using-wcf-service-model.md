---
title: Invocar fuertemente tipado procedimientos almacenados en SQL mediante el modelo de servicio de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d56df5f6-b046-4fe4-a5b4-b29906093beb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b88cae88a01ea3f04da3b3672153da7d00ea7633
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966821"
---
# <a name="invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model"></a>Invocar fuertemente tipado procedimientos almacenados en SQL mediante el modelo de servicio de WCF
Al invocar un procedimiento que aparece bajo el **Strongly-Typed procedimientos** nodo en el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el resultado es en forma de un conjunto de resultados fuertemente tipado. Este tema proporciona instrucciones sobre cómo crear un cliente WCF para invocar procedimientos almacenados en SQL Server que devuelven un conjunto de resultados fuertemente tipado.  
  
> [!NOTE]
>  Si va a realizar la operación en tablas con columnas de tipos definidos por el usuario, asegúrese de que se hace referencia a [operaciones en tablas y vistas con tipos definidos por el usuario](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) antes de empezar a desarrollar su aplicación.  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 El ejemplo de este tema usa el procedimiento almacenado de GET_EMP_DETAILS. Este procedimiento almacenado toma un identificador de empleado como parámetro de entrada y devuelve todas las columnas correspondientes para el empleado con ese identificador. El procedimiento almacenado de GET_EMP_DETAILS se crea mediante la ejecución de la secuencia de comandos SQL con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md). Un ejemplo, **Execute_TypedStoredProcedure**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF generado para invocar procedimientos almacenados en el **Strongly-Typed procedimientos** nodo mediante la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] aparece en la tabla siguiente.  
  
|Artefactos de base de datos SQL Server|Nombre de cliente WCF|  
|----------------------------------|---------------------|  
|Procedimiento (bajo la **Strongly-Typed procedimientos** nodo)|TypedProcedures_ cliente [esquema]|  
  
 [] es el esquema al que pertenece el procedimiento; Por ejemplo, "dbo".  
  
### <a name="method-signature-for-invoking-stored-procedures"></a>Firma de método para invocar procedimientos almacenados  
 En la tabla siguiente se muestra la firma del método que se exponen para invocar los procedimientos almacenados.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Nombre del procedimiento|[PROC_NS] [nombre_procedimiento] (param1, param2...\)|  
  
 [PROC_NS] es el espacio de nombres de procedimiento; Por ejemplo schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0]  
  
 [procedure_name] es el nombre del procedimiento; Por ejemplo GET_EMP_DETAILS  
  
 Por ejemplo, la firma del método invocar el procedimiento GET_EMP_DETAILS se muestra en el siguiente fragmento de código.  
  
```  
public partial class TypedProcedures_dboClient : System.ServiceModel.ClientBase<TypedProcedures_dbo>, TypedProcedures_dbo{  
public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[]   
  GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue);  
}  
```  
  
 En este fragmento de código  
  
-   `TypedProcedures_dboClient` es el nombre de la clase. En este ejemplo, utiliza esta clase para crear un cliente para invocar el procedimiento almacenado.  
  
-   `public schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] GET_EMP_DETAILS(System.Nullable<int> emp_id, out int ReturnValue)` es el método que invoque en este ejemplo para invocar el procedimiento almacenado. Este procedimiento almacenado toma un identificador de empleado y devuelve un conjunto de resultados fuertemente tipado.  
  
## <a name="creating-a-wcf-client-to-invoke-a-stored-procedure-in-sql-server"></a>Creación de un cliente WCF para invocar un procedimiento almacenado en SQL Server  
 El conjunto genérico de las acciones necesarias para realizar una operación en SQL Server mediante un cliente de WCF implica un conjunto de tareas que se describen en [general del modelo de servicio WCF con el adaptador de SQL](overview-of-the-wcf-service-model-with-the-sql-adapter.md). En concreto, esta sección describe cómo crear a un cliente WCF que invoca un procedimiento almacenado, el conjunto de resultados para que está fuertemente tipada. En este tema, por ejemplo, se invoca el procedimiento almacenado de GET_EMP_DETAILS. Este procedimiento almacenado se crea al ejecutar el script SQL proporcionado con cada ejemplo.  
  
1. Cree un proyecto de Visual C# en Visual Studio. Este tema, cree una aplicación de consola.  
  
2. Generar la clase de cliente WCF para el procedimiento almacenado de GET_EMP_DETAILS. Asegúrese de seleccionar el procedimiento en el **Strongly-Typed procedimientos** nodo. Para obtener más información acerca de cómo generar una clase de cliente WCF, vea [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server](generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
   > [!IMPORTANT]
   >  Antes de generar la clase de cliente WCF, asegúrese de establecer el **EnableBizTalkCompatibilityMode** enlaza la propiedad en false.  
  
3. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql` y `Microsoft.ServiceModel.Channels`.  
  
4. Abra el archivo Program.cs y cree a un cliente como se describe en el siguiente fragmento.  
  
   ```  
  
             TypedProcedures_dboClient client = new TypedProcedures_dboClient("SqlAdapterBinding_TypedProcedures_dbo");  
   client.ClientCredentials.UserName.UserName = "<Enter username here>";  
   client.ClientCredentials.UserName.Password = "<Enter username here>";  
   ```  
  
    En este fragmento de código, `TypedProcedures_dboClient` es el cliente WCF definido en SqlAdapterBindingClient.cs. Este archivo es generado por el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. `SqlAdapterBinding_TypedProcedures_dbo` es el nombre de la configuración de punto de conexión de cliente y se define en el archivo app.config. Este archivo también se genera mediante el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y contiene las propiedades de enlace y otras opciones de configuración.  
  
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
  
6. Invocar el procedimiento GET_EMP_DETAILS almacenados como se describe en el siguiente fragmento.  
  
   ```  
   // Create array of type as specified in the method signature  
   schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[] resultSet =  
      new schemas.microsoft.com.Sql._2008._05.ProceduresResultSets.dbo.GET_EMP_DETAILS.StoredProcedureResultSet0[1];  
   int returnCode;  
  
   try  
   {  
      Console.WriteLine("Calling a stored procedure...");  
      resultSet = client.GET_EMP_DETAILS(10001, out returnCode);  //Invoke the stored procedure  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   Console.WriteLine("The details for the employee with ID '10001' are:");  
   Console.WriteLine("*************************************************");  
  
   for (int i = 0; i < resultSet.Length; i++)  
      {  
         Console.WriteLine("Employee Name        : " + resultSet[i].Name);  
         Console.WriteLine("Employee Designation : " + resultSet[i].Designation);  
         Console.WriteLine("Employee Salary      : " + resultSet[i].Salary);  
      }  
  
   Console.WriteLine("*************************************************");  
  
   ```  
  
7. Cierre al cliente como se describe en el siguiente fragmento:  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. Compile el proyecto y, a continuación, ejecútelo. El nombre, designación y salario para el identificador de empleado, se muestran en la consola.  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones con el modelo de servicio WCF](develop-sql-applications-using-the-wcf-service-model.md)