---
title: Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo del canal WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495b9010-856f-4782-bd19-1522bc3eb950
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 650a60b3a8a9484461edab432370e58cdd8eee70
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013781"
---
# <a name="poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model"></a>Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de canal WCF
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódica mediante el uso de una instrucción SELECT para las tablas de interfaz un sondeo continuo, interfaz vistas, tablas y vistas de Oracle E-Business Suite. Puede especificar una instrucción SELECT como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear Oracle E-Business Suite. También puede especificar un bloque de código posterior a la encuesta PL/SQL que el adaptador se ejecuta después de ejecutar la instrucción de sondeo.  

 Para habilitar el sondeo, debe especificar ciertas propiedades de enlace como se describe en este tema. Para obtener más información acerca de cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Configuración de una operación de sondeo con enlazar propiedades de adaptador para Oracle E-Business Suite  
 La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mensajes de cambio de propiedades de enlace que usan para configurar el adaptador para recibir datos. Debe especificar estas propiedades de enlace al ejecutar la aplicación de sondeo.  


|         Propiedad de enlace         |                                                                                                                                                                                                                            Descripción                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          Especifica si desea realizar **sondeo** o **notificación** operación entrante. El valor predeterminado es **sondeo**.                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. Solo si hay un registro, la instrucción SELECT especifique para la **PollingInput** se ejecutará el enlace de propiedad.                                                                                                              |
|       **PollingInterval**        | Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo. |
|         **PollingInput**         |                         Especifica la instrucción de sondeo. Para sondear con una instrucción SELECT, debe especificar una instrucción SELECT para esta propiedad de enlace. El valor predeterminado es null.<br /><br /> Debe especificar un valor para **PollingInput** enlace de propiedad para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad.                          |
|        **PollingAction**         |                                                                                                                Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo de la interfaz de servicio generada para la operación mediante la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].                                                                                                                |
|      **PostPollStatement**       |                                                                                                                                                                  Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y la instrucción de sondeo, se ejecuta continuamente si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado. El valor predeterminado es False.                                     |

 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle, lea el resto de este tema.  

## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de datos cambia mensajes mediante las instrucciones SELECT, sondea la **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación**aplicación. Esta tabla se crea al ejecutar el script de create_apps_artifacts.sql proporcionado con los ejemplos para crear estos objetos en Oracle E-Business Suite.  

 Para demostrar una operación de sondeo, llevamos a cabo lo siguiente:  

-   Especifique una instrucción SELECT para la **PolledDataAvailableStatement** enlaza la propiedad para determinar donde la interfaz tabla sondea (MS_SAMPLE_EMPLOYEE) tiene los datos. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla de interfaz MS_SAMPLE_EMPLOYEE tiene algunos registros.  

-   Especifique una instrucción SELECT para la **PollingInput** enlaza la propiedad. Esta instrucción recupera todas las filas de la tabla de interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  Para obtener información acerca de la cláusula FOR UPDATE en la instrucción SELECT, vea [recibir los mensajes basados en sondeos de cambio de datos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/receive-polling-based-data-changed-messages-from-oracle-e-business-suite.md).  

-   Especifique una instrucción DELETE como parte de la **PostPollStatement** enlaza la propiedad. Esta instrucción eliminará todos los datos de tabla de la interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     Tras esto, la próxima vez que la instrucción especificada para **PollingInput** será ejecuta, no capturará todos los datos.  

-   Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo por lo que debe volver a llenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros. Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.  

## <a name="consuming-the-polling-request-message"></a>Consume el mensaje de solicitud de sondeo  
 El adaptador invoca la operación de sondeo en el código para sondear Oracle E-Business Suite. Es decir, el adaptador envía un mensaje de solicitud de sondeo que reciba a través de una forma de canal IInputChannel. El mensaje de solicitud de sondeo contiene el conjunto de resultados de la consulta especificada por el **PollingInput** enlaza la propiedad. Puede consumir el mensaje de sondeo en uno de dos maneras:  

-   Para consumir el mensaje con el valor del nodo de transmisión por secuencias, debe llamar a la **WriteBodyContents** método en la respuesta del mensaje y pasarle un **XmlDictionaryWriter** que implementa el valor del nodo de transmisión por secuencias.  

-   Para consumir el mensaje mediante el flujo de nodo, se puede llamar a **GetReaderAtBodyContents** en el mensaje de respuesta para obtener un **XmlReader**.  

## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema sondean la tabla de interfaz MS_SAMPLE_EMPLOYEE. Se proporciona un script para generar la tabla con los ejemplos. Para obtener más información acerca de los ejemplos, vea [ejemplos para el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md). Un ejemplo, **SelectPolling_ChannelModel**, que se basa en este tema, también se proporciona con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejemplos.  

## <a name="receiving-inbound-messages-for-polling-operation-using-the-wcf-channel-model"></a>Recibir mensajes de entrada para la operación de sondeo mediante el modelo de canal de WCF  
 Esta sección proporciona instrucciones sobre cómo escribir una aplicación de .NET (modelo de canal) para recibir mensajes de sondeo de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  

#### <a name="to-receive-polling-messages-from-the-adapter"></a>Para recibir mensajes de sondeo del adaptador  

1. Crear un proyecto Microsoft Visual C#® en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]. Este tema, cree una aplicación de consola.  

2. En el Explorador de soluciones, agregue la referencia a `Microsoft.Adapters.OracleEBS`, `Microsoft.ServiceModel.Channels`, `System.ServiceModel`, y `System.Runtime.Serialization`.  

3. Abra el archivo Program.cs y agregue los espacios de nombres siguientes:  

   -   `Microsoft.Adapters.OracleEBS`  

   -   `System.ServiceModel`  

   -   `System.ServiceModel.Description`  

   -   `System.ServiceModel.Channels`  

   -   `System.Xml`  

4. Especifique un URI de conexión. Para obtener más información sobre el URI de conexión del adaptador, vea [crear el URI de conexión de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-the-oracle-e-business-suite-connection-uri.md).  

   ```  
   Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name");  
   ```  

5. Cree una instancia de **OracleEBSBinding** y establezca las propiedades de enlace necesarias para configurar el sondeo. Como mínimo, debe establecer el **InboundOperationType**, **PolledDataAvailableStatement**, **PollingInput**, y **PollingAction** propiedades de enlace. Para obtener más información sobre las propiedades utilizadas para configurar el sondeo de enlace, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md).  

   ```  
   OracleEBSBinding binding = new OracleEBSBinding();  
   binding.InboundOperationType = InboundOperation.Polling;  
   binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
   binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
   binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
   binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
   ```  

6. Dado que sondean una tabla de interfaz, también debe establecer el contexto de las aplicaciones. Para obtener más información sobre el contexto de la aplicación y las propiedades de enlace necesarias para el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

   ```  
   binding.OracleUserName = "<Enter user name here>";  
   binding.OraclePassword = "<Enter password here>";  
   binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  
   ```  

7. Crear una colección de parámetros de enlace y establecer las credenciales.  

   ```  
   ClientCredentials credentials = new ClientCredentials();  
   credentials.UserName.UserName = "<Enter user name here>";  
   credentials.UserName.Password = "<Enter password here>";  

   BindingParameterCollection bindingParams = new BindingParameterCollection();  
   bindingParams.Add(credentials);  
   ```  

8. Cree una escucha de canales y ábralo. Crear el agente de escucha mediante la invocación **BuildChannelListener < IInputChannel\>**  método en el **OracleEBSBinding**.  

   ```  
   IChannelListener<IInputChannel> listener = binding.BuildChannelListener<IInputChannel>(connectionUri, bindingParams);  
   listener.Open();  
   ```  

9. Obtener un **IInputChannel** canal invocando el **AcceptChannel** método en el agente de escucha y ábralo.  

    ```  
    IInputChannel channel = listener.AcceptChannel();  
    channel.Open();  
    ```  

10. Invocar **recepción** en el canal para obtener el mensaje entrante del adaptador.  

    ```  
    Message message = channel.Receive();  
    ```  

11. Consumir el conjunto de resultados devuelto por la operación de entrada. Puede consumir el mensaje mediante un **XmlReader** o un **XmlDictionaryWriter**.  

    ```  
    XmlReader reader = message.GetReaderAtBodyContents();  
    ```  

12. Cierre el canal cuando haya terminado de procesar la solicitud.  

    ```  
    channel.Close()  
    ```  

    > [!IMPORTANT]
    >  Debe cerrar el canal cuando haya terminado de procesar la operación de entrada. Error al cerrar el canal puede afectan al comportamiento del código.  

13. Cierre el agente de escucha cuando haya terminado de recibir mensajes de cambio de datos.  

    ```  
    listener.Close()  
    ```  

    > [!IMPORTANT]
    >  Cerrando el agente de escucha no cierra los canales creados mediante el agente de escucha. Debe cerrar explícitamente cada canal creado mediante el agente de escucha.  

### <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra una aplicación de sondeo que sondea la tabla de interfaz MS_SAMPLE_EMPLOYEE. El **PollingInput** propiedad contiene la instrucción select que lee todos los datos de la tabla MS_SAMPLE_EMPLOYEE y la instrucción de sondeo de envío, elimina todos los datos de la misma tabla. Se escribe el mensaje de sondeo en `C:\PollingOutput.xml`.  

 Mensajes de sondeo subsiguiente no contendrá ningún registro hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE. Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla. El adaptador seguirá sondeando hasta que cierre el host de servicio presionando \<devolver\>.  

```  
using System;  
using Microsoft.Adapters.OracleEBS;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
using System.ServiceModel.Channels;  
using System.Xml;  

namespace SelectPolling_ChannelModel  
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

                OracleEBSBinding binding = new OracleEBSBinding();  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PolledDataAvailableStatement = "SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE";  
                binding.PollingInput = "SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE";  
                binding.PollingAction = "InterfaceTables/Poll/FND/APPS/MS_SAMPLE_EMPLOYEE";  
                binding.PostPollStatement = "DELETE FROM MS_SAMPLE_EMPLOYEE";  
                binding.OracleUserName = "<Enter user name here>";  
                binding.OraclePassword = "<Enter password here>";  
                binding.OracleEBSResponsibilityName = "<Enter responsibility here>";  

                Uri ConnectionUri = new Uri("oracleebs://ebs_instance_name?");  

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
                Console.ReadLine();  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                    Console.ReadLine();  
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
 [Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-channel-model.md)