---
title: "Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44451c85-929a-4d13-b0dd-53ea600d0859
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878a6e180aaf7e5f37c5cf98ca0a67790917859a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-implement-content-based-routing-using-a-business-rules-policy-for-a-known-message-type"></a>Cómo: implementar enrutamiento por contenidos mediante una empresa de reglas de directiva para un tipo de mensaje conocido
## <a name="goal"></a>Objetivo  
 En esta sección se muestra cómo crear un itinerario que dinámicamente enruta un mensaje, en función del contenido de un tipo de mensaje conocido (esquema implementado en la base de datos de configuración de Microsoft BizTalk Server), utilizando un negocio de reglas de directiva.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear una directiva de reglas de negocios que se usará para enrutar un mensaje basado en contenido.  
  
-   Crear una lista de distribución itinerario con una resolución BRE para enrutar un mensaje de forma dinámica.  
  
-   Probar el itinerario utilizando la aplicación de ejemplo de cliente de prueba de itinerario.  
  
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
  
#### <a name="to-create-a-bre-policy-to-route-using-custom-message-properties"></a>Para crear una directiva del BRE para enrutar con propiedades personalizadas de mensajes  
 Esta regla utilizará el nombre del cliente para establecer dinámicamente el extremo que se utiliza para enrutar el mensaje.  
  
1.  Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
2.  En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**. Nombre de la directiva **RouteBasedOnCustomerKnownType**.  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-west"></a>Para agregar una regla de enrutamiento de cliente GlobalBank West  
  
1.  En el **RouteBasedOnCustomerKnownType** directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva regla**. Nombre de la regla **SetWestEndpoint**.  
  
2.  En el Explorador de hechos, haga clic en el **esquemas XML** pestaña, haga clic en **esquemas**y, a continuación, haga clic en **examinar**.  
  
3.  En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione **NAOrderDoc.xsd**y, a continuación, haga clic en **abiertos**.  
  
    > [!NOTE]
    >  Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes de Oeste y este que va a usar para las pruebas.  
  
4.  En el Explorador de hechos, haga clic en **NAOrderDoc.xsd**y, a continuación, en el panel Propiedades, haga clic en el **tipo de documento** propiedad y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc** .  
  
    > [!NOTE]
    >  Este es el nombre completo del esquema.  
  
5.  En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.  
  
6.  En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.  
  
7.  En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.  
  
8.  Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.  
  
9. En el Explorador de hechos, haga clic en el **vocabularios** , expanda **ESB. EndPointInfo**y, a continuación, expanda **versión 1.0**.  
  
    > [!NOTE]
    >  El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye varios vocabularios que pueden usarse para crear reglas para su uso en ESB. Algunos de ellos deben reemplazarse o ampliada con sus propios vocabularios. Por ejemplo, el **DynamicRunTimeMaptypes** tiene definiciones de las asignaciones proporcionadas en el **GlobalBank** ejemplos.  
  
10. En el Explorador de hechos, arrastre el **establecer ubicación de transporte saliente de punto final** definición a **acciones**.  
  
11. Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **C:\HowTos\Out\West%MessageID%.xml**.  
  
12. En el Explorador de hechos, arrastre el **establecer tipo de transporte saliente de punto final** definición a **acciones**.  
  
13. En el Explorador de hechos, expanda **ESB. TransportTypes**, expanda **versión 1.0**y, a continuación, arrastre el **proveedores de adaptador** definición a  **\<una cadena vacía\>** .  
  
14. En el **acciones** panel, expanda el **proveedores de adaptador** lista desplegable y, a continuación, haga clic en **archivo**.  
  
#### <a name="to-add-a-routing-rule-for-customer-globalbank-east"></a>Para agregar una regla de enrutamiento para este GlobalBank de cliente  
  
1.  En el Explorador de directivas, haga clic en el **SetWestEndpoint** de regla y, a continuación, haga clic en **copia**.  
  
2.  Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **pegar**.  
  
3.  En el **nombre de nueva regla** cuadro de diálogo, escriba **SetEastEndpoint**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de directivas, haga clic en el **SetEastEndpoint** regla.  
  
5.  En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **Restablecer argumento**.  
  
6.  Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.  
  
7.  En el **acciones** sección, haga clic en **C:\HowTos\Out\West%MessageID%.xml**y, a continuación, haga clic en **Restablecer argumento**.  
  
8.  Haga clic en  **\<una cadena vacía\>**y, a continuación, escriba **C:\HowTos\Out\East%MessageID%.xml**.  
  
#### <a name="to-add-a-routing-rule-for-unknown-customers"></a>Para agregar una regla de enrutamiento para los clientes desconocidos  
  
1.  En la directiva RouteBasedOnCustomerKnownType, haga clic en la versión 1.0 (sin guardar) y, a continuación, haga clic en Agregar nueva regla. Nombre de la regla SetUnknownCustomerEndpoint.  
  
2.  En la ventana de la regla, haga clic en condiciones y, a continuación, haga clic en Agregar operador lógico AND.  
  
3.  En la ventana de la regla, haga clic en, elija predicados y, a continuación, haga clic en Distintode.  
  
4.  En el Explorador de hechos, haga clic en la pestaña esquemas XML, expanda NAOrderDoc.xsd y, a continuación, expanda OrderDoc.  
  
5.  Desde el Explorador de hechos, arrastre el elemento customerName al nodo argumento1 en condiciones.  
  
6.  Haga clic en el nodo argumento2 y, a continuación, escriba GlobalBankWest.  
  
7.  En la ventana de la regla, haga clic en, elija predicados y, a continuación, haga clic en Distintode.  
  
8.  Desde el Explorador de hechos, arrastre el elemento customerName al nodo argumento1 en condiciones.  
  
9. Haga clic en el nodo argumento2 y, a continuación, escriba GlobalBankEast.  
  
10. En el Explorador de hechos, haga clic en la pestaña vocabularios, expanda ESB. EndPointInfo y, a continuación, expanda la versión 1.0.  
  
11. Desde el Explorador de hechos, arrastre la definición de establecer ubicación de transporte saliente de punto de conexión a las acciones.  
  
12. Haga clic en \<una cadena vacía\>, y, a continuación, escriba C:\HowTos\Out\CustomerUnknown%MessageID%.xml.  
  
13. Desde el Explorador de hechos, arrastre la definición de tipo de transporte saliente punto final establecido a las acciones.  
  
14. En el Explorador de hechos, expanda ESB. TransportTypes, expanda versión 1.0 y, a continuación, arrastre la definición de proveedores de adaptador para \<una cadena vacía\>.  
  
15. En el panel Acciones, expanda la lista desplegable de proveedores de adaptador y, a continuación, haga clic en archivo.  
  
#### <a name="to-publish-and-deploy-the-policy"></a>Para publicar e implementar la directiva  
  
1.  En el Explorador de directivas, en la **RouteBasedOnCustomerKnownType** directiva, haga clic derecho **versión 1.0 (sin guardar)**y, a continuación, haga clic en **publicar**.  
  
2.  En el Explorador de directivas, en la **RouteBasedOnCustomerKnownType** directiva, haga clic derecho **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a>Para crear un modelo DSL itinerario de ESB  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.  
  
3.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **nombre** , escriba **CbrKnownType**y, a continuación, haga clic en **agregar**.  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de la itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de **CbrKnownType.itinerary**. En el **CbrKnownType** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  
  
    2.  En el **configuración del dispositivo Extender** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  
  
    3.  En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\CbrKnownType** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.  
  
        > [!NOTE]
        >  Este paso permite exportar el itinerario como XML en una ubicación de archivo local. Al exportar un itinerario en una ubicación de archivo local, en lugar de la base de datos de itinerario habilita las pruebas de la itinerario utilizando la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema "Cómo...".  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de la itinerario  
  
1.  En el cuadro de herramientas, arrastre un **en rampa** elemento del modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **en rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  
  
    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary**.  
  
2.  En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **ReceiveNAOrder** elemento del modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendRegionalOrders**.  
  
    2.  En el **Extender** la lista desplegable, haga clic en **fuera de rampa ESB Extender**.  
  
    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  
  
    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionOneWay**.  
  
3.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **ReceiveNAOrder** elemento del modelo y la **SendRegionalOrders**elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  
  
    2.  En el **extensor del servicio de itinerario** la lista desplegable, haga clic en **Extender fuera de rampa**.  
  
    3.  En el **fuera de rampa** lista desplegable lista, expanda **SendRegionalOrders**y, a continuación, haga clic en **controladores de envío**.  
  
4.  Haga clic en el **resolución** colección de la **SendPortFilter** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  
  
    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **RouteRegionalOrders**.  
  
    2.  En el **nombre del transporte** la lista desplegable, haga clic en **BRE**.  
  
    3.  En el **implementación de la resolución** la lista desplegable, haga clic en **Bre resolución extensión**.  
  
    4.  En el **directiva** la lista desplegable, haga clic en **RouteBasedOnCustomerKnownType**.  
  
    5.  En el **reconoce el formato de mensaje** lista desplegable y haga clic en **True**.  
  
    6.  En el **UseMsg** la lista desplegable, haga clic en **True**.  
  
        > [!NOTE]
        >  Si utiliza la extensión de la resolución de BRE de orquestación, el **recognizeMessageFormat** propiedad debe establecerse en **False**.  
  
5.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **SendPortFilter** elemento del modelo.  
  
6.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendRegionalOrders** elemento del modelo.  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **CbrKnownType** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  
  
2.  Guarde todos los artefactos de proyecto.  
  
3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (CbrKnownType.xml).  
  
#### <a name="to-test-the-itinerary-and-business-rules"></a>Para probar las itinerarios y reglas del negocio  
  
1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario usando el método abreviado que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  
  
2.  En el cliente de prueba de itinerario, desactive el **usar el servicio de WCF** casilla de verificación y, a continuación, haga clic en **carga itinerario**.  
  
3.  En el **archivos abiertos de itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **CbrKnownType.xml**y, a continuación, haga clic en **abiertos** para cargar el itinerario.  
  
4.  Haga clic en **Aceptar** para borrar la **itinerario cargó correctamente** mensaje.  
  
5.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **mensaje de carga** cuadro.  
  
6.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **West.xml**y, a continuación, haga clic en **abiertos** para cargar el mensaje de prueba.  
  
7.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  
  
8.  En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje West%MessageID%.xml en el directorio.  
  
9. Repita el proceso de prueba con el mensaje East.xml.  
  
10. En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje East%MessageID%.xml en el directorio.  
  
11. Repita el proceso de prueba con el mensaje NAOrderDoc.xml.  
  
12. En el Explorador de Windows, vaya a C:\HowTos\Out. Compruebe que se ha escrito el mensaje CustomerUnknown%MessageID%.xml en el directorio.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Cómo: Enrutar dinámicamente un mensaje basado en el contexto del mensaje mediante una directiva de reglas de negocio](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)