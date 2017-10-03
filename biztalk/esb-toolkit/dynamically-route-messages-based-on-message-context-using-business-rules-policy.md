---
title: "Cómo: dinámicamente enrutar un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 717e0180ba92d49751342e00a4d0367832084135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a>Cómo: dinámicamente enrutar un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocios
## <a name="goal"></a>Objetivo  
 En esta sección se muestra cómo crear un itinerario que determina los puntos de conexión de mensaje, en función de propiedades de contexto de mensaje con un [!INCLUDE[prague](../includes/prague-md.md)] directiva del motor de reglas de negocios (BRE) y, a continuación, las rutas el mensaje mediante la [!INCLUDE[prague](../includes/prague-md.md)] adaptador de archivo.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear una directiva de reglas de negocios para evaluar el tipo de mensaje.  
  
-   Crear una lista de distribución itinerario para dirigir de manera dinámica mediante una directiva de reglas de negocios.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
 **Para crear una directiva del BRE para enrutar un mensaje con propiedades de contexto de mensaje**  
  
1.  Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione  **[!INCLUDE[prague](../includes/prague-md.md)]** y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
2.  En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**. Nombre de la directiva **RouteBasedOnMessageType**.  
  
 **Para agregar una regla de enrutamiento para los pedidos de América del Norte**  
  
1.  En el **RouteBasedOnMessageType** directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva regla**. Nombre de la regla **SetNAOrderEndpoint**.  
  
2.  En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.  
  
3.  En el Explorador de hechos, expanda el **ESB. ContextInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **tipo de mensaje de contexto** hecho a la **argumento1** nodo bajo  **Condiciones**.  
  
    > [!NOTE]
    >  El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varios vocabularios que pueden usarse para crear reglas. Algunos de ellos deben reemplazarse o ampliada con sus propios vocabularios. Por ejemplo, el **DynamicRunTimeMaptypes** directiva tiene definiciones de las asignaciones proporcionadas en el **GlobalBank** ejemplos.  
  
4.  Haga clic en el **argumento2** nodo y, a continuación, escriba **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**  
  
5.  En el Explorador de hechos, expanda el **ESB. EndPointInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **establecer ubicación de transporte saliente de punto final** definición a **acciones**.  
  
6.  Haga clic en  **\<una cadena vacía >**y, a continuación, escriba **C:\HowTos\Out\NorthAmerica%MessageID%.xml**  
  
7.  En el Explorador de hechos, arrastre el **establecer tipo de transporte saliente de punto final** definición a **acciones**.  
  
8.  En el Explorador de hechos, expanda el **ESB. TansportTypes** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **proveedores de adaptador** definición a  **\<una cadena vacía >**.  
  
9. En el panel Acciones, expanda la **proveedores de adaptador** lista desplegable y, a continuación, haga clic en **archivo**.  
  
 **Para publicar e implementar la directiva**  
  
1.  En el Explorador de directivas, en la **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 (sin guardar)**y, a continuación, haga clic en **publicar**.  
  
2.  En el Explorador de directivas, en la **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
 **Para crear un modelo de lenguaje de específico de dominio (DSL) itinerarios de ESB**  
  
1.  En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **nombre** , escriba **MessageType**y, a continuación, haga clic en **agregar**.  
  
 **Para configurar las propiedades de la itinerario**  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **MessageType.itinerary**. En el **MessageType** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\MessageType**y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Exportar un itinerario en una ubicación de archivo local, en lugar de a la base de datos de itinerario, habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
 **Para definir la estructura de la itinerario**  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveOrders**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **BreRoute**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveOrders**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
3.  Haga clic en el **resolución** colección de la **BreRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ByMessageType**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **Bre resolución extensión**.  
  
    3.  En el **directiva** la lista desplegable, haga clic en **RouteBasedOnMessageType v1.0**.  
  
4.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveOrders** elemento de modelo para el **BreRoute** elemento del modelo.  
  
5.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BreRoute** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendBasedOnType**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
6.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BreRoute** elemento del modelo y la **SendBasedOnType** modelo elemento. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendBasedOnType**y, a continuación, haga clic en **controladores de envío**.  
  
7.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **BreRoute** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
8.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendBasedOnType** elemento del modelo.  
  
 **Para exportar el modelo para su uso con el cliente de prueba de itinerario**  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **MessageType** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (MessageType.xml).  
  
 **Para probar el itinerario**  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **MessageType.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a C:\HowTos\Out\\. Compruebe que se ha escrito el mensaje NorthAmerica%MessageID%.xml en el directorio.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)  
  
-   [Uso de resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md)