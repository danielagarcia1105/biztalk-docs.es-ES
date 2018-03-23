---
title: 'Paso 1: Probar el controlador de salida del adaptador de eco | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad4a8164-a584-436f-b20b-4c884f6e2b37
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba2b1d6586588d17c58c0ca9a74cb11a7a9bd9f2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="step-1-test-outbound-handler-of-the-echo-adapter"></a>Paso 1: Probar el controlador de salida del adaptador de eco
![Paso 1 de 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **Tiempo para completar:** 15 minutos  
  
 En este paso, probará las tres operaciones de salida proporcionadas por el adaptador de eco. Se hace esto con Visual Studio, agregar adaptador de servicio de referencia de complemento de Visual Studio y código personalizado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para completar este paso, debe haber completado [Tutorial 1: desarrollar el adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md).  
  
## <a name="create-a-visual-studio-project"></a>Crear un proyecto de Visual Studio  
  
1.  Inicie Visual Studio.  
  
2.  En Visual Studio, en el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.  
  
3.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Tipos de proyecto**|Haga clic en **Visual C#**.|  
    |**Plantillas**|Haga clic en **aplicación de consola**.|  
    |**Nombre**|Tipo de **ConsumeEchoAdapter_Outbound**.|  
    |**Ubicación**|Tipo de **C:\Tutorials**.|  
    |**Nombre de solución**|Tipo de **ConsumeEchoAdapter_Outbound**.|  
  
4.  Haga clic en **Aceptar**.  
  
5.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
## <a name="browse-search-and-generate-the-wcf-client"></a>Examinar, buscar y generar al cliente de WCF  
  
1.  En el panel de la solución de Visual Studio, haga clic en **ConsumeEchoAdapter_Outbound** del proyecto, y luego elija **Agregar referencia de servicio de adaptador** para iniciar el complemento de agregar Adapter Service Reference.  
  
2.  En el **Agregar referencia de servicio de adaptador** , elija un enlace. Para ello, elija **echoAdapterBindingV2**.  
  
3.  A continuación, configure las propiedades de conexión y adaptador, haga clic en **configurar...** .  Esto le llevará a la **configurar el adaptador** pantalla.  
  
4.  En el **configurar el adaptador** pantalla, seleccione la **propiedades de URI** ficha para configurar las propiedades de conexión. Tenga en cuenta que se muestran las categorías de eco adaptador personalizadas: **conexión** y **formato**. En el **formato** categoría, cambio **EchoInUpperCase** a **True**.  
  
5.  En el **configurar el adaptador** pantalla, seleccione la **propiedades de enlace** ficha para configurar las propiedades del adaptador. Tenga en cuenta que las categorías de eco adaptador personalizadas **entrada** y **varios** se muestran. En el **varios** categoría, cambio **recuento** a **3**.  
  
6.  Haga clic en **Aceptar** para cerrar el **configurar el adaptador** pantalla y volver a la **Agregar referencia de servicio de adaptador** pantalla.  
  
7.  A continuación, haga clic en **conectar** para conectar con el adaptador de eco (y el sistema de línea de negocio hipotético admite). Transcurridos unos instantes, debería cambiar el estado de la conexión a **conectado** y el árbol de categorías (en **seleccione una categoría**) se debe rellenar.  
  
8.  En el árbol de categorías, haga clic en **categoría principal**. Esto rellenará la lista de categorías disponibles y las operaciones con tres operaciones de salida. No habrá ninguna categoría.  
  
    > [!NOTE]
    >  El tipo de contrato predeterminado es saliente. Resultados de la categoría coincidirá con este tipo de contrato.  
  
9. En el **categorías y operaciones disponibles**, seleccione las tres operaciones. Cuando hay un gran número de operaciones, podría usar búsqueda para restringir la selección; en este caso, hay sólo tres. Haga clic en **agregar** para realizar la parte de operaciones seleccionadas de la interfaz WCF generada.  
  
10. Haga clic en **Aceptar** para generar la interfaz WCF. Esto agregará un archivo de configuración de aplicación (app.config) y un proxy de cliente WCF (EchoAdapterBindingClient.cs) al proyecto.  
  
11. Haga clic en **archivo** en el menú de Visual Studio y elija **guardar todo**.  
  
## <a name="configure-adapter-authentication"></a>Configurar la autenticación de adaptador  
  
1.  En el panel de la solución de Visual Studio, haga doble clic en **app.config**.  
  
2.  Buscar el `address` de atributo en el `endpoint` elemento. Debería tener un aspecto similar al siguiente:  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=False&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
     Cambio **enableAuthentication** de **False** a **True** tal y como se muestra a continuación. Esto requerirá la aplicación que realiza la llamada para pasar las credenciales para el adaptador.  
  
    ```  
    <endpoint address="echov2://lobhostname/lobapplication?enableAuthentication=True&echoInUpperCase=True"  
        binding="echoAdapterBindingV2" bindingConfiguration="EchoAdapterBinding"  
        contract="EchoOutboundContract" name="EchoAdapterBinding_EchoOutboundContract" />  
    ```  
  
3.  Guarde la solución haciendo clic en **archivo** en Visual Studio menú y eligiendo **guardar todo**.  
  
## <a name="create-a-sample-xml-file"></a>Crear un archivo XML de ejemplo  
  
1.  Iniciar una instancia del Bloc de notas. Mediante el menú Inicio, haga clic en **todos los programas** &#124; **Accesorios** y, a continuación, elija **el Bloc de notas**.  
  
2.  Copie los siguientes datos de ejemplo en el editor en el Bloc de notas.  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <ns0:greeting xmlns:ns0="echov2://microsoft.adapters.samples.echov2/PreDefinedTypes">  
      <ns0:address>  
        <ns0:street1>123 Microsoft Way</ns0:street1>  
        <ns0:street2>Building # 4599</ns0:street2>  
        <ns0:city>Redmond</ns0:city>  
        <ns0:state>WA</ns0:state>  
        <ns0:zip>98052</ns0:zip>  
      </ns0:address>  
      <ns0:greetingText>Welcome to Redmond!</ns0:greetingText>  
    </ns0:greeting>              
    ```  
  
3.  En el menú el Bloc de notas, haga clic en **archivo** y, a continuación, elija **Guardar como...** . Escriba "CustomGreetingInstance.xml" para el nombre de archivo y elija Unicode para la codificación y, a continuación, guardarlo en el directorio del proyecto o en otra ubicación adecuada. Tenga en cuenta la ruta de acceso completa y nombre de archivo para consultarlos más adelante.  
  
4.  Cierre el editor de texto cuando el archivo se guardó correctamente.  
  
## <a name="test-the-echo-adapter"></a>Probar el adaptador de eco  
  
1.  En el Explorador de soluciones, haga doble clic en el **Program.cs** archivo.  
  
2.  En el editor de Visual Studio, dentro de la **Main** método, agregue la siguiente línea de código para crear una instancia del cliente WCF generado.  
  
    ```csharp  
    EchoOutboundContractClient client = new EchoOutboundContractClient();  
    ```  
  
3.  Ahora, agregue código que establece las credenciales para el adaptador. Cuando se habilita la autenticación en el adaptador de eco, comprobará la existencia de un nombre de usuario pero no comprobará el valor.  
  
    ```csharp  
    // pass client credentials  
    client.ClientCredentials.UserName.UserName = "username";  
    ```  
  
4.  Continúe agregando código para invocar la operación de EchoStrings.  
  
    ```csharp  
    // Invoke EchoStrings()  
    Console.WriteLine("Invoking EchoStrings() method against the adapter...");  
    string[] response = client.EchoStrings("Bonjour!");  
    foreach (string data in response)  
    {  
        Console.WriteLine(data);  
    }  
    ```  
  
5.  Continúe agregando código para invocar la operación de EchoGreetings.  
  
    ```csharp  
    // Invoke EchoGreetings()  
    Console.WriteLine("\nInvoking EchoGreetings() method against the adapter...");  
    microsoft.adapters.samples.echov2.Types.Greeting greeting = new microsoft.adapters.samples.echov2.Types.Greeting();  
    greeting.id = Guid.NewGuid();  
    greeting.sentDateTime = DateTime.Now;  
    greeting.greetingText = "Hello World!";  
    greeting.name = new microsoft.adapters.samples.echov2.Types.Name();  
    greeting.name.salutation = microsoft.adapters.samples.echov2.Types.Salutation.Miss;  
    greeting.name.firstName = "Jane";  
    greeting.name.middleName = "Z.";  
    greeting.name.lastName = "Smith";  
    microsoft.adapters.samples.echov2.Types.Greeting[] greetingArray = client.EchoGreetings(greeting);  
    foreach (microsoft.adapters.samples.echov2.Types.Greeting data in greetingArray)  
    {  
        Console.WriteLine(data.id + " " + data.sentDateTime + " " + data.greetingText + " " + data.name.firstName );  
    }  
    ```  
  
6.  Continúe agregando código para invocar la operación de EchoCustomGreetingsFromFile.  
  
    ```csharp  
    // Invoke EchoCustomGreetingFromFile()  
    Console.WriteLine("\nInvoking EchoCustomGreetingFromFile() method against the adapter ...");  
    // Copy the sample data from CustomGreeting-instance.xml file and place in appropriate folder  
    // as specified in the operation parameter  
    microsoft.adapters.samples.echov2.PreDefinedTypes.CustomGreeting   
    // change the Uri to point to the greeting instance xml file you created  
    customGreeting = client.EchoCustomGreetingFromFile(new Uri(@"c:\CustomGreetingInstance.xml"));  
    Console.WriteLine(customGreeting.greetingText + " " + customGreeting.address.city);  
    client.Close();  
    Console.ReadLine();  
    ```  
  
7.  En la EchoCustomGreetingsFromFile probar el código, asegúrese de que el saludo personalizado usa el archivo creado en un procedimiento anterior. Cambie el código para reflejar la ubicación del archivo.  
  
8.  En Visual Studio, en el **archivo** menú, haga clic en **guardar todo**.  
  
9. Ejecute la aplicación. Debería ver un resultado similar al siguiente:  
  
     **Invocar el método de EchoStrings() con el adaptador...**  
  
     **¡Bonjour!**  
  
     **¡Bonjour!**  
  
     **¡Bonjour!**  
  
     **¡Bonjour!**  
  
     **¡Bonjour!**  
  
     **Invocar el método de EchoGreetings() con el adaptador...**  
  
     **179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**  
  
     **179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**  
  
     **179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**  
  
     **179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**  
  
     **179665bb-db21-42ac-810E-77ebfa99d460 13/9/2007 3:18:07 P.M. Hola a todos! Julia**  
  
     **Invocar el método de EchoCustomGreetingFromFile() con el adaptador...**  
  
     **Bienvenido a Redmond. Redmond**  
  
10. Presione la tecla ENTRAR para detener el programa.  
  
## <a name="what-did-i-just-do"></a>¿Simplemente lo que hacía?  
 En este paso, ha creado una aplicación de prueba para las operaciones de salida tres expuestas por el adaptador de eco desarrollado en el Tutorial 1. Para ello, crea un proyecto de Visual Studio, genera un servicio WCF y proporciona código para hospedar el servicio de WCF. Por último, ejecutó la aplicación de prueba.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Para probar la operación de entrada, continúe con [paso 2: probar el controlador de entrada del adaptador de eco](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md).  
  
## <a name="see-also"></a>Vea también  
  [Tutorial 2: Utilizar el adaptador de eco de .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)   
 [Paso 2: Probar el controlador de entrada del adaptador de Echo](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-test-inbound-handler-of-the-echo-adapter.md)