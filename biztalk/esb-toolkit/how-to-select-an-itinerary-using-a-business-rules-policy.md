---
title: 'Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f6373a8-d9d6-46c6-95e3-f62dd33c342a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 521b3768251cfcd31defe271a21d4b2d0bc771e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010589"
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a>Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo crear reglas de negocios que pueden usarse para seleccionar un itinerario en función del contenido de un mensaje recibido y cómo configurar el componente de canalización de Selector de itinerario dentro de un genérico itinerario en rampa para llamar a estas reglas. Esta sección describe un escenario empresarial en el que el mensajes se enrutan de manera diferente, en función de la región donde reside el cliente.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Modelos itinerarios para las divisiones del este y de cliente Global Bank.  
  
-   Crear directivas de reglas de negocios que se usará para seleccionar un itinerario para procesar la solicitud.  
  
-   Configurar el componente de canalización de Selector de itinerario para usar una directiva de reglas de negocios para seleccionar el itinerario adecuado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":  
  
-   Crear el mensaje de prueba GlobalBank West.  
  
-   Crear el mensaje de prueba de este GlobalBank.  
  
 Los procedimientos siguientes describen cómo realizar cada una de ellas.  
  
#### <a name="to-create-the-globalbank-west-test-message"></a>Para crear el mensaje de prueba GlobalBank West  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de West.xml.  
  
3.  En el Bloc de notas, abra West.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankWest**.  
  
4.  Guardar West.xml como UTF-8 y, a continuación, cierre el Bloc de notas.  
  
#### <a name="to-create-the-globalbank-east-test-message"></a>Para crear el mensaje de prueba de este GlobalBank  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de East.xml.  
  
3.  En el Bloc de notas, abra East.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankEast**.  
  
4.  Guardar East.xml como UTF-8 y, a continuación, cierre el Bloc de notas.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>Para crear una directiva del motor de reglas de negocios (BRE) para seleccionar un itinerario con propiedades personalizadas de mensajes  
  
1.  Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
2.  En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**. Nombre de la directiva **ResolveItineraryBasedOnCustomer**.  
  
    > [!NOTE]
    >  Este tema "Cómo..." utiliza la misma directiva de reglas de negocios y los itinerarios como los creados en el tema [Cómo: dividir un intercambio y enrutar los mensajes resultantes a varios archivos ubicaciones utilizando distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md). Si ya ha completado esa sección, puede omitir el procedimiento, "para crear y configurar un ESB en rampa" más adelante en este tema.  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>Para agregar una regla de selección de cliente GlobalBank West  
  
1.  En el **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**. Nombre de la regla **SetGlobalBankWestItinerary**.  
  
2.  En el Explorador de hechos, haga clic en el **esquemas XML** pestaña, haga clic en **esquemas**y, a continuación, haga clic en **examinar**.  
  
3.  En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione **NAOrderDoc.xsd**y, a continuación, haga clic en **abiertos**.  
  
    > [!NOTE]
    >  Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes de Oeste y este que va a usar para las pruebas.  
  
4.  En el Explorador de hechos, haga clic en **NAOrderDoc.xsd**, haga clic en el **tipo de documento** propiedad en el panel de propiedades y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  Este es el nombre completo del esquema.  
  
5.  En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.  
  
6.  En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.  
  
7.  En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.  
  
8.  Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.  
  
9. En el Explorador de hechos, haga clic en el **vocabularios** ficha. Expanda el **ESB. Itinerario** vocabulario, expanda **versión 1.1**y, a continuación, arrastre el **nombre del conjunto de itinerario** definición a **acciones**.  
  
10. Haga clic en  **\<una cadena vacía\>** y, a continuación, escriba **GlobalBankWestItinerary**.  
  
    > [!NOTE]
    >  Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de GlobalBank West.  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>Para agregar una regla de selección para este GlobalBank de cliente  
  
1.  En el Explorador de directivas, haga clic en el **SetGlobalBankWestItinerary** de regla y, a continuación, haga clic en **copia**.  
  
2.  Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **pegar**.  
  
3.  En el **nombre de nueva regla** cuadro de diálogo, escriba **SetGlobalBankEastItinerary**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de directivas, haga clic en el **SetGlobalBankEastItinerary** regla.  
  
5.  En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **Restablecer argumento**.  
  
6.  Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.  
  
7.  En el **acciones** sección, haga clic en **GlobalBankWestItinerary**y, a continuación, haga clic en **Restablecer argumento**.  
  
8.  Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **GlobalBankEastItinerary**.  
  
    > [!NOTE]
    >  Más adelante en el tema "Cómo...", creará este itinerario para procesar los mensajes de este GlobalBank.  
  
#### <a name="to-publish-and-deploy-the-policy"></a>Para publicar e implementar la directiva  
  
1.  En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic derecho **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.  
  
2.  En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a>Para crear un modelo de lenguaje de itinerarios específico de dominio (DSL) ESB para los mensajes de GlobalBank West  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.  
  
4.  En el **nombre** , escriba **GlobalBankWestItinerary**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a>Para configurar las propiedades de la itinerario GlobalBank West  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **GlobalBankWestItinerary.itinerary**. En el **GlobalBankWestItinerary** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.  
  
    2.  Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.  
  
    3.  En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).  
  
2.  En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.  
  
    > [!NOTE]
    >  Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio tras la recepción de mensajes. Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar a la resolución de motor de reglas de negocios (BRI) para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
3.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
4.  Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\West%MessageID%.xml**.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento del modelo.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento del modelo.  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>Para exportar el modelo a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankWestItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.  
  
2.  Guarde todos los artefactos de proyecto.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>Para crear un modelo DSL itinerario de ESB para mensaje de este GlobalBank  
  
1.  En Visual Studio, abra C:\HowTos\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.  
  
4.  En el **nombre** , escriba **GlobalBankEastItinerary**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a>Para configurar las propiedades de la itinerario este GlobalBank  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **GlobalBankEastItinerary.itinerary**. En el **GlobalBankEastItinerary** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **base de datos de itinerario exportador**.  
  
    2.  Haga clic en el botón de puntos suspensivos (...) junto a la **base de datos de itinerario** propiedad.  
  
    3.  En el **propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de repositorio itinerarios y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).  
  
2.  En el **estado de itinerario** la lista desplegable, haga clic en **implementadas**.  
  
    > [!NOTE]
    >  Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio cuando se reciben los mensajes. Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar al Solucionador BRI para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **extensión de servicio de ESB en rampa**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
3.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
4.  Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estáticos**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\East%MessageID%.xml**.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento del modelo.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento del modelo.  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>Para exportar el modelo a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankEastItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.  
  
2.  Guarde todos los artefactos de proyecto.  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>Para crear y configurar un ESB rampa  
  
1.  Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.  
  
3.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
4.  En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **OnRamp.Itinerary.HowTo**.  
  
6.  En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba **C:\HowTos\DropFolder**y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>Para configurar el componente de canalización de Selector de itinerario  
  
1.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **canalización de recepción** la lista desplegable, haga clic en **ItinerarySelectReceiveXml**y, a continuación, haga clic en el botón de puntos suspensivos (...) ).  
  
2.  Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **Selector de itinerario** propiedades de componente:  
  
    1.  Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.  
  
    2.  Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.  
  
3.  Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>Para probar el selector itinerario y reglas de negocios  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Copia (no se mueven) los archivos East.xml y West.xml a la carpeta CarpetaDestino.  
  
3.  Vaya a C:\HowTos\Out. Compruebe que los mensajes de East%MessageID%.xml y West%MessageID%.xml se han escrito en el directorio.  
  
    > [!NOTE]
    >  Aunque idénticos salvo por el valor del elemento del cliente, los mensajes se han procesado mediante diferentes itinerarios, basados en la resolución del componente de canalización de Selector de itinerario.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.  
  
5.  Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**. En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos mediante distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Instalación y ejecución del ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)