---
title: Recibir mensajes basados en sondeos de cambio de datos de SQL Server mediante el modelo de canal WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0f4af71-fb0c-433d-ba74-48ee6487eb1a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6b87cdb7d36b5f143a833547e4b5522a40e0eb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987358"
---
# <a name="receive-polling-based-data-changed-messages-from-sql-server-by-using-the-wcf-channel-model"></a>Recibir mensajes basados en sondeos de cambio de datos de SQL Server mediante el modelo de canal de WCF
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de cambio de datos periódica o vistas de tablas de SQL Server. Puede especificar una instrucción de sondeo que se ejecuta el adaptador para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.  

 Para obtener más información sobre cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  

> [!IMPORTANT]
>  Si desea tener más de un sondeo operación en una sola aplicación, debe especificar un **InboundID** propiedad de conexión como parte de la conexión URI para que sea único. Especifica el identificador de entrada se agrega al espacio de nombres de operación para que sea único.  

## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] admite la recepción de datos de mensajes de cambio, cree una aplicación .NET para la **sondeo** operación. Este tema, especifique el **PolledDataAvailableStatement** como:  

```  
SELECT COUNT(*) FROM Employee  
```  

 El **PolledDataAvailableStatement** debe devolver un conjunto de resultados con la primera celda que contiene un valor positivo. Si la primera celda no contiene un valor positivo, el adaptador no ejecuta la instrucción de sondeo.  

 Como parte de la instrucción de sondeo, realice las siguientes operaciones:  

1. Seleccione todas las filas de la tabla Employee.  

2. Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.  

3. Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla Employee. Este procedimiento toma el nombre de empleado, designación y salario como parámetros.  

   Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** enlaza la propiedad:  

```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  

 Después de ejecutar la instrucción de sondeo, se seleccionan todos los registros de la tabla de empleados y se recibe el mensaje de SQL Server. Una vez que se ejecuta el procedimiento almacenado de MOVE_EMP_DATA por el adaptador, todos los registros se mueven a la tabla HistorialEmpleados. A continuación, se ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un nuevo registro a la tabla Employee. La siguiente ejecución de sondeo solo devolverá un único registro. Este ciclo continúa hasta que cierre el agente de escucha del canal.  

## <a name="configuring-a-polling-query-with-the-sql-adapter-binding-properties"></a>Configuración de una consulta de sondeo con el adaptador de SQL, las propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades que usan para configurar el adaptador para recibir mensajes de cambio de datos de enlace. Debe especificar estas propiedades de enlace como parte de la aplicación .NET para el sondeo.  


|         Propiedad de enlace         |                                                                                                                                                                                                                                         Descripción                                                                                                                                                                                                                                          |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                             Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante. El valor predeterminado es **sondeo**.                                                                                                                                                                              |
| **PolledDataAvailableStatement** |                                                                                       Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados. Solo si hay una fila, la instrucción SQL especificada para el **PollingStatement** se ejecutará el enlace de propiedad.                                                                                       |
|   **PollingIntervalInSeconds**   |                         Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.                          |
|       **PollingStatement**       | Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server. Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo. El valor predeterminado es null. Debe especificar un valor para **PollingStatement** para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad. Puede especificar cualquier número de instrucciones SQL separadas por punto y coma. |
|      **PollWhileDataFound**      |                            Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y continuamente se ejecuta la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado. El valor predeterminado es **false**.                             |

 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, lea el resto de este tema.  

## <a name="consuming-the-polling-request-message"></a>Consume el mensaje de solicitud de sondeo  
 El adaptador invoca el **sondeo** operación en el código para sondear la base de datos de SQL Server. Es decir, el adaptador envía un mensaje de solicitud de sondeo que reciba a través de una forma de canal IInputChannel. El mensaje de solicitud de sondeo contiene el conjunto de resultados de la consulta especificada por la propiedad de enlace PollingStatement. Puede consumir el mensaje de sondeo en uno de dos maneras:  

-   Para consumir el mensaje mediante el valor del nodo de transmisión por secuencias se debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y pasarle un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.  

-   Para consumir el mensaje mediante el flujo de nodo se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.  

## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema sondean la tabla de empleados. El ejemplo también usa el MOVE_EMP_DATA y ADD_EMP_DETAILS procedimiento almacenado. Una secuencia de comandos para generar estos artefactos se suministra con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md). Un ejemplo, **Polling_ChannelModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejemplos.  

## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a>Recibir mensajes de entrada para la operación de sondeo mediante el modelo de canal de WCF  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación de .NET (modelo de canal) para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  

#### <a name="to-receive-polling-messages-from-the-sql-adapter"></a>Para recibir mensajes de sondeo del adaptador de SQL  

1. Crear un proyecto de Microsoft Visual C# en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Este tema, cree una aplicación de consola.  

2. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.Sql`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.  

3. Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  

   -   `Microsoft.Adapters.Sql`  

   -   `System.ServiceModel`  

   -   `System.ServiceModel.Description`  

   -   `System.ServiceModel.Channels`  

   -   `System.Xml`  

4. Especifique un URI de conexión. Para obtener más información sobre el URI de conexión del adaptador, vea [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  

   ```  
   Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  
   ```  

5. Cree una instancia de **SqlAdapterBinding** y establezca las propiedades de enlace necesarias para configurar el sondeo. Como mínimo, debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, y **PollingStatement** propiedades de enlace. Para obtener más información sobre las propiedades utilizadas para configurar el sondeo de enlace, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  

   ```  
   SqlAdapterBinding binding = new SqlAdapterBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
   binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  
   ```  

6. Crear una colección de parámetros de enlace y establecer las credenciales.  

   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  

   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  

7. Cree una escucha de canales y ábralo. Crear el agente de escucha mediante la invocación **BuildChannelListener < IInputChannel\>**  método en el **SqlAdapterBinding**.  

   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  

8. Obtener un **IInputChannel** canal invocando el **AcceptChannel** método en el agente de escucha y ábralo.  

   ```  
   IInputChannel channel = listener.AcceptChannel();  
   channel.Open();  
   ```  

9. Invocar **recepción** en el canal para obtener el siguiente mensaje POLLINGSTMT desde el adaptador.  

    ```  
    Message message = channel.Receive();  
    ```  

10. Consumir el conjunto de resultados devuelto por la operación POLLINGSTMT. Puede consumir el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.  

    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  

11. Cierre el canal cuando haya terminado de procesar la solicitud.  

    ```  
    channel.Close()  
    ```  

    > [!IMPORTANT]
    >  Debe cerrar el canal cuando haya terminado de procesar la operación POLLINGSTMT. Error al cerrar el canal puede afectan al comportamiento del código.  

12. Cierre el agente de escucha cuando haya terminado de recibir mensajes de cambio de datos.  

    ```  
    listener.Close()  
    ```  

    > [!IMPORTANT]
    >  Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha. Debe cerrar explícitamente cada canal creado mediante el agente de escucha.  

### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una consulta de sondeo que se ejecuta en la tabla Employee. La instrucción de sondeo lleva a cabo las siguientes tareas:  

- Selecciona todos los registros de la tabla Employee.  

- Ejecuta el procedimiento MOVE_EMP_DATA almacenado para mover todos los registros de la tabla Employee a HistorialEmpleados tabla.  

- Ejecuta el procedimiento almacenado de ADD_EMP_DETAILS para agregar un único registro a la tabla Employee.  

  Los mensajes de sondeo que se guardan en `C:\PollingOutput.xml`.  

```  
using System;  
using Microsoft.Adapters.Sql;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  

using System.Xml;  

namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Console.WriteLine("Sample started. This sample will poll 5 times and will perform the following tasks:");  
            Console.WriteLine("Press any key to start polling...");  
            Console.ReadLine();  
            IChannelListener<IInputChannel> listener = null;  

            IInputChannel channel = null;  

            try  
            {  
                TimeSpan messageTimeout = new TimeSpan(0, 0, 30);  

                SqlAdapterBinding binding = new SqlAdapterBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM EMPLOYEE";  
                binding.PollingStatement = "SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000";  

                Uri ConnectionUri = new Uri("mssql://mysqlserver//mydatabase?");  

                ClientCredentials credentials = new ClientCredentials();  
                credentials.UserName.UserName = "<Enter user name here>";  
                credentials.UserName.Password = "<Enter password here>";  

                BindingParameterCollection bindingParams = new BindingParameterCollection();  
                bindingParams.Add(credentials);  

                listener = binding.BuildChannelListener<IInputChannel>(ConnectionUri, bindingParams);  
                listener.Open();  

                channel = listener.AcceptChannel();  
                channel.Open();  

                Console.WriteLine("Channel and Listener opened...");  
                Console.WriteLine("\nWaiting for polled data...");  
                Console.WriteLine("Receive request timeout is {0}", messageTimeout);  

                // Poll five times with the specified message timeout   
                // If a timeout occurs polling will be aborted  
                for (int i = 0; i < 5; i++)  
                {  
                    Console.WriteLine("Polling: " + i);  
                    Message message = null;  
                    XmlReader reader = null;  
                    try  
                    {  
                        //Message is received so process the results  
                        message = channel.Receive(messageTimeout);  
                    }  
                    catch (System.TimeoutException toEx)  
                    {  
                        Console.WriteLine("\nNo data for request number {0}: {1}", i + 1, toEx.Message);  
                        continue;  
                    }  

                    // Get the query results using an XML reader  
                    try  
                    {  
                        reader = message.GetReaderAtBodyContents();  
                    }  
                    catch (Exception ex)  
                    {  
                        Console.WriteLine("Exception :" + ex);  
                        throw;  
                    }  

                    XmlDocument doc = new XmlDocument();  
                    doc.Load(reader);  
                    using (XmlWriter writer = XmlWriter.Create("C:\\PollingOutput.xml"))  
                    {  
                        doc.WriteTo(writer);  
                        Console.WriteLine("The polling response is saved at 'C:\\PollingOutput.xml'");  
                    }  

                    // return the cursor  
                    Console.WriteLine();  

                    // close the reader  
                    reader.Close();  

                    message.Close();  
                }  
                Console.WriteLine("\nPolling done -- hit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
                // IMPORTANT: close the channel and listener to stop polling  
                if (channel != null)  
                {  
                    if (channel.State == CommunicationState.Opened)  
                        channel.Close();  
                    else  
                        channel.Abort();  
                }  

                if (listener != null)  
                {  
                    if (listener.State == CommunicationState.Opened)  
                        listener.Close();  
                    else  
                        listener.Abort();  
                }  
            }  
        }  
    }  
}  

```  

## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)