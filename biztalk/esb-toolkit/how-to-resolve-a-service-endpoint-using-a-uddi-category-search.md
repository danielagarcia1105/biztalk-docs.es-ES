---
title: "Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 61ac5d37-5529-4509-a948-415453944e01
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 207c50c8f2dc61c0e7e86f865fec470dae4d2e84
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-category-search"></a>Cómo: resolver un extremo de servicio mediante una búsqueda de la categoría UDDI
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo utilizar el lenguaje de ESB diseñador específico de dominio (DSL) para crear una lista de distribución itinerario que usa el Universal Description, Discovery, y solucionador Integration (UDDI) 3 para localizar un punto de conexión de servicio con una categoría de búsqueda. En este escenario, el extremo de servicio será un punto de conexión de archivo publicado en UDDI.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear una lista de distribución itinerario para resolver un extremo de servicio.  
  
-   Configurar el itinerario para enrutar el mensaje a un extremo de servicio con una resolución de 3 de UDDI.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-an-itinerary-model"></a>Para crear un modelo itinerario  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, escriba **UDDI3CategorySearch** en el **nombre** cuadro y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **UDDI3CategorySearch.itinerary**. En el **UDDI3CategorySearch** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\UDDI3CategorySearch** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento del modelo a la superficie de diseño. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **CategoryRoute**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **mensajería Extender**.  
  
    3.  En el **contenedor** lista desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  
  
    4.  En el **nombre del servicio** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**  
  
3.  Haga clic en el **resolución** colección de la **CategoryRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **CategorySearch**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **Uddi3 resolución extensión**.  
  
    3.  En el **Moniker de resolución** la lista desplegable, haga clic en **UDDI3**.  
  
    4.  Haga clic en el **categoría búsqueda** propiedad y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
    5.  En el **Editor de propiedades de nombre de valor** cuadro de diálogo, haga clic en **agregar**.  
  
    6.  Haga clic en el **nombre** propiedad y, a continuación, escriba **uddi:esb:biztalkapplication**.  
  
    7.  Haga clic en el **valor** propiedad y, a continuación, escriba **GlobalBank.ESB**.  
  
    8.  En el **Editor de propiedades de nombre de valor** cuadro de diálogo, haga clic en **agregar**.  
  
    9. Haga clic en el **nombre** propiedad y, a continuación, escriba **uddi:esb:portname**.  
  
    10. Haga clic en el **valor** propiedad y, a continuación, escriba **OrderFileServicev3**.  
  
    11. En el **Editor de propiedades de nombre de valor** cuadro de diálogo, haga clic en **agregar**.  
  
    12. Haga clic en el **nombre** propiedad y, a continuación, escriba **uddi:esb:version**.  
  
    13. Haga clic en el **valor** propiedad y, a continuación, escriba **1**.  
  
    14. Haga clic en **Aceptar** para cerrar el **Editor de propiedades de nombre de valor** cuadro de diálogo.  
  
4.  Haga clic en el **CategorySearch** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
    > [!NOTE]
    >  Compruebe el resultado que aparece en la ventana de salida.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **CategoryRoute** elemento del modelo.  
  
6.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **CategoryRoute** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
7.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **CategoryRoute** elemento del modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
8.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **CategoryRoute** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
9. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento del modelo.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **UDDI3CategorySearch** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (UDDI3CategorySearch.xml).  
  
#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **UDDI3CategorySearch.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione NAOrderDoc.xml y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a **C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out** y compruebe que la **%MessageID%.xml** mensaje se ha escrito en el directorio.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de claves de enlace de UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)