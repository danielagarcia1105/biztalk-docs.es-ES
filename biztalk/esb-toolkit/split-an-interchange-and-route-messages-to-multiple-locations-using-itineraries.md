---
title: "Cómo: dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos utilizando distintos itinerarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccd46bee-e4a1-4846-8bde-b0460bda1e72
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 538432f548b1403fd9c0cd566b82eb8cb113f737
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-split-an-interchange-and-route-the-resulting-messages-to-multiple-file-locations-using-distinct-itineraries"></a>Cómo: dividir un intercambio y enrutar los mensajes resultantes a varias ubicaciones de archivos utilizando distintos itinerarios
## <a name="goal"></a>Objetivo  
 En esta sección se muestra cómo crear un ESB en rampa que usa el **ItinerarySelectReceiveXml** canalización y cómo configurar los componentes de la canalización para dividir un intercambio de entrada y seleccione el enrutamiento adecuado para la remisión cada mensaje resultante, basado en contexto del mensaje. Selección de itinerarios se resolverá mediante una directiva de reglas de negocios y los mensajes se enrutarán diferente en función de la región donde reside el cliente.  
  
 En este tema "Cómo...", se realizarán los pasos siguientes:  
  
-   Crear un ESB en rampa que divide un intercambio XML.  
  
-   Configurar el componente de canalización de Selector de itinerario para usar una directiva de reglas de negocios para seleccionar el itinerario adecuado.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema "Cómo..." requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar  
 Complete las tareas siguientes antes de realizar los pasos más adelante en este tema "Cómo...":  
  
-   Crear los artefactos necesarios.  
  
-   Agregue un proyecto de esquemas a la solución de patrones.  
  
-   Agregue los artefactos al proyecto de esquemas.  
  
-   Crear una directiva del BRE para seleccionar un itinerario con propiedades personalizadas de mensajes.  
  
-   Agregar una regla de selección de cliente GlobalBank West.  
  
-   Agregar una regla de selección para GlobalBank este cliente.  
  
-   Publique e implemente la directiva.  
  
-   Crear un modelo de lenguaje de itinerarios específico de dominio (DSL) de ESB para los mensajes de GlobalBank West.  
  
-   Configurar las propiedades de la itinerario GlobalBank West.  
  
-   Definir la estructura de la itinerario GlobalBank West.  
  
-   Exportar el modelo GlobalBank West a la base de datos de itinerario.  
  
-   Crear un modelo DSL itinerario de ESB para los mensajes de este GlobalBank.  
  
-   Configurar las propiedades de la itinerario GlobalBank este.  
  
-   Definir la estructura de la itinerario GlobalBank este.  
  
-   Exportar el modelo de este GlobalBank a la base de datos de itinerario.  
  
     Los procedimientos siguientes describen cómo realizar cada una de ellas.  
  
#### <a name="to-create-the-required-artifacts"></a>Para crear los artefactos necesarios  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Crear un nuevo documento de texto denominado OrderDocEnvelope.xsd.  
  
3.  Abra el esquema de OrderDocEnvelope.xsd en el Bloc de notas.  
  
4.  Editar el documento utilizando el código siguiente.  
  
    ```  
    <?xml version="1.0" ?>  
    <xs:schema xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://ESB.BizUnit.Map.Test" targetNamespace="http://ESB.BizUnit.Map.Test" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
      <xs:import schemaLocation="GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc" namespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
      <xs:annotation>  
        <xs:appinfo>  
          <b:schemaInfo is_envelope="yes" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" />  
          <b:references>  
            <b:reference targetNamespace="http://globalbank.esb.dynamicresolution.com/northamericanservices/" />  
          </b:references>  
        </xs:appinfo>  
      </xs:annotation>  
      <xs:element name="OrderEnvelope">  
        <xs:annotation>  
          <xs:appinfo>  
            <b:recordInfo body_xpath="/*[local-name()='OrderEnvelope' and namespace-uri()='http://ESB.BizUnit.Map.Test']" />  
          </xs:appinfo>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element ref="ns0:OrderDoc" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
5.  Guardar OrderDocEnvelope.xsd como UTF-8 y, a continuación, cierre el Bloc de notas.  
  
6.  En la carpeta C:\HowTos, cree un nuevo documento de texto denominado Batch.xml.  
  
7.  En el Bloc de notas, abra Batch.xml.  
  
8.  Editar el documento utilizando el código siguiente.  
  
    ```  
    <?xml version="1.0" ?>  
    <ns0:OrderEnvelope xmlns:ns0="http://ESB.BizUnit.Map.Test">  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankWest</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>10</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>11</ns0:requestType>  
      </ns0:OrderDoc>  
      <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
        <ns0:customerName>GlobalBankEast</ns0:customerName>  
        <ns0:ID>ns0:ID_0</ns0:ID>  
        <ns0:requestType>12</ns0:requestType>  
      </ns0:OrderDoc>  
    </ns0:OrderEnvelope>  
    ```  
  
9. Guarde y cierre Batch.xml.  
  
#### <a name="to-add-a-schemas-project-to-the-patterns-solution"></a>Para agregar un proyecto de esquemas a la solución de patrones  
  
1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  
  
2.  En el Explorador de soluciones, haga clic en **solución 'Patrones'**, seleccione **agregar**y, a continuación, haga clic en **nuevo proyecto**.  
  
3.  En el **Agregar nuevo proyecto** cuadro de diálogo, en el panel tipos de proyecto, haga clic en **proyectos de BizTalk**, y, a continuación, realice lo siguiente:  
  
    1.  En el panel Plantillas, haga clic en **proyecto vacío de servidor BizTalk**.  
  
    2.  En el **nombre** , escriba **Patterns.Schemas**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de soluciones, haga clic en **Patterns.Schemas**y, a continuación, haga clic en **propiedades**.  
  
5.  En la ventana Propiedades, en la **firma** ficha, seleccione la **firmar el ensamblado** casilla de verificación.  
  
6.  En el **elegir un archivo de clave de nombre seguro** la lista desplegable, haga clic en  **\<nuevo... \>**.  
  
7.  En el **crear clave de nombre seguro** diálogo cuadro, configure las siguientes propiedades:  
  
    1.  En el **nombre de archivo de clave** , escriba **división**.  
  
    2.  Desactive el **proteger mi archivo de clave con una contraseña** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
8.  En la ventana Propiedades, en la **implementación** ficha la **nombre de la aplicación** , escriba **Microsoft.Practices.ESB**.  
  
9. Cierre la ventana Propiedades.  
  
#### <a name="to-add-the-artifacts-to-the-schemas-project"></a>Para agregar los artefactos al proyecto de esquemas  
  
1.  En el Explorador de soluciones, haga clic en **Patterns.Schemas**y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el **examinar** pestaña de la **Agregar referencia** cuadro de diálogo, localice y seleccione C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas\bin\Debug\GlobalBank.ESB.DynamicResolution.Schemas.dll y, a continuación, haga clic en **Aceptar**.  
  
3.  En el Explorador de soluciones, haga clic en **Patterns.Schemas**, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.  
  
4.  En el **Agregar elemento existente** cuadro de diálogo, busque y seleccione C:\HowTos\OrderDocEnvelope.xsd y, a continuación, haga clic en **agregar**.  
  
5.  Guarde todos los artefactos de la solución.  
  
6.  En el Explorador de soluciones, haga clic en **Patterns.Schemas**y, a continuación, haga clic en **implementar**.  
  
    > [!NOTE]
    >  Este tema "Cómo..." utiliza la misma directiva de reglas de negocios y los itinerarios como los creados en el [Cómo: seleccionar un itinerario mediante una directiva de reglas de negocios](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md) tema. Si aún no has completado esa sección, complete los siguientes pasos adicionales. Si ha completado esa sección, continuar directamente en la sección "Pasos".  
  
#### <a name="to-create-a-business-rules-engine-bre-policy-to-select-an-itinerary-using-custom-message-properties"></a>Para crear una directiva del motor de reglas de negocios (BRE) para seleccionar un itinerario con propiedades personalizadas de mensajes  
  
1.  Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **Compositor de reglas de negocios**.  
  
2.  En el Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**. Nombre de la directiva **ResolveItineraryBasedOnCustomer**.  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-west"></a>Para agregar una regla de selección de cliente GlobalBank West  
  
1.  En el **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **agregar nueva regla**. Nombre de la regla **SetGlobalBankWestItinerary**.  
  
2.  En el Explorador de hechos, haga clic en el **esquemas XML** pestaña, haga clic en **esquemas**y, a continuación, haga clic en **examinar**.  
  
3.  En el **archivos de esquema** cuadro de diálogo, vaya a C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Source\ESB. DynamicResolution.Schemas, seleccione NAOrderDoc.xsd y, a continuación, haga clic en **abiertos**.  
  
    > [!NOTE]
    >  Éste es el esquema que define el mensaje NAOrderDoc.xml, que se usó para crear los mensajes de Oeste y este que va a usar para las pruebas.  
  
4.  En el Explorador de hechos, haga clic en NAOrderDoc.xsd, haga clic en el **tipo de documento** propiedad en el panel de propiedades y, a continuación, escriba **GlobalBank.ESB.DynamicResolution.Schemas.NAOrderDoc**.  
  
    > [!NOTE]
    >  Este es el nombre completo del esquema.  
  
5.  En el Explorador de hechos, expanda **NAOrderDoc.xsd**y, a continuación, expanda **OrderDoc**.  
  
6.  En la ventana de la regla, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **igual**.  
  
7.  En el Explorador de hechos, arrastre el **customerName** elemento a la **argumento1** nodo bajo **condiciones**.  
  
8.  Haga clic en el **argumento2** nodo y, a continuación, escriba **GlobalBankWest**.  
  
9. En el Explorador de hechos, haga clic en el **vocabularios** ficha. Expanda el **ESB. Itinerario** vocabulario, expanda **versión 1.1**y, a continuación, arrastre el **nombre del conjunto de itinerario** definición a **acciones**.  
  
10. Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **GlobalBankWestItinerary**.  
  
    > [!NOTE]
    >  Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de GlobalBank West.  
  
#### <a name="to-add-a-selection-rule-for-customer-globalbank-east"></a>Para agregar una regla de selección para este GlobalBank de cliente  
  
1.  En el Explorador de directivas, haga clic en el **SetGlobalBankWestItinerary** de regla y, a continuación, haga clic en **copia**.  
  
2.  Haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **pegar**.  
  
3.  En el **nombre de nueva regla** cuadro de diálogo, escriba **SetGlobalBankEastItinerary**y, a continuación, haga clic en **Aceptar**.  
  
4.  En el Explorador de directivas, haga clic en el **SetGlobalBankEastItinerary** regla.  
  
5.  En el **condiciones** sección, haga clic en **GlobalBankWest**y, a continuación, haga clic en **Restablecer argumento**.  
  
6.  Haga clic en **argumento2**y, a continuación, escriba **GlobalBankEast**.  
  
7.  En el **acciones** sección, haga clic en **GlobalBankWestItinerary**y, a continuación, haga clic en **Restablecer argumento**.  
  
8.  Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **GlobalBankEastItinerary.**  
  
    > [!NOTE]
    >  Más adelante en este tema de procedimientos, creará este itinerario para procesar los mensajes de este GlobalBank.  
  
#### <a name="to-publish-and-deploy-the-policy"></a>Para publicar e implementar la directiva  
  
1.  En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 (sin guardar)**y, a continuación, haga clic en **publicar**.  
  
2.  En el Explorador de directivas, en la **ResolveItineraryBasedOnCustomer** directiva, haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-west-messages"></a>Para crear un modelo DSL itinerario de ESB para los mensajes de GlobalBank West  
  
1.  En **Visual Studio**, abra C:\HowTos\Patterns\Patterns.sln.  
  
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
    >  Este paso le permite exportar el itinerario en un repositorio central; itinerarios pueden seleccionarse y se adjuntan desde este repositorio cuando se reciben los mensajes. Más adelante, va a configurar el componente de canalización de Selector de itinerario para utilizar al Solucionador BRI para evaluar los mensajes entrantes y seleccionar el itinerario adecuado de este repositorio.  
  
#### <a name="to-define-the-structure-of-the-globalbank-west-itinerary"></a>Para definir la estructura de la itinerario GlobalBank West  
  
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
  
#### <a name="to-export-the-globalbank-west-model-to-the-itinerary-database"></a>Para exportar el modelo GlobalBank West a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankWestItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.  
  
2.  Guarde todos los artefactos de proyecto.  
  
#### <a name="to-create-an-esb-itinerary-dsl-model-for-globalbank-east-message"></a>Para crear un modelo DSL itinerario de ESB para mensaje de este GlobalBank  
  
1.  En **Visual Studio**, abra C:\HowTos\Patterns.sln.  
  
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
  
#### <a name="to-define-the-structure-of-the-globalbank-east-itinerary"></a>Para definir la estructura de la itinerario este GlobalBank  
  
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
  
#### <a name="to-export-the-globalbank-east-model-to-the-itinerary-database"></a>Para exportar el modelo de este GlobalBank a la base de datos de itinerario  
  
1.  En Visual Studio, haga clic en la superficie de diseño de la **GlobalBankEastItinerary** itinerario y, a continuación, haga clic en **Exportar modelo**.  
  
    > [!NOTE]
    >  El itinerario se ha exportado a la base de datos de itinerario y ahora puede usarse por el componente de Selector de itinerario.  
  
2.  Guarde todos los artefactos de proyecto.  
  
## <a name="steps"></a>Pasos  
  
#### <a name="to-create-and-configure-an-esb-on-ramp"></a>Para crear y configurar un ESB rampa  
  
1.  Haga clic en **iniciar** en la barra de tareas, seleccione **todos los programas**, seleccione **BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Microsoft.Practices.ESB**.  
  
3.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
4.  En el **seleccionar un puerto de recepción** cuadro de diálogo, haga clic en **OnRamp.Itinerary**y, a continuación, haga clic en **Aceptar**.  
  
5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en la **nombre** , escriba **OnRamp.Itinerary.HowTo**.  
  
6.  En el **tipo** la lista desplegable, haga clic en **archivo** y, a continuación, haga clic en **configurar**.  
  
7.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta recepción** , escriba **C:\HowTos\DropFolder**y, a continuación, haga clic en **Aceptar**.  
  
#### <a name="to-configure-the-itinerary-selector-pipeline-component"></a>Para configurar el componente de canalización de Selector de itinerario  
  
1.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **ItinerarySelectReceiveXml** en el **canalización de recepción** lista desplegable lista y, a continuación, haga clic en el botón de puntos suspensivos (...).  
  
2.  Use la **configurar canalización** cuadro de diálogo para configurar lo siguiente **Selector de itinerario** propiedades de componente:  
  
    1.  Haga clic en el **ItineraryFactKey** propiedad y, a continuación, escriba **Resolver.Itinerary**.  
  
    2.  Haga clic en el **ResolverConnectionString** propiedad y, a continuación, escriba **BRI:\\\policy=ResolveItineraryBasedOnCustomer;useMsg=true;recognizeMessageFormat=true;**  
  
    3.  Haga clic en **Aceptar** para cerrar el **configurar canalización** cuadro de diálogo.  
  
        > [!NOTE]
        >  Dado que esta recepción ubicación es desensamblar un intercambio XML, se requiere ninguna configuración de componente de desensamblador XML.  
  
3.  Haga clic en **Aceptar** para cerrar el **propiedades de la ubicación de recepción** cuadro de diálogo.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **OnRamp.Itinerary.HowTo** ubicación de recepción y, a continuación, haga clic en **habilitar**.  
  
#### <a name="to-test-the-itinerary-selector-and-business-rules"></a>Para probar el Selector de itinerario y reglas de negocios  
  
1.  En el Explorador de Windows, vaya a C:\HowTos.  
  
2.  Copia (no se mueven) Batch.xml a la carpeta CarpetaDestino.  
  
3.  Vaya a C:\HowTos\Out. Compruebe que un mensaje de West%MessageID%.xml y dos mensajes East%MessageID%.xml se han escrito en el directorio.  
  
    > [!NOTE]
    >  Aunque los mensajes son idénticos, salvo por el valor del elemento customer, que fueron procesados mediante diferentes itinerarios, basados en la resolución del componente de canalización de Selector de itinerario.  
  
4.  En la consola de administración de BizTalk Server, haga la OnRamp.Itinerary.HowTo ubicación de recepción y, a continuación, haga clic en deshabilitar.  
  
5.  Después de la **OnRamp.Itinerary.HowTo** recibir la ubicación está deshabilitado, haga clic en él y, a continuación, haga clic en **eliminar**. En el **Confirmar eliminación de ubicación de recepción** cuadro de diálogo, haga clic en **Sí**.  
  
## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  
  
-   [Cómo: Seleccionar un itinerario mediante una directiva de reglas de negocio](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)  
  
-   [Instalación y ejecución del ejemplo de resolución dinámica](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)  
  
-   [Uso de resolución y enrutamiento dinámicos](../esb-toolkit/using-dynamic-resolution-and-routing.md)  
  
-   [Patrones de enrutamiento de mensajes](../esb-toolkit/message-routing-patterns.md)