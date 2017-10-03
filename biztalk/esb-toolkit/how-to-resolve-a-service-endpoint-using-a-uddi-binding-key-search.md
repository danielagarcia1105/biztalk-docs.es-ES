---
title: "Cómo: resolver un extremo de servicio mediante una búsqueda de la clave de enlace de UDDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a685641-2beb-4153-a9ba-c766679ce48e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e73ecbc5d1ef88fe2b8bdc7f19f56f6f2ae207
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a>Cómo: resolver un extremo de servicio mediante una búsqueda de la clave de enlace de UDDI
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear una lista de distribución itinerario que usa el Universal Description, Discovery, y el solucionador Integration (UDDI) 3 para localizar un punto de conexión de servicio con una clave de enlace búsqueda. En este escenario, el extremo de servicio será un punto de conexión de archivo publicado en UDDI.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear una lista de distribución itinerario para resolver un extremo de servicio.  
  
-   Configurar el itinerario para enrutar el mensaje a un extremo de servicio con una resolución de 3 de UDDI.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-an-itinerary-model"></a>Para crear un modelo itinerario  
  
1.  En [!INCLUDE[vs2010](../includes/vs2010-md.md)], abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **nombre** , escriba **UDDI3BindingKeySearch**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **UDDI3BindingKeySearch.itinerary**. En el **UDDI3BindingKeySearch** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\UDDI3BindingKeySearch** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento del modelo a la superficie de diseño. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeyRoute**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  
  
3.  Haga clic en el **resolución** colección de la **BindingKeyRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeySearch**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **Uddi3 resolución extensión**.  
  
    3.  En el **Moniker de resolución** la lista desplegable, haga clic en **UDDI3**.  
  
    4.  Haga clic en el **clave de enlace** propiedad y, a continuación, escriba **uddi:esb:orderfileservicev3.1**.  
  
4.  Haga clic en el **BindingKeySearch** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
    > [!NOTE]
    >  Compruebe el resultado que aparece en la ventana de salida.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **BindingKeyRoute** elemento del modelo.  
  
6.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BindingKeyRoute** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
7.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BindingKeyRoute** elemento del modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
8.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **BindingKeyRoute** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
9. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento del modelo.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **UDDI3BindingKeySearch** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (UDDI3BindingKeySearch.xml).  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el cuadro de diálogo Abrir archivo de itinerario, vaya a C:\HowTos\Itineraries. Seleccione UDDI3BindingKeySearch.xml y, a continuación, haga clic en Abrir para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Compruebe que se ha escrito el mensaje %MessageID%.xml en el directorio.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Uso de resolución dinámica y enrutamiento](../esb-toolkit/using-dynamic-resolution-and-routing.md)