---
title: 'Paso 1: Crear una prueba unitaria para enviar documentos a BizTalk Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688b14e4-bb16-4d12-86b8-37b8b6808472
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8016bc237b55c2404a21c91e2e68d78fdd21bcf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302700"
---
# <a name="step-1-create-a-unit-test-to-submit-documents-to-biztalk-server"></a>Paso 1: Crear una prueba unitaria para enviar documentos a BizTalk Server
Servidores de aplicaciones del equipo como el servidor BizTalk Server están diseñados para realizar determinadas tareas en nombre de los usuarios. Estas tareas se inician como las solicitudes de cliente que se envían al servidor de aplicaciones como mensajes que cumplan con un estándar que entienda el servidor de aplicaciones, a través de un protocolo que entienda el servidor de aplicaciones. Por ejemplo, los clientes pueden iniciar el procesamiento de correo electrónico mediante el envío de mensajes de correo electrónico de internet a un servidor de correo electrónico a través del protocolo SMTP. Del mismo modo, procesan los servidores web cliente HTML o las solicitudes ASP, servidores de base de datos procesan las solicitudes de cliente SQL y BizTalk Server puede procesar mensajes de cliente con un formato conforme a varios estándares de mensaje del sector mediante varios protocolos estándar del sector. Normalmente, la capacidad de carga de trabajo de un servidor de aplicaciones se mide por el número de mensajes que el servidor de aplicaciones puede procesar en un período de tiempo determinado. La capacidad de carga de trabajo de BizTalk Server del mismo modo se mide como el número medio de "documentos recibidos por segundo", "documentos procesados por segundo" y "orquestaciones completadas por segundo" durante un período prolongado de tiempo, por ejemplo, un día de trabajo o incluso un semana laboral. Funcionalidad de prueba de carga de Visual Studio 2010 puede simular un perfil de carga de hasta cientos de usuarios que acceden al mismo tiempo a una aplicación de servidor. Esta funcionalidad de la prueba de carga proporciona métricas de tiempo real para los indicadores clave de rendimiento seleccionado, así como la capacidad para almacenar estas métricas en una base de datos para su posterior análisis. Pruebas de este describe el uso de proyectos de prueba de Visual Studio con el fin de una aplicación de BizTalk Server, incluido cómo crear unidad de prueba de carga de documento, cómo crear pruebas de carga y cómo configurar las pruebas de carga para capturar datos del contador de rendimiento necesarios para determinar el rendimiento sostenible máximo (MST) de una aplicación de BizTalk Server.  
  
## <a name="creating-a-visual-studio-unit-test-to-submit-documents-to-biztalk-server"></a>Crear una prueba unitaria de Visual Studio para enviar documentos a BizTalk Server  
 Hace referencia a una prueba unitaria de Visual Studio la [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) de espacio de nombres que proporciona varias clases que proporcionan compatibilidad para pruebas unitarias. De especial importancia, el [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.Microsoft.com/fwlink/?) LinkID = 132293) espacio de nombres incluye la [Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.Microsoft.com/fwlink/?) LinkID = 208233) clase para almacenar información que se proporciona a las pruebas unitarias y el [Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.Microsoft.com/fwlink/?) LinkID = 208235) clase se utiliza para definir métodos de prueba. Para fines de BizTalk Server de prueba de carga, los métodos de prueba deben especificar el mensaje que se va a cargar y el punto de conexión/URL a la que debe enviarse el mensaje. La URL de extremo, a continuación, dará servicio a medida que se crea el punto de entrada de mensaje en BizTalk Server cuando la ubicación de recepción de BizTalk correspondiente.  
  
 A efectos de ilustración, el código de ejemplo en este tema describe los métodos de prueba que usan la [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.Microsoft.com/fwlink/?) LinkID = 208238) clase para enviar mensajes a extremos de servicio que utilizan el extremo de net.tcp WCF y se supervisan mediante WCF-Custom de BizTalk: adaptador de recepción. Los extremos de servicio para los mensajes de prueba se definen en el archivo de configuración de la aplicación (app.config) del proyecto de prueba.  
  
 Para obtener más información acerca de las pruebas de unidad de Visual Studio Vea [Anatomía de una prueba unitaria](http://go.microsoft.com/fwlink/?LinkID=208232) (http://go.microsoft.com/fwlink/?LinkID=208232).  
  
 Siga los pasos descritos en las secciones siguientes para crear un proyecto de prueba con una prueba unitaria para enviar documentos a uno o más equipos de BizTalk Server. Estos pasos se completaron con Visual Studio 2010 Ultimate Edition.  
  
### <a name="set-visual-studio-2010-test-project-options"></a>Establecer opciones de proyecto de prueba de Visual Studio 2010  
  
1.  Inicie Visual Studio 2010 Ultimate edition. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Visual Studio 2010** y, a continuación, haga clic en **Microsoft Visual Studio 2010**.  
  
2.  En Visual Studio 2010, haga clic en **herramientas** y, a continuación, haga clic en **opciones** para mostrar la **opciones** cuadro de diálogo.  
  
3.  Haga clic para expandir **herramientas de prueba** y, a continuación, haga clic en **proyecto de prueba** para mostrar las opciones para la creación de nuevos proyectos de prueba.  
  
4.  Establecer el **idioma predeterminado del proyecto de prueba:** a **proyecto de prueba de Visual C#**.  
  
5.  En la opción de **seleccionar los archivos que se agregará a cada nuevo proyecto de prueba, de forma predeterminada:** seleccione **proyecto de prueba de Visual C#** y desactive todos los tipos de prueba de Visual C# de proyectos excepto deprueba **Prueba unitaria**.  
  
6.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Opciones** .  
  
### <a name="create-a-new-visual-studio-2010-solution-with-a-test-project"></a>Crear una nueva solución de Visual Studio 2010 con un proyecto de prueba  
  
1.  Cree la carpeta **C:\Projects** en el equipo de Visual Studio 2010 Ultimate.  
  
2.  En Visual Studio 2010, haga clic en **archivo**, seleccione **New**y haga clic en **proyecto** para mostrar la **nuevo proyecto** cuadro de diálogo.  
  
3.  En **plantillas instaladas** haga clic para expandir **Visual C#** y haga clic en **prueba**.  
  
4.  En la parte inferior de la **nuevo proyecto** cuadro de diálogo especificar las siguientes opciones:  
  
    -   **Nombre:**  
         **BTSLoad**  
  
    -   **Ubicación:**  
         **C:\projects\\**  
  
    -   **Nombre de la solución:**  
         **LoadTest**  
  
5.  Asegúrese de que la opción de **crear directorio para la solución** está activada y, a continuación, haga clic en **Aceptar**.  
  
6.  Agregar una carpeta al proyecto BTSLoad; Esta carpeta contendrá los mensajes de prueba que se envíen al servidor BizTalk Server. En el Explorador de soluciones, haga clic en el proyecto BTSLoad, seleccione **agregar**y haga clic en **nueva carpeta**. Un icono de carpeta con el texto resaltado **NewFolder1** aparecerá en el proyecto BTSLoad, escriba **TestMessages** para cambiar el texto resaltado y presione la **ENTRAR** clave Para crear la carpeta C:\Projects\LoadTest\BTSLoad\TestMessages.  
  
### <a name="update-the-code-in-the-test-project-and-add-an-application-configuration-file-to-the-test-project"></a>Actualice el código en el proyecto de prueba y agregue un archivo de configuración de aplicación para el proyecto de prueba  
  
1.  En el Explorador de soluciones, haga clic para seleccionar **UnitTest1.cs** y reemplace el código existente con la lista de código de ejemplo siguiente:  
  
    ```csharp  
    #region Using Directives  
    using System;  
    using System.IO;  
    using System.Diagnostics;  
    using System.Text;  
    using System.Configuration;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Xml;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using Microsoft.VisualStudio.TestTools.UnitTesting;  
    #endregion  
  
    namespace Microsoft.BizTalk.Samples  
    {  
        [TestClass]  
        public class BTSLoadTest  
        {  
            #region Constants  
            private const int MaxBufferSize = 2097152;  
            private const string Source = "BTS Load Test";  
            private const string Star = "*";  
            private const string TestMessageFolderParameter = "testMessageFolder";  
            private const string TestMessageFolderDefault = @"C:\Projects\LoadTest\BTSLoad\TestMessages";  
            private const string TestMessageFolderFormat = @"Test Message Folder = {0}";  
            private const string TestXmlDocument = "testxmldocument.xml";  
            #endregion  
  
            #region Private Instance Fields  
            private TestContext testContextInstance;  
            #endregion  
  
            #region Private ThreadStatic Fields  
            [ThreadStatic]  
            private static ChannelFactory<IRequestChannel> channelFactory;  
            [ThreadStatic]  
            private static IRequestChannel channel = null;  
            [ThreadStatic]  
            private static byte[] buffer = null;  
            #endregion  
  
            #region Private Static Fields  
            private static string testMessageFolder = null;  
            #endregion  
  
            #region Public Instance Constructor  
            public BTSLoadTest()  
            {  
            }  
            #endregion  
  
            #region Public Static Constructor  
            static BTSLoadTest()  
            {  
                try  
                {  
                    testMessageFolder = ConfigurationManager.AppSettings[TestMessageFolderParameter];  
                    if (string.IsNullOrEmpty(testMessageFolder))  
                    {  
                        testMessageFolder = TestMessageFolderDefault;  
                    }  
                }  
                catch (Exception ex)  
                {  
                    Trace.WriteLine(ex.Message);  
                    EventLog.WriteEntry(Source, ex.Message, EventLogEntryType.Error);  
                }  
            }  
            #endregion  
  
            #region Public Properties  
            /// <summary>  
            ///Gets or sets the test context which provides  
            ///information about and functionality for the current test run.  
            ///</summary>  
            public TestContext TestContext  
            {  
                get  
                {  
                    return testContextInstance;  
                }  
                set  
                {  
                    testContextInstance = value;  
                }  
            }  
            #endregion  
  
            #region Test Methods  
  
            [TestMethod]  
            public void BTSMessaging()  
            {  
                InvokeBizTalkReceiveLocation("BTSMessagingEP",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
  
            [TestMethod]  
            public void BTSMessaging2()  
            {  
                InvokeBizTalkReceiveLocation("BTSMessagingEP2",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
  
            [TestMethod]  
            public void BTSOrchestration()  
            {  
                InvokeBizTalkReceiveLocation("BTSOrchestrationEP",  
                                               testMessageFolder,  
                                               TestXmlDocument,  
                                               MessageVersion.Default,  
                                               SessionMode.Allowed);  
            }  
            #endregion  
  
            #region Helper Methods  
            public void InvokeBizTalkReceiveLocation(string endpointConfigurationName,  
                                               string requestMessageFolder,  
                                               string requestMessageName,  
                                               MessageVersion messageVersion,  
                                               SessionMode sessionMode)  
            {  
                XmlTextReader xmlTextReader = null;  
                Message requestMessage = null;  
                Message responseMessage = null;  
  
                try  
                {  
                    if (channel == null || channel.State != CommunicationState.Opened)  
                    {  
                        channelFactory = new ChannelFactory<IRequestChannel>(endpointConfigurationName);  
                        channelFactory.Endpoint.Contract.SessionMode = sessionMode;  
                        channel = channelFactory.CreateChannel();  
                    }  
                    if (buffer == null)  
                    {  
                        string path = Path.Combine(requestMessageFolder, requestMessageName);  
  
                        string message;  
                        using (StreamReader reader = new StreamReader(File.Open(path, FileMode.Open, FileAccess.Read, FileShare.Read)))  
                        {  
                            message = reader.ReadToEnd();  
                        }  
                        buffer = Encoding.UTF8.GetBytes(message);  
                    }  
                    MemoryStream stream = new MemoryStream(buffer);  
                    xmlTextReader = new XmlTextReader(stream);  
                    requestMessage = Message.CreateMessage(messageVersion, Star, xmlTextReader);  
                    TestContext.BeginTimer(requestMessageName);  
                    responseMessage = channel.Request(requestMessage);  
                }  
                catch (FaultException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (CommunicationException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (TimeoutException ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                catch (Exception ex)  
                {  
                    HandleException(ex);  
                    throw;  
                }  
                finally  
                {  
                    TestContext.EndTimer(requestMessageName);  
                    CloseObjects(xmlTextReader,  
                                 requestMessage,  
                                 responseMessage);  
                }  
            }  
  
            private void HandleException(Exception ex)  
            {  
                try  
                {  
                    Trace.WriteLine(ex.Message);  
                    EventLog.WriteEntry(Source, ex.Message, EventLogEntryType.Error);  
                }  
                catch (Exception)  
                {  
                }  
            }  
  
            private void CloseObjects(XmlTextReader xmlTextReader,  
                               Message requestMessage,  
                               Message responseMessage)  
            {  
                try  
                {  
                    if (xmlTextReader != null)  
                    {  
                        xmlTextReader.Close();  
                    }  
                    if (requestMessage != null)  
                    {  
                        requestMessage.Close();  
                    }  
                    if (responseMessage != null)  
                    {  
                        responseMessage.Close();  
                    }  
                }  
                catch (Exception)  
                {  
                }  
            }  
  
            #endregion  
        }  
    }  
    ```  
  
2.  Agregue un archivo de configuración de aplicación para el proyecto de prueba:  
  
    1.  En el Explorador de soluciones, haga clic en el proyecto BTSLoad, seleccione **agregar** y haga clic en **nuevo elemento**.  
  
    2.  En el **Agregar nuevo elemento** cuadro de diálogo **plantillas instaladas**, haga clic en **General**.  
  
    3.  En la lista de elementos que se muestran, haga clic para seleccionar **archivo de configuración de aplicación** y, a continuación, haga clic en **agregar**.  
  
    4.  En el Explorador de soluciones, seleccione el archivo app.config y reemplace el contenido del archivo app.config con la lista debajo del código de ejemplo:  
  
        > [!IMPORTANT]  
        >  Para cada punto de conexión de cliente definido en este archivo, *equipo de BizTalk Server* es un marcador de posición para el nombre real de la carga de equipos que llevarán a cabo pruebas con el servidor BizTalk Server.  
  
        ```xml  
  
        <configuration>  
          <system.serviceModel>  
            <!-- Bindings used by client endpoints -->  
            <bindings>  
              <netTcpBinding>  
                <binding name="netTcpBinding" closeTimeout="01:10:00" openTimeout="01:10:00" receiveTimeout="01:10:00" sendTimeout="01:10:00" transactionFlow="false" transferMode="Buffered" transactionProtocol="OleTransactions" hostNameComparisonMode="StrongWildcard" listenBacklog="100" maxBufferPoolSize="1048576" maxBufferSize="10485760" maxConnections="400" maxReceivedMessageSize="10485760">  
                  <readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" />  
                  <reliableSession ordered="true" inactivityTimeout="00:10:00" enabled="false" />  
                  <security mode="None">  
                    <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
                    <message clientCredentialType="Windows" />  
                  </security>  
                </binding>  
              </netTcpBinding>  
            </bindings>  
            <client>  
              <!-- Client endpoints used to exchange messages with WCF Receive Locations -->  
  
              <!-- BTSMessagingEP -->  
              <endpoint address="net.tcp://BizTalk Server Computer:8123/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSMessagingEP" />  
              <endpoint address="net.tcp://BizTalk Server Computer:8123/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSMessagingEP" />  
  
              <!-- BTSOrchestrationEP -->  
              <endpoint address="net.tcp://BizTalk Server Computer:8122/btsloadtest" binding="netTcpBinding" bindingConfiguration="netTcpBinding" contract="System.ServiceModel.Channels.IRequestChannel" name="BTSOrchestrationEP" />  
            </client>  
          </system.serviceModel>  
          <appSettings>  
            <!-- Folder containing test messages -->  
            <add key="testMessageFolder" value="C:\Projects\LoadTest\BTSLoad\TestMessages" />  
            <add key="ClientSettingsProvider.ServiceUri" value="" />  
          </appSettings>  
        </configuration>  
        ```  
  
    5.  Haga clic en el **archivo** menú en Visual Studio 2010 y, a continuación, haga clic en **guardar todo**.  
  
### <a name="add-a-test-message-to-the-project"></a>Agregar un mensaje de prueba al proyecto  
 Para fines de este ejemplo, BizTalk Server, ubicaciones de recepción y envío puertos se configurarán para utilizar pasan a través de canalizaciones y no realizará ninguna validación de documento. Siga estos pasos para agregar un mensaje de prueba al proyecto:  
  
1.  Inicie el Bloc de notas. Haga clic en **iniciar**, haga clic en **ejecutar** y tipo **el Bloc de notas** en el **ejecutar** cuadro de diálogo.  
  
2.  Copie el texto siguiente en el Bloc de notas y guardar como "C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml"  
  
    ```  
    <BTSLoadTest xmlns="http://Microsoft.BizTalk.Samples.BTSLoadTest">  
    <MessageText>  
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    This is sample message text. This is sample message text. This is sample message text. This is sample message text.   
    </MessageText>  
    </BTSLoadTest>  
    ```  
  
3.  Cierre el Bloc de notas.  
  
> [!IMPORTANT]  
>  Este archivo deberá van a guardar en la misma ruta de acceso con el mismo nombre de archivo en cada equipo del agente de prueba de carga si se utilizan varios equipos de agente de prueba de carga para pruebas de carga.  
  
### <a name="add-necessary-references-to-the-project-and-build-the-test-project"></a>Agregar las referencias necesarias al proyecto y compile el proyecto de prueba  
  
1.  En el Explorador de soluciones, haga clic en el **referencias** carpeta para el proyecto BTSLoad y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo Agregar referencia, haga clic en el **.NET** pestaña y utilice la combinación de teclado y mouse CTRL + clic para seleccionar simultáneamente los siguientes espacios de nombres. NET:  
  
    -   System.Configuration  
  
    -   System.Runtime.Serialization  
  
    -   System.ServiceModel.Channels  
  
    -   System.ServiceModel  
  
    -   System.Web.Extensions  
  
    -   System.Xml  
  
3.  Después de seleccionar los espacios de nombres, haga clic en **Aceptar** para agregar estos ensamblados como referencias al proyecto de prueba BTSLoad.  
  
4.  Haga clic con el **BTSLoad** del proyecto y, a continuación, haga clic en **generar** para compilar el proyecto en el ensamblado BTSLoad.