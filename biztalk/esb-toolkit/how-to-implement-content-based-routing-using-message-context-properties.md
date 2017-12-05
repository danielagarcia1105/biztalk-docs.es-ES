---
title: "Cómo: implementar el enrutamiento por contenidos mediante propiedades de contexto de mensaje | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be099923fea9d5dbb22559203b297fadf5dd1fdc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a>Cómo: implementar el enrutamiento por contenidos mediante propiedades de contexto de mensaje
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo utilizar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Diseñador de itinerario para crear un itinerario que selecciona un destinatario del mensaje en función de la propiedad de contexto de mensaje y, a continuación, enruta un mensaje a dicho destinatario con el agente de itinerario del servicio de mensajería.  
  
 En este tema, se realizarán los pasos siguientes:  
  
-   Crear un itinerario con un agente itinerario y dos servicios de enrutamiento con resoluciones estáticos.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
> [!NOTE]
>  Ningún servicio de agente basado en la orquestación se proporciona en la implementación actual.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>Para crear un modelo DSL de itinerario de ESB  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en **ItineraryLibrary**, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.  
  
4.  En el **nombre** , escriba **ChoiceRouter**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario. En el **ChoiceRouter** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, haga clic en el botón de puntos suspensivos (...) junto a la **archivo XML de itinerario** propiedad.  
  
    3.  En el **exportar modo** lista de propiedades de lista desplegable, haga clic en **Strict**.  
  
    4.  En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\ChoiceRouter** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.  
  
    > [!NOTE]
    >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de a la base de datos de itinerario, puede probar el itinerario utilizando la aplicación de cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En la ventana Propiedades de OnRamp1, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **de Service Broker itinerario** elemento a la superficie del diseñador del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo. En el **ItineraryBrokerService1**, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteBrokerService**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **extensor de Broker de mensajería**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.  
  
3.  Haga clic en el **filtro** colección y, a continuación, haga clic en **Agregar nuevo filtro**. En el **Filter1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ASMXFilter**.  
  
    2.  Haga clic en el **filtro** la lista desplegable de implementación y, a continuación, haga clic en **filtro XPath**.  
  
    3.  Haga clic en el **expresión** propiedad y, a continuación, escriba **recuento (/ ContextProperties/propiedad [@name= 'InboundTransportLocation'] [contiene (., 'ProcessItinerary.asmx')]) > 0**.  
  
4.  Haga clic en el **filtro** colección y, a continuación, haga clic en **Agregar nuevo filtro**. En el **Filter1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **WCFFilter**.  
  
    2.  Haga clic en el **filtro implementación** lista desplegable y haga clic en **filtro XPath**.  
  
    3.  Haga clic en el **expresión** propiedad y, a continuación, escriba **recuento (/ ContextProperties/propiedad [@name= 'InboundTransportLocation'] [contiene (., ' ESB. ItineraryServices.WCF')]) > 0**.  
  
5.  Haga clic en el **resolución** colección de la **RouteBrokerService** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ResolverBrokerRoute**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **MessageContext resolución extensión**.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteBrokerService** elemento del modelo.  
  
7.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquela bajo la **RouteBrokerService** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToFileFromASMX**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
8.  Haga clic en el **resolución** colección de la **RouteToFileFromASMX** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ResolverFromAsmx**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **c:\howtos\out\asmx%MessageId%.xml**.  
  
9. En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToFileFromASMX** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendASMXOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
10. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToFileFromASMX** elemento del modelo y la **SendASMXOrder**elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilterASMX**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendASMXOrder**y, a continuación, haga clic en **controladores de envío**.  
  
11. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteToFileFromASMX** elemento de modelo para el **SendPortFilterASMX** elemento del modelo.  
  
12. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilterASMX** elemento de modelo para el **SendASMXOrder** elemento del modelo.  
  
13. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha del **RouteBrokerService** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToFileFromWCF**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
14. Haga clic en el **resolución** colección de la **RouteToFileFromWCF** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ResolverFromWCF**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **c:\howtos\out\wcf%MessageId%.xml**.  
  
15. En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToFileFromWCF** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendWCFOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
16. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToFileFromWCF** elemento del modelo y la **SendWCFOrder**elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilterWCF**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendWCFOrder**y, a continuación, haga clic en **controladores de envío**.  
  
17. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteToFileFromWCF** elemento de modelo para el **SendPortFilterWCF** elemento del modelo.  
  
18. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilterWCF** elemento de modelo para el **SendWCFOrder** elemento del modelo.  
  
19. En el cuadro de herramientas, arrastre un **itinerario Outport** al borde derecho del elemento del modelo **RouteBrokerService**. En el **ItineraryBrokerOutPort1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **puerto WCF**.  
  
    2.  En el **filtro** la lista desplegable, haga clic en **WCFFilter**.  
  
    3.  En el **resolución** la lista desplegable, haga clic en **ResolverBrokerRoute**.  
  
20. En el cuadro de herramientas, arrastre un **itinerario Outport** elemento de modelo para el borde inferior del **RouteBrokerService**. En el **ItineraryBrokerOutPort1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ASMX puerto**.  
  
    2.  En el **filtro** la lista desplegable, haga clic en **ASMXFilter**.  
  
    3.  En el **resolución** la lista desplegable, haga clic en **ResolverBrokerRoute**.  
  
21. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **puerto WCF** elemento de modelo para el **RouteToFileFromWCF** elemento del modelo.  
  
22. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **puerto ASMX** elemento de modelo para el **RouteToFileFromASMX** elemento del modelo.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
> [!NOTE]
>  Debe exportar el itinerario dos veces: una vez en XML y una hora para la base de datos para probar el enrutamiento mediante el agente.  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y, a continuación, observe la creación de su itinerario XML (ChoiceRouter.xml).  
  
3.  En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
4.  En la ventana Propiedades, haga clic en **base de datos de itinerario exportador** en el **modelo exportador** lista desplegable.  
  
5.  En la ventana Propiedades, establezca la **base de datos de itinerario** cadena de conexión de la propiedad para que apunte a la base de datos de itinerario.  
  
6.  En el **estado de itinerario** propiedad lista desplegable seleccione **implementadas**.  
  
7.  En Visual Studio, haga clic en la superficie de diseño de la **ChoiceRouter** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **ChoiceRouter.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para cerrar el mensaje "Itinerario cargó correctamente".  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\Patterns\HowTos. Seleccione NAOrderDoc.xml y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para cerrar el mensaje de confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se han escrito los mensajes ASMX%MessageID%.xml a este directorio.  
  
9. Haga clic en el cliente de prueba de itinerario **usar el servicio de WCF** casilla de verificación. En el **itinerario nombre** , escriba **ChoiceRouter**y, a continuación, haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para cerrar el mensaje de confirmación.  
  
10. En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se han escrito los mensajes WCF%MessageID%.xml a este directorio.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Cómo: Enrutar dinámicamente un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocio](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)