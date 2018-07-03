---
title: 'Cómo: enrutar dinámicamente un mensaje en función del contexto de mensaje mediante una directiva de reglas de negocio | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7406b0daed4374241bb92fdcb4afcdcd5acd77b9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973893"
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a>Cómo: enrutar dinámicamente un mensaje en función del contexto de mensaje mediante una directiva de reglas de negocio
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo crear un itinerario que determina los puntos de conexión de mensaje, según las propiedades de contexto de mensaje, mediante una directiva de motor de reglas de negocios (BRE) de BizTalk Server y, a continuación, enruta el mensaje mediante el adaptador de archivo de BizTalk Server.  
  
 En este tema de procedimientos, se completará los pasos siguientes:  
  
-   Crear una directiva de reglas de negocios para evaluar el tipo de mensaje.  
  
-   Crear una lista de distribución de itinerarios para enrutar dinámicamente mediante una directiva de reglas de negocio.  
  
-   Pruebe el itinerario mediante la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
 **Para crear una directiva BRE para enrutar un mensaje mediante las propiedades de contexto de mensaje**  
  
1. Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **compositor**.  
  
2. En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**. Nombre de la directiva **RouteBasedOnMessageType**.  
  
   **Para agregar una regla de enrutamiento para los pedidos de América del Norte**  
  
3. En el **RouteBasedOnMessageType** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**. Nombre de la regla **SetNAOrderEndpoint**.  
  
4. En la ventana de la regla, haga clic en **condiciones**, apunte a **predicados**y, a continuación, haga clic en **igual**.  
  
5. En el Explorador de hechos, expanda el **ESB. ContextInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **tipo de contexto de mensaje** hecho a la **argumento1** nodo bajo  **Condiciones**.  
  
   > [!NOTE]
   >  El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varios vocabularios que pueden usarse para crear reglas. Algunas de estas deben reemplazar o ampliada con sus propios vocabularios. Por ejemplo, el **DynamicRunTimeMaptypes** directiva tiene definiciones para las asignaciones proporcionadas en el **GlobalBank** ejemplos.  
  
6. Haga clic en el **argumento2** nodo y, a continuación, escriba **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**  
  
7. En el Explorador de hechos, expanda el **ESB. EndPointInfo** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **establecer ubicación de transporte de salida de punto de conexión** definición a **acciones**.  
  
8. Haga clic en  **\<una cadena vacía\>** y, a continuación, escriba **C:\HowTos\Out\NorthAmerica%MessageID%.xml**  
  
9. En el Explorador de hechos, arrastre el **establecer tipo de transporte saliente de punto de conexión** definición a **acciones**.  
  
10. En el Explorador de hechos, expanda el **ESB. TansportTypes** vocabulario, expanda **versión 1.0**y, a continuación, arrastre el **adaptador proveedores** definición a **\<una cadena vacía\>**.  
  
11. En el panel Acciones, expanda el **adaptador proveedores** lista desplegable y, a continuación, haga clic en **archivo**.  
  
    **Para publicar e implementar la directiva**  
  
12. En el Explorador de directivas, bajo el **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.  
  
13. En el Explorador de directivas, bajo el **RouteBasedOnMessageType** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
    **Para crear un modelo de lenguaje de específicos de dominio (DSL) itinerarios de ESB**  
  
14. En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
15. En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.  
  
16. En el **nombre** , escriba **MessageType**y, a continuación, haga clic en **agregar**.  
  
    **Para configurar las propiedades de los itinerarios**  
  
17. En Visual Studio, haga clic en la superficie de diseño de **MessageType.itinerary**. En el **MessageType** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración extensor** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo el **nombre de archivo** , escriba **C:\HowTos\Itineraries\MessageType**y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso le permite exportar el itinerario como XML en una ubicación de archivos local. Exportar un itinerario en una ubicación de archivos local, en lugar de a la base de datos de itinerario, permite probar el itinerario mediante la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema de procedimientos.  
  
    **Para definir la estructura de los itinerarios**  
  
18. En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveOrders**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **rampa de ESB extensor**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
19. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **vía** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **BreRoute**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **mensajería extensor**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca el **extensor del servicio de itinerarios** propiedad **orquestación extensor**.  
  
    3.  En el **contenedor** desplegable lista, expanda **ReceiveOrders**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
20. Haga clic en el **resolución** colección de la **BreRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ByMessageType**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **Bre resolución extensión**.  
  
    3.  En el **directiva** la lista desplegable, haga clic en **RouteBasedOnMessageType v 1.0**.  
  
21. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveOrders** elemento de modelo para el **BreRoute** elemento de modelo.  
  
22. En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BreRoute** elemento de modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendBasedOnType**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **fuera de rampa ESB extensor**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
23. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BreRoute** elemento de modelo y la **SendBasedOnType** modelo elemento. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **fuera de rampa extensor**.  
  
    3.  En el **fuera de rampa** desplegable lista, expanda **SendBasedOnType**y, a continuación, haga clic en **controladores de envío**.  
  
24. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **BreRoute** elemento de modelo para el **SendPortFilter** elemento de modelo.  
  
25. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendBasedOnType** elemento de modelo.  
  
    **Para exportar el modelo para su uso con el cliente de prueba de itinerario**  
  
26. En Visual Studio, haga clic en la superficie de diseño de la **MessageType** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
27. Guarde todos los artefactos de proyecto.  
  
28. En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (MessageType.xml).  
  
    **Para probar el itinerario**  
  
29. Abra la aplicación de ejemplo de cliente de prueba de itinerario mediante el acceso directo que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
30. En el cliente de prueba de itinerario, desactive la **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
31. En el **abrir archivo itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **MessageType.xml**y, a continuación, haga clic en **abierto** para cargar el itinerario.  
  
32. Haga clic en **Aceptar** para borrar el **itinerario se cargó correctamente** mensaje.  
  
33. En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **carga mensaje** cuadro.  
  
34. En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abierto** para cargar el mensaje de prueba.  
  
35. Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
36. En el Explorador de Windows, vaya a C:\HowTos\Out\\. Compruebe que se ha escrito el mensaje NorthAmerica%MessageID%.xml en el directorio.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Cómo: Transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución de itinerarios](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [Cómo: Implementar el enrutamiento basado en contenido mediante una directiva de reglas de negocio para un tipo de mensaje conocido](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)