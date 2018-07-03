---
title: 'Cómo: seleccionar un itinerario mediante una directiva de reglas de negocio | Microsoft Docs'
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
ms.openlocfilehash: 12496da0de4057e96be0b714ad1af048ee6b8ef1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976965"
---
# <a name="how-to-select-an-itinerary-using-a-business-rules-policy"></a>Cómo: seleccionar un itinerario mediante una directiva de reglas de negocio
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo crear reglas de negocios que se pueden usar para seleccionar un itinerario según el contenido de un mensaje recibido y cómo configurar el componente de canalización de Selector de itinerarios dentro de un genérico itinerario en rampa para llamar a estas reglas. Esta sección describe un escenario de negocio en la que el mensajes se enrutan de forma diferente, según la región donde reside el cliente.  
  
 En este tema de procedimientos, se completará los pasos siguientes:  
  
-   Modelos itinerarios para las divisiones del este y de cliente Global Bank.  
  
-   Crear directivas de reglas de negocio que se usará para seleccionar un itinerario para procesar la solicitud.  
  
-   Configurar el componente de canalización de Selector de itinerarios para usar una directiva de reglas de negocio para seleccionar el itinerario adecuado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Complete las tareas siguientes antes de realizar los pasos más adelante en este tema de procedimientos:  
  
- Crear el mensaje de prueba GlobalBank West.  
  
- Crear el mensaje de prueba GlobalBank oriental.  
  
  Los procedimientos siguientes describen cómo realizar cada una de ellas.  
  
#### <a name="to-create-the-globalbank-west-test-message"></a>Para crear el mensaje de prueba GlobalBank West  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de West.xml.  
  
3.  En el Bloc de notas, abra West.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankWest**.  
  
4.  Guardar West.xml como UTF-8 y, a continuación, cierre el Bloc de notas.  
  
#### <a name="to-create-the-globalbank-east-test-message"></a>Para crear el mensaje de prueba GlobalBank oriental  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Crear una copia de NAOrderDoc.xml y, a continuación, el nombre de East.xml.  
  
3.  En el Bloc de notas, abra East.xml y, a continuación, cambie el valor de la **customerName** elemento **GlobalBankEast**.  
  
4.  Guardar East.xml como UTF-8 y, a continuación, cierre el Bloc de notas.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>Para crear una directiva del motor de reglas de negocios (BRE) para seleccionar un itinerario mediante las propiedades de mensaje personalizado  
  
1.  Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **compositor**.  
  
2.  En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**. Nombre de la directiva **ResolveItineraryBasedOnCustomer**.  
  
    > [!NOTE]
    >  En este tema de procedimientos usa la misma directiva de reglas de negocios y los itinerarios como los creados en el tema [Cómo: dividir un intercambio y enrutar los mensajes resultantes a varios archivos ubicaciones utilizando distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md). Si ya ha completado esa sección, puede omitir el procedimiento "para crear y configurar una rampa de ESB" más adelante en este tema.  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>Para agregar una regla de selección para el cliente GlobalBank West  
  
1.  En el **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**. Nombre de la regla **SetGlobalBankWestItinerary**.  
  
2.  En el Explorador de hechos, haga clic en el **esquemas XML** secundario **esquemas**y, a continuación, haga clic en **examinar**.  
  
3.  En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione **NAOrderDoc.xsd**y, a continuación, haga clic en **abierto**.  
  
    > [!NOTE]
    >  Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes oeste y este que usará para las pruebas.  
  
4.  En el Explorador de hechos, haga clic en **NAOrderDoc.xsd**, haga clic en el **tipo de documento** propiedad en el panel de propiedades y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  Este es el nombre completo del esquema.  
  
5.  En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.  
  
6.  En la ventana de la regla, haga clic en **condiciones**, apunte a **predicados**y, a continuación, haga clic en **igual**.  
  
7.  En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.  
  
8.  Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.  
  
9. En el Explorador de hechos, haga clic en el **vocabularios** ficha. Expanda el **ESB. Itinerario** vocabulario, expanda **versión 1.1**y, a continuación, arrastre el **nombre del conjunto de itinerario** definición a **acciones**.  
  
10. Haga clic en  **\<una cadena vacía\>** y, a continuación, escriba **GlobalBankWestItinerary**.  
  
    > [!NOTE]
    >  Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de GlobalBank West.  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>Para agregar una regla de selección para el cliente GlobalBank oriental  
  
1.  En el Explorador de directivas, haga clic en el **SetGlobalBankWestItinerary** de regla y, a continuación, haga clic en **copia**.  
  
2.  Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **pegar**.  
  
3.  En el **nuevo nombre de regla** cuadro de diálogo, escriba **SetGlobalBankEastItinerary**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de directivas, haga clic en el **SetGlobalBankEastItinerary** regla.  
  
5.  En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **reestablecer argumento**.  
  
6.  Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.  
  
7.  En el **acciones** sección, haga clic en **GlobalBankWestItinerary**y, a continuación, haga clic en **reestablecer argumento**.  
  
8.  Haga clic en **\<una cadena vacía\>** y, a continuación, escriba **GlobalBankEastItinerary**.  
  
    > [!NOTE]
    >  Más adelante en el tema de procedimientos, creará este itinerario para procesar los mensajes de Oriente GlobalBank.  
  
#### <a name="to-publish-and-deploy-the-policy"></a>Para publicar e implementar la directiva  
  
1.  En el Explorador de directivas, bajo el **ResolveItineraryBasedOnCustomer** directiva, haga clic derecho **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.  
  
2.  En el Explorador de directivas, bajo el **ResolveItineraryBasedOnCustomer** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
#### <a name="to-create-an-esb-itinerary-domain-specific-language-dsl-model-for-globalbank-west-messages"></a>Para crear un modelo de lenguaje de itinerarios específico de dominio (DSL) ESB para mensajes GlobalBank West  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.  
  
4.  En el **nombre** , escriba **GlobalBankWestItinerary**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-globalbank-west-itinerary"></a>Para configurar las propiedades de los itinerarios GlobalBank West  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **GlobalBankWestItinerary.itinerary**. En el **GlobalBankWestItinerary** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **exportador de base de datos de itinerario**.  
  
    2.  Haga clic en el botón de puntos suspensivos (...) junto a la **Itinerary Database** propiedad.  
  
    3.  En el **las propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de itinerario del repositorio y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).  
  
2.  En el **estado itinerario** la lista desplegable, haga clic en **implementadas**.  
  
    > [!NOTE]
    >  Este paso le permite exportar el itinerario a un repositorio central; itinerarios pueden seleccionarse y adjunta desde este repositorio tras la recepción de mensajes. Más adelante, configurará el componente de canalización de Selector de itinerarios para utilizar a la resolución de motor de reglas de negocios (BRI) para evaluar los mensajes entrantes y seleccionar el itinerario adecuado desde este repositorio.  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de los itinerarios  
  
1.  En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **extensión de servicio de rampa de ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento de modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
3.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento de modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.  
  
    3.  En el **fuera de rampa** desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
4.  Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\West%MessageID%.xml**.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento de modelo.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento de modelo.  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>Para exportar el modelo a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankWestItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora se puede usar el componente Selector de itinerarios.  
  
2.  Guarde todos los artefactos de proyecto.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>Para crear un modelo DSL itinerario de ESB para mensaje GlobalBank oriental  
  
1.  En Visual Studio, abra C:\HowTos\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en el panel Plantillas, haga clic en **ItineraryDsl**.  
  
4.  En el **nombre** , escriba **GlobalBankEastItinerary**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-globalbank-east-itinerary"></a>Para configurar las propiedades del itinerario GlobalBank oriental  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **GlobalBankEastItinerary.itinerary**. En el **GlobalBankEastItinerary** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **exportador de base de datos de itinerario**.  
  
    2.  Haga clic en el botón de puntos suspensivos (...) junto a la **Itinerary Database** propiedad.  
  
    3.  En el **las propiedades de conexión** cuadro de diálogo, elija el servidor SQL Server que hospeda la base de datos de itinerario del repositorio y, a continuación, especifique el nombre de la base de datos (el nombre predeterminado es **EsbItineraryDb**).  
  
2.  En el **estado itinerario** la lista desplegable, haga clic en **implementadas**.  
  
    > [!NOTE]
    >  Este paso le permite exportar el itinerario a un repositorio central; itinerarios pueden seleccionarse y adjunta desde este repositorio cuando se reciben mensajes. Más adelante, configurará el componente de canalización de Selector de itinerarios para utilizar a la resolución BRI para evaluar los mensajes entrantes y seleccionar el itinerario adecuado desde este repositorio.  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de los itinerarios  
  
1.  En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **extensión de servicio de rampa de ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento de modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendNAOrder**.  
  
    2.  En el **extensor** la lista desplegable, haga clic en **extensión de servicio fuera de rampa ESB**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
3.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento de modelo y la **SendNAOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteMessage**.  
  
    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **extensión de servicio fuera de rampa itinerario**.  
  
    3.  En el **fuera de rampa** desplegable lista, expanda **SendNAOrder**y, a continuación, haga clic en **controladores de envío**.  
  
4.  Haga clic en el **resolución** colección de la **RouteMessage** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **StaticResolver**.  
  
    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.  
  
    3.  En el **nombre del transporte** la lista desplegable, haga clic en **archivo**.  
  
    4.  Haga clic en el **transporte ubicación** propiedad y, a continuación, escriba **C:\HowTos\Out\East%MessageID%.xml**.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **RouteMessage** elemento de modelo.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **RouteMessage** elemento de modelo para el **SendNAOrder** elemento de modelo.  
  
#### <a name="to-export-the-model-to-the-itinerary-database"></a>Para exportar el modelo a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankEastItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora se puede usar el componente Selector de itinerarios.  
  
2.  Guarde todos los artefactos de proyecto.  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>Para crear y configurar una rampa de ESB  
  
1.  Haga clic en **iniciar** en la barra de tareas, señale **todos los programas**, apunte a **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.  
  
3.  Haga clic en **ubicaciones de recepción**, apunte a **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
4.  En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de ubicación de recepción** cuadro de diálogo el **nombre** , escriba **OnRamp.Itinerary.HowTo**.  
  
6.  En el **tipo** la lista desplegable, haga clic en **archivo**y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo el **carpeta recepción** , escriba **C:\HowTos\DropFolder**y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>Para configurar el componente de canalización de Selector de itinerarios  
  
1.  En el **propiedades de ubicación de recepción** cuadro de diálogo el **canalización de recepción** la lista desplegable, haga clic en **ItinerarySelectReceiveXml**y, a continuación, haga clic en el botón de puntos suspensivos (...) ).  
  
2.  Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **itinerario Selector** propiedades de componente:  
  
    1.  Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.  
  
    2.  Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.  
  
3.  Haga clic en **Aceptar** para cerrar el **propiedades de ubicación de recepción** cuadro de diálogo.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>Para probar el selector de itinerarios y reglas de negocios  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Copia (no se mueven) los archivos East.xml y West.xml a la carpeta CarpetaDestino.  
  
3.  Vaya a C:\HowTos\Out. Compruebe que los mensajes East%MessageID%.xml y West%MessageID%.xml se han escrito en el directorio.  
  
    > [!NOTE]
    >  Aunque idénticos excepto el valor del elemento de cliente, los mensajes se han procesado mediante itinerarios diferentes, según la resolución del componente de canalización de Selector de itinerarios.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **deshabilitar**.  
  
5.  Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**. En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos mediante distintos itinerarios](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Instalación y ejecución del ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)