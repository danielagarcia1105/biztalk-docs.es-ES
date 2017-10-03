---
title: "Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud-respuesta | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfc7c7d572f3370e87df2f03d392a993116b74d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a>Cómo: transformar un mensaje y una ruta a un extremo de servicio mediante un patrón de intercambio de mensajes de solicitud y respuesta
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear un itinerario de solicitudes y respuestas que se puede utilizar con un aumento bidireccional. Se creará una lista de distribución para recibir un mensaje, transformar el mensaje, envía el mensaje a un servicio y devolver el mensaje de respuesta de servicio para el remitente del mensaje original.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear una lista de distribución itinerario con un servicio de itinerarios de transformación que implementa una asignación de Microsoft BizTalk Server.  
  
-   Configurar el itinerario para enrutar el mensaje transformado a un extremo de servicio.  
  
-   Configurar el itinerario para devolver el mensaje de respuesta de servicio a la entidad remitente original.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>Para crear un modelo DSL itinerario de ESB  
  
1.  En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **nombre** , escriba **RequestResponse**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **RequestResponse.itinerary**. En el **RequestResponse** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **respuesta de solicitud es** la lista desplegable, haga clic en **True**.  
  
    2.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    3.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    4.  En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\RequestResponse**y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary.Response**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **MapNAOrderToCNOrder**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.  
  
3.  Haga clic en el **resolución** colección de la **MapNAOrderToCNOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheMap**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.  
  
4.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **MapNAOrderToCNOrder** elemento del modelo.  
  
5.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **MapNAOrderToCNOrder** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToCNService**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
6.  Haga clic en el **resolución** colección de la **RouteToCNService** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticallySpecifyTheService**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **WCF-BasicHttp**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.  
  
    5.  Haga clic en el **Target Namespace** propiedad y, a continuación, escriba **http://globalbank.esb.dynamicresolution.com/canadianservices**.  
  
    6.  Haga clic en el **acción** propiedad y, a continuación, escriba **submitOrder**.  
  
7.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **MapNAOrderToCNOrder** elemento de modelo para el **RouteToCNService** elemento del modelo.  
  
8.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToCNService** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **InvokeCNService**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionSolicitResp**.  
  
9. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToCNService** elemento del modelo y la **InvokeCNService**elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **InvokeCNService**y, a continuación, haga clic en **controladores de envío**.  
  
10. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteToCNService** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
11. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **InvokeCNService** elemento del modelo.  
  
12. Haga clic en la superficie de diseño y, a continuación, haga clic en **validar**.  
  
    > [!NOTE]
    >  Valida el itinerario; no es necesario volver a conectar fuera de rampa con el aumento con el fin de enviar el mensaje de respuesta a la entidad que lo solicita. Mediante el uso de un aumento bidireccional, el mensaje final se devuelve automáticamente a la entidad que lo solicita.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **RequestResponse** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries. Tenga en cuenta la creación de su itinerario XML (RequestResponse.xml).  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación.  
  
3.  En el **opciones del servicio Web** sección, seleccione la **dos servicios de manera** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
4.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **RequestResponse.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
5.  Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.  
  
6.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
7.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
8.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
9. En el **resultados** cuadro, observe el nodo de raíz del mensaje es **submitOrderResponse** y el espacio de nombres predeterminado es... **canadianservices**.  
  
    > [!NOTE]
    >  Si el mensaje de respuesta requiere transformación adicional antes de que la respuesta se envía a la entidad de solicitud, debe utilizar una canalización que contiene el componente de reenviador de ESB. Para obtener un ejemplo de esta funcionalidad, consulte la [instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: transformar un mensaje y enrutar el mensaje resultante a una ubicación de archivo con una lista de distribución itinerario](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)  
  
-   [Instalar y ejecutar el ejemplo de servicios Web varios](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)