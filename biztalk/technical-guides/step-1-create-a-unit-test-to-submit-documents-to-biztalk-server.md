---
title: 'Paso 1: Crear una prueba unitaria para enviar documentos a BizTalk Server | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 688b14e4-bb16-4d12-86b8-37b8b6808472
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8016bc237b55c2404a21c91e2e68d78fdd21bcf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-a-unit-test-to-submit-documents-to-biztalk-server"></a><span data-ttu-id="e13cd-102">Paso 1: Crear una prueba unitaria para enviar documentos a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e13cd-102">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>
<span data-ttu-id="e13cd-103">Servidores de aplicaciones del equipo como el servidor BizTalk Server están diseñados para realizar determinadas tareas en nombre de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e13cd-103">Computer application servers such as BizTalk Server are designed to perform particular tasks on behalf of users.</span></span> <span data-ttu-id="e13cd-104">Estas tareas se inician como las solicitudes de cliente que se envían al servidor de aplicaciones como mensajes que cumplan con un estándar que entienda el servidor de aplicaciones, a través de un protocolo que entienda el servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e13cd-104">These tasks are initiated as client requests sent to the application server as messages that conform to a standard that the application server understands, via a protocol that the application server understands.</span></span> <span data-ttu-id="e13cd-105">Por ejemplo, los clientes pueden iniciar el procesamiento de correo electrónico mediante el envío de mensajes de correo electrónico de internet a un servidor de correo electrónico a través del protocolo SMTP.</span><span class="sxs-lookup"><span data-stu-id="e13cd-105">For example, clients may initiate processing of email by sending internet e-mail messages to an email server via the SMTP protocol.</span></span> <span data-ttu-id="e13cd-106">Del mismo modo, procesan los servidores web cliente HTML o las solicitudes ASP, servidores de base de datos procesan las solicitudes de cliente SQL y BizTalk Server puede procesar mensajes de cliente con un formato conforme a varios estándares de mensaje del sector mediante varios protocolos estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="e13cd-106">Likewise, web servers process client HTML or ASP requests, database servers process client SQL requests and BizTalk Server can process client messages formatted in compliance with multiple industry message standards using numerous industry standard protocols.</span></span> <span data-ttu-id="e13cd-107">Normalmente, la capacidad de carga de trabajo de un servidor de aplicaciones se mide por el número de mensajes que el servidor de aplicaciones puede procesar en un período de tiempo determinado.</span><span class="sxs-lookup"><span data-stu-id="e13cd-107">The workload capacity of an application server is typically measured by the number of messages that the application server can process in a given time period.</span></span> <span data-ttu-id="e13cd-108">La capacidad de carga de trabajo de BizTalk Server del mismo modo se mide como el número medio de "documentos recibidos por segundo", "documentos procesados por segundo" y "orquestaciones completadas por segundo" durante un período prolongado de tiempo, por ejemplo, un día de trabajo o incluso un semana laboral.</span><span class="sxs-lookup"><span data-stu-id="e13cd-108">The workload capacity of BizTalk Server is likewise measured as the average number of “documents received per second”, “documents processed per second” and/or “orchestrations completed per second” over an extended period of time, such as a busy workday or even a work week.</span></span> <span data-ttu-id="e13cd-109">Funcionalidad de prueba de carga de Visual Studio 2010 puede simular un perfil de carga de hasta cientos de usuarios que acceden al mismo tiempo a una aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="e13cd-109">Visual Studio 2010 load test functionality can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="e13cd-110">Esta funcionalidad de la prueba de carga proporciona métricas de tiempo real para los indicadores clave de rendimiento seleccionado, así como la capacidad para almacenar estas métricas en una base de datos para su posterior análisis.</span><span class="sxs-lookup"><span data-stu-id="e13cd-110">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="e13cd-111">Pruebas de este describe el uso de proyectos de prueba de Visual Studio con el fin de una aplicación de BizTalk Server, incluido cómo crear unidad de prueba de carga de documento, cómo crear pruebas de carga y cómo configurar las pruebas de carga para capturar datos del contador de rendimiento necesarios para determinar el rendimiento sostenible máximo (MST) de una aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e13cd-111">This document desribes the use of Visual Studio Test projects for the purpose of load testing a BizTalk Server application, including how to create unit tests, how to create load tests and how to configure load tests to capture performance counter data required to determine the Maximum Sustainable Throughput (MST) of a BizTalk Server application.</span></span>  
  
## <a name="creating-a-visual-studio-unit-test-to-submit-documents-to-biztalk-server"></a><span data-ttu-id="e13cd-112">Crear una prueba unitaria de Visual Studio para enviar documentos a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e13cd-112">Creating a Visual Studio Unit Test to Submit Documents to BizTalk Server</span></span>  
 <span data-ttu-id="e13cd-113">Hace referencia a una prueba unitaria de Visual Studio la [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) de espacio de nombres que proporciona varias clases que proporcionan compatibilidad para pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="e13cd-113">A Visual Studio Unit test references the [Microsoft.VisualStudio.TestTools.UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) namespace which supplies several classes that provide support for unit testing.</span></span> <span data-ttu-id="e13cd-114">De especial importancia, el [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.Microsoft.com/fwlink/?) LinkID = 132293) espacio de nombres incluye la [Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.Microsoft.com/fwlink/?) LinkID = 208233) clase para almacenar información que se proporciona a las pruebas unitarias y el [Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.Microsoft.com/fwlink/?) LinkID = 208235) clase se utiliza para definir métodos de prueba.</span><span class="sxs-lookup"><span data-stu-id="e13cd-114">Of particular importance, the [UnitTesting](http://go.microsoft.com/fwlink/?LinkID=132293) (http://go.microsoft.com/fwlink/?LinkID=132293) namespace includes the [Microsoft.VisualStudio.TestTools.UnitTesting.TestContext](http://go.microsoft.com/fwlink/?LinkID=208233) (http://go.microsoft.com/fwlink/?LinkID=208233) class to store information provided to Unit tests and the [Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute](http://go.microsoft.com/fwlink/?LinkID=208235) (http://go.microsoft.com/fwlink/?LinkID=208235) class is used to define Test methods.</span></span> <span data-ttu-id="e13cd-115">Para fines de BizTalk Server de prueba de carga, los métodos de prueba deben especificar el mensaje que se va a cargar y el punto de conexión/URL a la que debe enviarse el mensaje.</span><span class="sxs-lookup"><span data-stu-id="e13cd-115">For purposes of load testing BizTalk Server, Test methods should specify the message to be loaded and the endpoint/URL to which the message should be sent.</span></span> <span data-ttu-id="e13cd-116">La URL de extremo, a continuación, dará servicio a medida que se crea el punto de entrada de mensaje en BizTalk Server cuando la ubicación de recepción de BizTalk correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e13cd-116">The endpoint/URL will then serve as the message entry point into BizTalk Server when a corresponding BizTalk receive location is created.</span></span>  
  
 <span data-ttu-id="e13cd-117">A efectos de ilustración, el código de ejemplo en este tema describe los métodos de prueba que usan la [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.Microsoft.com/fwlink/?) LinkID = 208238) clase para enviar mensajes a extremos de servicio que utilizan el extremo de net.tcp WCF y se supervisan mediante WCF-Custom de BizTalk: adaptador de recepción.</span><span class="sxs-lookup"><span data-stu-id="e13cd-117">For purposes of illustration, the sample code in this topic describes Test methods which utilize the [System.ServiceModel.ChannelFactory(TChannel)](http://go.microsoft.com/fwlink/?LinkId=208238) (http://go.microsoft.com/fwlink/?LinkID=208238) class to send messages to service endpoints that use the WCF net.tcp endpoint and are monitored by the BizTalk WCF-Custom receive adapter.</span></span> <span data-ttu-id="e13cd-118">Los extremos de servicio para los mensajes de prueba se definen en el archivo de configuración de la aplicación (app.config) del proyecto de prueba.</span><span class="sxs-lookup"><span data-stu-id="e13cd-118">Service endpoints for test messages are defined in the Application Configuration (app.config) file of the Test project.</span></span>  
  
 <span data-ttu-id="e13cd-119">Para obtener más información acerca de las pruebas de unidad de Visual Studio Vea [Anatomía de una prueba unitaria](http://go.microsoft.com/fwlink/?LinkID=208232) (http://go.microsoft.com/fwlink/?LinkID=208232).</span><span class="sxs-lookup"><span data-stu-id="e13cd-119">For more information about Visual Studio Unit Tests see [Anatomy of a Unit Test](http://go.microsoft.com/fwlink/?LinkID=208232) (http://go.microsoft.com/fwlink/?LinkID=208232).</span></span>  
  
 <span data-ttu-id="e13cd-120">Siga los pasos descritos en las secciones siguientes para crear un proyecto de prueba con una prueba unitaria para enviar documentos a uno o más equipos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e13cd-120">Follow the steps in the sections below to create a Test project with a Unit Test to submit documents to one or more BizTalk Server computers.</span></span> <span data-ttu-id="e13cd-121">Estos pasos se completaron con Visual Studio 2010 Ultimate Edition.</span><span class="sxs-lookup"><span data-stu-id="e13cd-121">These steps were completed using Visual Studio 2010 Ultimate Edition.</span></span>  
  
### <a name="set-visual-studio-2010-test-project-options"></a><span data-ttu-id="e13cd-122">Establecer opciones de proyecto de prueba de Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="e13cd-122">Set Visual Studio 2010 Test Project Options</span></span>  
  
1.  <span data-ttu-id="e13cd-123">Inicie Visual Studio 2010 Ultimate edition.</span><span class="sxs-lookup"><span data-stu-id="e13cd-123">Launch Visual Studio 2010 Ultimate edition.</span></span> <span data-ttu-id="e13cd-124">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Visual Studio 2010** y, a continuación, haga clic en **Microsoft Visual Studio 2010**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-124">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2010** and then click **Microsoft Visual Studio 2010**.</span></span>  
  
2.  <span data-ttu-id="e13cd-125">En Visual Studio 2010, haga clic en **herramientas** y, a continuación, haga clic en **opciones** para mostrar la **opciones** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e13cd-125">In Visual Studio 2010, click **Tools** and then click **Options** to display the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="e13cd-126">Haga clic para expandir **herramientas de prueba** y, a continuación, haga clic en **proyecto de prueba** para mostrar las opciones para la creación de nuevos proyectos de prueba.</span><span class="sxs-lookup"><span data-stu-id="e13cd-126">Click to expand **Test Tools** and then click **Test Project** to display options for creation of new test projects.</span></span>  
  
4.  <span data-ttu-id="e13cd-127">Establecer el **idioma predeterminado del proyecto de prueba:** a **proyecto de prueba de Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-127">Set the **Default test project language:** to **Visual C# test project**.</span></span>  
  
5.  <span data-ttu-id="e13cd-128">En la opción de **seleccionar los archivos que se agregará a cada nuevo proyecto de prueba, de forma predeterminada:** seleccione **proyecto de prueba de Visual C#**y desactive todos los tipos de prueba de Visual C# de proyectos excepto deprueba **Prueba unitaria**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-128">Under the option to **Select the files that will be added to each new test project, by default:** select **Visual C# test project**, and uncheck all of the test types for Visual C# test projects except for **Unit Test**.</span></span>  
  
6.  <span data-ttu-id="e13cd-129">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="e13cd-129">Click **OK** to close the **Options** dialog box.</span></span>  
  
### <a name="create-a-new-visual-studio-2010-solution-with-a-test-project"></a><span data-ttu-id="e13cd-130">Crear una nueva solución de Visual Studio 2010 con un proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="e13cd-130">Create a new Visual Studio 2010 Solution with a Test Project</span></span>  
  
1.  <span data-ttu-id="e13cd-131">Cree la carpeta **C:\Projects** en el equipo de Visual Studio 2010 Ultimate.</span><span class="sxs-lookup"><span data-stu-id="e13cd-131">Create the folder **C:\Projects** on the Visual Studio 2010 Ultimate computer.</span></span>  
  
2.  <span data-ttu-id="e13cd-132">En Visual Studio 2010, haga clic en **archivo**, seleccione **New**y haga clic en **proyecto** para mostrar la **nuevo proyecto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e13cd-132">In Visual Studio 2010 click **File**, point to **New**, and click **Project** to display the **New Project** dialog box.</span></span>  
  
3.  <span data-ttu-id="e13cd-133">En **plantillas instaladas** haga clic para expandir **Visual C#**y haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-133">Under **Installed Templates** click to expand **Visual C#**, and click **Test**.</span></span>  
  
4.  <span data-ttu-id="e13cd-134">En la parte inferior de la **nuevo proyecto** cuadro de diálogo especificar las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e13cd-134">At the bottom of the **New Project** dialog box specify the following options:</span></span>  
  
    -   <span data-ttu-id="e13cd-135">**Nombre:**</span><span class="sxs-lookup"><span data-stu-id="e13cd-135">**Name:**</span></span>  
         <span data-ttu-id="e13cd-136">**BTSLoad**</span><span class="sxs-lookup"><span data-stu-id="e13cd-136">**BTSLoad**</span></span>  
  
    -   <span data-ttu-id="e13cd-137">**Ubicación:**</span><span class="sxs-lookup"><span data-stu-id="e13cd-137">**Location:**</span></span>  
         <span data-ttu-id="e13cd-138">**C:\projects\\**</span><span class="sxs-lookup"><span data-stu-id="e13cd-138">**C:\Projects\\**</span></span>  
  
    -   <span data-ttu-id="e13cd-139">**Nombre de la solución:**</span><span class="sxs-lookup"><span data-stu-id="e13cd-139">**Solution name:**</span></span>  
         <span data-ttu-id="e13cd-140">**LoadTest**</span><span class="sxs-lookup"><span data-stu-id="e13cd-140">**LoadTest**</span></span>  
  
5.  <span data-ttu-id="e13cd-141">Asegúrese de que la opción de **crear directorio para la solución** está activada y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-141">Ensure that the option to **Create directory for solution** is checked and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="e13cd-142">Agregar una carpeta al proyecto BTSLoad; Esta carpeta contendrá los mensajes de prueba que se envíen al servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e13cd-142">Add a folder to the BTSLoad project; this folder will contain test messages to be submitted to BizTalk Server.</span></span> <span data-ttu-id="e13cd-143">En el Explorador de soluciones, haga clic en el proyecto BTSLoad, seleccione **agregar**y haga clic en **nueva carpeta**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-143">In Solution Explorer, right-click the BTSLoad project, point to **Add**, and click **New Folder**.</span></span> <span data-ttu-id="e13cd-144">Un icono de carpeta con el texto resaltado **NewFolder1** aparecerá en el proyecto BTSLoad, escriba **TestMessages** para cambiar el texto resaltado y presione la **ENTRAR** clave Para crear la carpeta C:\Projects\LoadTest\BTSLoad\TestMessages.</span><span class="sxs-lookup"><span data-stu-id="e13cd-144">A folder icon with the highlighted text **NewFolder1** will appear under the BTSLoad project, type **TestMessages** to change the highlighted text and press the **Enter** key to create the folder C:\Projects\LoadTest\BTSLoad\TestMessages.</span></span>  
  
### <a name="update-the-code-in-the-test-project-and-add-an-application-configuration-file-to-the-test-project"></a><span data-ttu-id="e13cd-145">Actualice el código en el proyecto de prueba y agregue un archivo de configuración de aplicación para el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="e13cd-145">Update the Code in the Test Project and add an Application Configuration File to the Test Project</span></span>  
  
1.  <span data-ttu-id="e13cd-146">En el Explorador de soluciones, haga clic para seleccionar **UnitTest1.cs** y reemplace el código existente con la lista de código de ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e13cd-146">In Solution Explorer click to select **UnitTest1.cs** and replace the existing code with the following sample code listing:</span></span>  
  
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
  
2.  <span data-ttu-id="e13cd-147">Agregue un archivo de configuración de aplicación para el proyecto de prueba:</span><span class="sxs-lookup"><span data-stu-id="e13cd-147">Add an Application Configuration file to the Test project:</span></span>  
  
    1.  <span data-ttu-id="e13cd-148">En el Explorador de soluciones, haga clic en el proyecto BTSLoad, seleccione **agregar** y haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-148">In Solution Explorer, right-click the BTSLoad project, point to **Add** and click **New item**.</span></span>  
  
    2.  <span data-ttu-id="e13cd-149">En el **Agregar nuevo elemento** cuadro de diálogo **plantillas instaladas**, haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-149">In the **Add New Item** dialog box, under **Installed Templates**, click **General**.</span></span>  
  
    3.  <span data-ttu-id="e13cd-150">En la lista de elementos que se muestran, haga clic para seleccionar **archivo de configuración de aplicación** y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-150">In the list of items that are displayed click to select **Application Configuration File** and then click **Add**.</span></span>  
  
    4.  <span data-ttu-id="e13cd-151">En el Explorador de soluciones, seleccione el archivo app.config y reemplace el contenido del archivo app.config con la lista debajo del código de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e13cd-151">In Solution Explorer select the app.config file and replace the contents of the app.config file with the sample code listing below:</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="e13cd-152">Para cada punto de conexión de cliente definido en este archivo, *equipo de BizTalk Server* es un marcador de posición para el nombre real de la carga de equipos que llevarán a cabo pruebas con el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e13cd-152">For each client endpoint defined in this file, *BizTalk Server Computer* is a placeholder for the actual name of the BizTalk Server computer(s) that you will perform load testing against.</span></span>  
  
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
  
    5.  <span data-ttu-id="e13cd-153">Haga clic en el **archivo** menú en Visual Studio 2010 y, a continuación, haga clic en **guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-153">Click the **File** menu in Visual Studio 2010 and then click **Save All**.</span></span>  
  
### <a name="add-a-test-message-to-the-project"></a><span data-ttu-id="e13cd-154">Agregar un mensaje de prueba al proyecto</span><span class="sxs-lookup"><span data-stu-id="e13cd-154">Add a Test Message to the Project</span></span>  
 <span data-ttu-id="e13cd-155">Para fines de este ejemplo, BizTalk Server, ubicaciones de recepción y envío puertos se configurarán para utilizar pasan a través de canalizaciones y no realizará ninguna validación de documento.</span><span class="sxs-lookup"><span data-stu-id="e13cd-155">For purposes of this example, BizTalk Server receive location(s) and send port(s) will be configured to use pass through pipelines and will not perform any document validation.</span></span> <span data-ttu-id="e13cd-156">Siga estos pasos para agregar un mensaje de prueba al proyecto:</span><span class="sxs-lookup"><span data-stu-id="e13cd-156">Follow these steps to add a test message to the project:</span></span>  
  
1.  <span data-ttu-id="e13cd-157">Inicie el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e13cd-157">Launch Notepad.</span></span> <span data-ttu-id="e13cd-158">Haga clic en **iniciar**, haga clic en **ejecutar** y tipo **el Bloc de notas** en el **ejecutar** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e13cd-158">Click **Start**, click **Run** and type **Notepad** in the **Run** dialog box.</span></span>  
  
2.  <span data-ttu-id="e13cd-159">Copie el texto siguiente en el Bloc de notas y guardar como "C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml"</span><span class="sxs-lookup"><span data-stu-id="e13cd-159">Copy the following text into Notepad and save as “C:\Projects\LoadTest\BTSLoad\TestMessages\TestXmlDocument.xml”</span></span>  
  
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
  
3.  <span data-ttu-id="e13cd-160">Cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="e13cd-160">Close Notepad.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e13cd-161">Este archivo deberá van a guardar en la misma ruta de acceso con el mismo nombre de archivo en cada equipo del agente de prueba de carga si se utilizan varios equipos de agente de prueba de carga para pruebas de carga.</span><span class="sxs-lookup"><span data-stu-id="e13cd-161">This file will need to be saved to the same path using the same file name on every Load Test Agent computer if multiple Load Test Agent computers are used for load testing.</span></span>  
  
### <a name="add-necessary-references-to-the-project-and-build-the-test-project"></a><span data-ttu-id="e13cd-162">Agregar las referencias necesarias al proyecto y compile el proyecto de prueba</span><span class="sxs-lookup"><span data-stu-id="e13cd-162">Add Necessary References to the Project and Build the Test Project</span></span>  
  
1.  <span data-ttu-id="e13cd-163">En el Explorador de soluciones, haga clic en el **referencias** carpeta para el proyecto BTSLoad y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="e13cd-163">In Solution Explorer, right-click the **References** folder for the BTSLoad project and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e13cd-164">En el cuadro de diálogo Agregar referencia, haga clic en el **.NET** pestaña y utilice la combinación de teclado y mouse CTRL + clic para seleccionar simultáneamente los siguientes espacios de nombres. NET:</span><span class="sxs-lookup"><span data-stu-id="e13cd-164">In the Add Reference dialog box, click the **.NET** tab and use the CTRL+Click keyboard/mouse combination to simultaneously select the following .NET namespaces:</span></span>  
  
    -   <span data-ttu-id="e13cd-165">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="e13cd-165">System.Configuration</span></span>  
  
    -   <span data-ttu-id="e13cd-166">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="e13cd-166">System.Runtime.Serialization</span></span>  
  
    -   <span data-ttu-id="e13cd-167">System.ServiceModel.Channels</span><span class="sxs-lookup"><span data-stu-id="e13cd-167">System.ServiceModel.Channels</span></span>  
  
    -   <span data-ttu-id="e13cd-168">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e13cd-168">System.ServiceModel</span></span>  
  
    -   <span data-ttu-id="e13cd-169">System.Web.Extensions</span><span class="sxs-lookup"><span data-stu-id="e13cd-169">System.Web.Extensions</span></span>  
  
    -   <span data-ttu-id="e13cd-170">System.Xml</span><span class="sxs-lookup"><span data-stu-id="e13cd-170">System.Xml</span></span>  
  
3.  <span data-ttu-id="e13cd-171">Después de seleccionar los espacios de nombres, haga clic en **Aceptar** para agregar estos ensamblados como referencias al proyecto de prueba BTSLoad.</span><span class="sxs-lookup"><span data-stu-id="e13cd-171">After selecting the namespaces click **OK** to add these assemblies as references to the BTSLoad Test project.</span></span>  
  
4.  <span data-ttu-id="e13cd-172">Haga clic con el **BTSLoad** del proyecto y, a continuación, haga clic en **generar** para compilar el proyecto en el ensamblado BTSLoad.</span><span class="sxs-lookup"><span data-stu-id="e13cd-172">Right click the **BTSLoad** project and then click **Build** to compile the project into the BTSLoad assembly.</span></span>