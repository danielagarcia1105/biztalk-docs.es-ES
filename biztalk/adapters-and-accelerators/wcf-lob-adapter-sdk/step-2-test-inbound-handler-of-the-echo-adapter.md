---
title: 'Paso 2: Probar el controlador de entrada del adaptador de eco | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86dede9b-6b7e-4901-9c79-b75bfee9155f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94e17bcc987949b9ca25ac25db9a1789ebe980eb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967042"
---
# <a name="step-2-test-inbound-handler-of-the-echo-adapter"></a>Paso 2: Probar el controlador de entrada del adaptador de eco
![Paso 2 de 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")  
  
 **Tiempo en completarse:** 10 minutos  
  
 En este paso, pruebe el servicio de entrada proporcionado por el adaptador de eco. Para ello, mediante Visual Studio, agregar adaptador de servicio de referencia de complemento de Visual Studio y código personalizado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para completar este paso, debe haber completado [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md). Este paso se puede realizar independientemente de [paso 1: controlador de salida de prueba del adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-1-test-outbound-handler-of-the-echo-adapter.md).  
  
## <a name="create-a-visual-studio-project"></a>Crear un proyecto de Visual Studio  
  
1.  Inicie Visual Studio.  
  
2.  En Visual Studio, en el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.  
  
3.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **aplicación de consola**.|  
    |**Nombre**|Tipo de **ConsumeEchoAdapter_Inbound**.|  
    |**Ubicación**|Tipo de **C:\Tutorials**.|  
    |**Nombre de solución**|Tipo de **ConsumeEchoAdapter_Inbound**.|  
  
4.  Haga clic en **Aceptar**.  
  
5.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
## <a name="browse-search-and-generate-the-wcf-service"></a>Examinar, buscar y generar el servicio WCF  
  
1.  En el panel de la solución de Visual Studio, haga clic en **ConsumeEchoAdapter_Inbound** del proyecto y luego elija **Agregar referencia de servicio de adaptador** para iniciar el complemento de agregar Adapter Service Reference.  
  
2.  En el **Agregar referencia de servicio de adaptador** , elija un enlace. Para ello, elija **echoAdapterBindingV2**.  
  
3.  A continuación, configure las propiedades de conexión y adaptador, haga clic en **configurar**.  Se abrirá la **configurar el adaptador** pantalla.  
  
4.  En el **configurar el adaptador** pantalla, seleccione la **propiedades de enlace** ficha para configurar las propiedades del adaptador. Tenga en cuenta que las categorías de eco adaptador personalizadas **entrada** y **varios** se muestran. En el **varios** categoría, haga clic en **InboundFileSystemWatcherFolder** y, a continuación, escriba el directorio que desea supervisar.  
  
5.  Haga clic en **Aceptar** para cerrar el **configurar el adaptador** pantalla y volver a la **Agregar referencia de servicio de adaptador** pantalla.  
  
6.  A continuación, haga clic en **conectar** para conectar con el adaptador de eco (y el sistema de línea de negocio hipotético admite). Transcurridos unos instantes, debería cambiar el estado de la conexión a **conectado** y el árbol de categorías (en **seleccione una categoría**) se debe rellenar.  
  
7.  Para ver las operaciones de entrada disponibles, cambie la **tipo de contrato de servicio** a **(operaciones de entrada) de servicio**.  
  
8.  En el árbol de categorías, haga clic en **categoría principal**. Esto rellenará la lista de categorías y operaciones con una sola operación de entrada disponibles. No hay ninguna categoría.  
  
9. En el **categorías y operaciones disponibles**, seleccione la **OnReceiveEcho** operación. Haga clic en **agregar** para realizar la parte de operaciones seleccionadas de la interfaz WCF generada.  
  
10. Haga clic en **Aceptar** para generar la interfaz WCF. Esto agrega un archivo de configuración de aplicación (app.config), una interfaz WCF (EchoAdapterBindingInterface.cs) y un servicio WCF (EchoAdapterBindingService.cs) al proyecto.  
  
11. Haga clic en **archivo** en el **Visual Studio** menú y elija **guardar todo**.  
  
## <a name="test-the-echo-adapter"></a>Probar el adaptador de eco  
  
1.  En el Explorador de soluciones, haga doble clic en el **EchoAdapterBindingService.cs** archivo.  
  
2.  En el editor de Visual Studio, dentro de la **OnReceiveEcho** método, reemplace la implementación existente con lo siguiente:  
  
    ```csharp  
    System.Console.WriteLine("path = " + path + ", len = " + length);  
    ```  
  
3.  En el Explorador de soluciones, haga doble clic en el **Program.cs** archivo.  
  
4.  En el editor de Visual Studio, dentro del método principal, agregue el código siguiente para hospedar el servicio WCF.  
  
    ```csharp  
    try  
    {  
        // Create a ServiceHost for the EchoServiceImpl type  
        // and use the base address from app.config  
        System.ServiceModel.ServiceHost host = new System.ServiceModel.ServiceHost(typeof(EchoAdapterBindingNamespace.EchoAdapterBindingService));  
  
        // Open the ServiceHost to start listening for messages  
        host.Open();  
  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost  
        host.Close();  
    }  
    catch (TimeoutException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    catch (System.ServiceModel.CommunicationException ex)  
    {  
        Console.WriteLine(ex.Message);  
        Console.WriteLine();  
    }  
    ```  
  
5.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
6.  Presione F5 para iniciar el ejemplo.  
  
7.  Coloque un archivo con la extensión "txt" en el directorio especificado anteriormente en este tutorial. Debería ver información similar al siguiente en la ventana de salida del programa:  
  
     **El servicio está listo.**  
  
     **Presione \<ENTRAR\> para terminar el servicio.**  
  
     **ruta de acceso = file:///C:/Tutorial/InboundTest/InboundTest.txt, len = 229179**  
  
8.  Presione la tecla ENTRAR para detener el servicio.  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 En este paso, ha creado una aplicación de prueba para la operación de entrada expuesta por el adaptador de eco desarrollado en [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md). Para ello, crea un proyecto de Visual Studio, genera un servicio WCF y proporciona código para hospedar el servicio de WCF. Por último, ejecutó la aplicación de prueba.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Este es el último paso del tutorial. Para obtener más información acerca de las operaciones de entrada, consulte `Microsoft.ServiceModel.Channels.Common.IInboundHandler`. Para ver un ejemplo SDK que se muestra cómo hospedar un servicio WCF que requiere autenticación, descargar el código de adaptador y prueba de eco en [http://go.microsoft.com/fwlink/?LinkID=96184](http://go.microsoft.com/fwlink/?LinkID=96184).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 2: Utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [Tutorial 1: Desarrollar el adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)