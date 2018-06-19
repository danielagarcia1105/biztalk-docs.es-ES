---
title: 'Cómo: enrutar un mensaje único a varios destinatarios mediante una lista de distribución itinerarios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c493b33081e540a4e18d6d20e4813cdddad894a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010477"
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a>Cómo: enrutar un mensaje único a varios destinatarios mediante una lista de distribución itinerarios
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo utilizar el lenguaje de diseñador específico de dominio (DSL) para crear un itinerario que enruta un mensaje a tres destinatarios distintos con una resolución estática y el adaptador de archivo de BizTalk Server.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear un itinerario con tres resoluciones estáticas para enrutar mensajes a varios destinatarios.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>Para crear un modelo DSL itinerario de ESB  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en **ItineraryLibrary**, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, haga clic en **ItineraryDsl** en el panel Plantillas.  
  
4.  En el **nombre** , escriba **RecipientList**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de RecipientList.itinerary. En la ventana Propiedades de RecipientList, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo, en la **nombre de archivo** , escriba **C:\HowTos\Itineraries\RecipientList**y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **en rampa** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteToThreeRecipients**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
        > [!NOTE]
        >  Esta propiedad define que el proceso llevará a cabo en una canalización (mensajería). Como alternativa, si el proceso llevará a cabo en una orquestación, establezca la **extensor del servicio de itinerario** propiedad **extensor de orquestación**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNaOrderDoc**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
3.  Haga clic en el **resolución** colección de la **RouteToThreeRecipients** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **FirstResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\First%MessageID%.xml**.  
  
        > [!NOTE]
        >  Ha agregado el primero de los tres resoluciones para este servicio itinerario. Ahora, agregará dos resoluciones más para enrutar el mensaje a los destinatarios adicionales.  
  
4.  Haga clic en el **resolución** colección de la **RouteToThreeRecipients** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SecondResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\Second%MessageID%.xml**.  
  
5.  Haga clic en el **resolución** colección de la **RouteToThreeRecipients** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ThirdResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\Third%MessageID%.xml**.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteToThreeRecipients** elemento del modelo.  
  
7.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **RouteToThreeRecipients** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendThreeMessages**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
8.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **RouteToThreeRecipients** elemento del modelo y la **SendThreeMessages** elemento del modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendThreeMessages**y, a continuación, haga clic en **controladores de envío**.  
  
9. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteToThreeRecipients** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
10. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendThreeMessages** elemento del modelo.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **RecipientList** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y, a continuación, observe la creación de su itinerario XML (RecipientList.xml).  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **RecipientList.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar la "itinerario se cargó correctamente: mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\Patterns. Seleccione NAOrderDoc.xml y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a C:\HowTos\Out\\. Compruebe que los mensajes siguientes se han escrito en el directorio:  
  
    -   First%MessageID%.Xml  
  
    -   Second%MessageID%.Xml  
  
    -   Third%MessageID%.Xml  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)