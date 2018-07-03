---
title: 'Cómo: publicar un servicio en la especificación UDDI 3.0 registro | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c3bd0ed-e5f1-43eb-98d1-e3247a565ba2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5ab38da9c78831b319d8c64e789b442fb6eef5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008021"
---
# <a name="how-to-publish-a-service-to-the-uddi-30-registry"></a>Cómo: publicar un servicio en la especificación UDDI 3.0 registro
## <a name="goal"></a>Objetivo  
 Esta sección muestra cómo usar el sitio de servicios UDDI para publicar un punto de conexión de servicio Web que se pueda resolver desde dentro de un itinerario para el enrutamiento de un mensaje de ESB. Duplicará el servicio PurchaseOrderSubmitOrderService existente publicado actualmente en el registro.  

 En este tema de procedimientos, se completará los pasos siguientes:  

-   Publicar un servicio en la Universal Description, Discovery and Integration (UDDI) 3 registro mediante la herramienta de editor UDDI.  

-   Probar la publicación de servicio mediante una lista de distribución de itinerarios que resuelve el punto de conexión de servicio con una resolución de UDDI3.  

## <a name="prerequisites"></a>Requisitos previos  
 Los procedimientos descritos en este tema de procedimientos requieren la finalización de la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) y la ejecución de la herramienta de editor UDDI (puede instalarlo en % ESB instalar Folder%\Bin\ Microsoft.Practices.ESB.UDDIPublisher.exe).  

## <a name="steps"></a>Pasos  

#### <a name="to-create-the-newposervice-in-the-uddi-registry"></a>Para crear el NewPOService en el registro UDDI  

1.  En Internet Explorer, vaya al sitio de servicios UDDI (de forma predeterminada, la dirección URL para esto es http://localhost/uddi).  

2.  En el **servicios uddi** página, haga clic en **publicar**.  

3.  En el panel publicar, haga clic en **Microsoft.Practices.ESB**y, a continuación, haga clic en **Agregar servicio**.  

4.  En la página siguiente, seleccione **especificar una clave para usar**y, a continuación, haga clic en **continuar**.  

5.  En la siguiente página, haga clic en el **esb** clave de partición. En el **clave sufijo** , escriba **newposervice**y, a continuación, haga clic en **continuar**.  

6.  En la página siguiente, junto a (**nuevo nombre de servicio**), haga clic en **editar**. Nombre del servicio **NewPOService**y, a continuación, haga clic en **actualización**.  

7.  Haga clic en **Agregar descripción**, escriba una descripción para el servicio (por ejemplo, **servicio de ejemplo**) y, a continuación, haga clic en **actualización**.  

#### <a name="to-add-a-binding-for-the-newposervice"></a>Para agregar un enlace para el NewPOService  

1.  Haga clic en el **enlaces** pestaña y, a continuación, haga clic en **Agregar enlace**.  

2.  Seleccione **especificar una clave para usar**y, a continuación, haga clic en **continuar**.  

3.  En la siguiente página, haga clic en el **esb** clave de partición. En el **clave sufijo** , escriba **newposervicebinding**y, a continuación, haga clic en **continuar**.  

4.  En **punto de acceso**, haga clic en **editar**y, a continuación, realice los pasos siguientes:  

    1.  En el **punto de acceso** , escriba **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.  

    2.  En el **Use Type** la lista desplegable, haga clic en **extremo**y, a continuación, haga clic en **actualización**.  

#### <a name="to-configure-the-binding-instance-information"></a>Para configurar la información de la instancia de enlace  

1. Haga clic en el **información de instancia** pestaña y, a continuación, haga clic en **agregar información de instancia**.  

2. En el **buscar nombres de estructuras tModel que contiene** , escriba **esb %** y, a continuación, haga clic en **búsqueda**.  

3. Busque y haga clic en el **tModel** para **transporttype**.  

   > [!NOTE]
   >  Para completar los pasos restantes de este procedimiento, es pueden que deba cambiar entre páginas 1 y 2.  

4. En el **descripciones** sección, haga clic en **Agregar descripción**.  

5. En el **descripción** , escriba **tipo de transporte para el uso de itinerarios de ESB**y, a continuación, haga clic en **actualización**.  

6. Haga clic en el **detalles de la instancia** pestaña y, a continuación, haga clic en **editar**.  

7. En el **parámetros de instancia** , escriba **WCF-BasicHttp**y, a continuación, haga clic en **actualización**.  

8. En el **descripciones** sección, haga clic en **Agregar descripción**.  

9. En el **descripción** , escriba **transporte HTTP básica de WCF**y, a continuación, haga clic en **actualización**.  

10. En el panel publicar, bajo **NewPOService**, haga clic en **http://localhost/esb.canadianservices/submitposervice.asmx**.  

11. En el **información de instancia** , haga clic **agregar información de instancia**.  

12. Mediante los pasos descritos anteriormente, agregue la siguiente información de instancia, según los valores mostrados en la tabla siguiente.  


    |                           tModel                           |       Descripción        |                          Parámetro                           |         Descripción del parámetro          |
    |------------------------------------------------------------|--------------------------|--------------------------------------------------------------|----------------------------------------|
    | Microsoft-com:esb:runtimeresolution:messageexchangepattern | Patrón de intercambio de mensajes |                           Bidireccional                            |           Operación bidireccional            |
    |      Microsoft-com:esb:runtimeresolution:cachetimeout      |      Tiempo de espera de caché       |                              -1                              |           Actualmente deshabilitado           |
    |     Microsoft-com:esb:runtimeresolution:jaxrpcresponse     |      JaxRpcResponse      |                            false                             |                                        |
    |         Microsoft-com:esb:runtimeresolution:action         |      Acción de servicio      |                         submitOrder                          | Especifica el método de servicio para invocar |
    |    Microsoft-com:esb:runtimeresolution:targetnamespace     |    Namespace de servicio     | http://globalbank.esb.dynamicresolution.com/canadianservices |            Espacio de nombres de destino            |

#### <a name="to-configure-the-binding-categorization"></a>Para configurar la categorización de enlace  

1.  En el panel publicar, bajo **NewPOService**, haga clic en **http://localhost/esb.canadianservices/submitposervice.asmx**.  

2.  En el **categorías** , haga clic **Agregar categoría personalizada**.  

3.  En el **búsqueda** , escriba **esb %** y, a continuación, haga clic en **búsqueda**.  

4.  Busque y haga clic en el **microsoft-com:esb:runtimeresolution:biztalkapplication** tModel.  

5.  En el **nombre de clave** , escriba **aplicación de BizTalk**.  

6.  En el **clave valor** , escriba **Microsoft.Practices.ESB**y, a continuación, haga clic en **Agregar categoría**.  

7.  Siguiendo los pasos descritos anteriormente, agregue las siguientes categorías personalizadas, según los valores mostrados en la tabla siguiente.  

    |tModel|Nombre de clave|Valor de clave|  
    |------------|--------------|---------------|  
    |Microsoft-com:esb:runtimeresolution:portname|Nombre de puerto|NewPOService|  
    |Microsoft-com:esb:runtimeresolution:transporttype|Tipo de transporte|WCF-BasicHttp|  

#### <a name="to-locate-the-service-in-the-uddi-registry"></a>Para localizar el servicio en el registro UDDI  

1.  En Internet Explorer, en el **servicios uddi** página, haga clic en **búsqueda**.  

2.  Haga clic en el **servicios** ficha.  

3.  En el **Service Name** , escriba **% PO**y, a continuación, haga clic en **búsqueda**.  

4.  En el **búsqueda** panel, en el **resultados** , haga clic **NewPOService**.  

    > [!NOTE]
    >  Esto confirma que el servicio se publicó correctamente en el registro.  

#### <a name="to-create-an-itinerary-model-to-test-the-uddi-service-publication"></a>Para crear un modelo de itinerarios para probar la publicación de servicios UDDI  

1.  En Visual Studio, abra C:\HowTos\Patterns\Patterns.sln.  

2.  En el Explorador de soluciones, haga clic en el **ItineraryLibrary** , seleccione **agregar**y, a continuación, haga clic en **itinerario nuevo**.  

3.  En el **Agregar nuevo elemento** cuadro de diálogo el **nombre** , escriba **NewBindingKeySearch**y, a continuación, haga clic en **agregar**.  

#### <a name="to-configure-the-properties-of-the-itinerary"></a>Para configurar las propiedades de los itinerarios  

1.  En Visual Studio, haga clic en la superficie de diseño de **NewBindingKeySearch.itinerary**. En el **NewBindingKeySearch** ventana Propiedades, configure las siguientes propiedades:  

    1.  En el **es solicitud-respuesta** la lista desplegable, haga clic en **True**.  

    2.  En el **modelo exportador** la lista desplegable, haga clic en **XML itinerario exportador**.  

    3.  En el **configuración extensor** sección, junto a la **archivo XML de itinerario** propiedad, haga clic en el botón de puntos suspensivos (...).  

    4.  En el **Seleccionar archivo XML** cuadro de diálogo, escriba **C:\HowTos\Itineraries\NewBindingKeySearch** en el **nombre de archivo** cuadro y, a continuación, haga clic en **guardar**.  

        > [!NOTE]
        >  Este paso le permite exportar el itinerario como XML en una ubicación de archivos local. Exportando un itinerario en una ubicación de archivos local, en lugar de a la base de datos de itinerario, permite probar el itinerario mediante la aplicación cliente de prueba de ESB. Complete este proceso más adelante en este tema de procedimientos.  

#### <a name="to-define-the-structure-of-the-itinerary"></a>Para definir la estructura de los itinerarios  

1.  En el cuadro de herramientas, arrastre un **vía** elemento de modelo a la superficie de diseño. En el **OnRamp1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **ReceiveNAOrder**.  

    2.  En el **extensor** la lista desplegable, haga clic en **rampa de ESB extensor**.  

    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **Microsoft.Practices.ESB**.  

    4.  En el **puerto de recepción** la lista desplegable, haga clic en **OnRamp.Itinerary.Response**.  

2.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento de modelo a la superficie de diseño. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **TransformNAOrder**.  

    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **mensajería extensor**.  

    3.  En el **contenedor** desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  

    4.  En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Transform**.  

3.  Haga clic en el **resolución** colección de la **TransformNAOrder** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **NAOrder_to_CNOrder**.  

    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **extensión resolución estático**.  

    3.  En el **transformar tipo** la lista desplegable, haga clic en **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.  

4.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **ReceiveNAOrder** elemento de modelo para el **TransformNAOrder** elemento de modelo.  

5.  En el cuadro de herramientas, arrastre un **itinerario servicio** elemento de modelo a la superficie de diseño. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeyRoute**.  

    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **mensajería extensor**.  

    3.  En el **contenedor** desplegable lista, expanda **ReceiveNAOrder**y, a continuación, haga clic en **controladores de recepción**.  

    4.  En el **Service Name** la lista desplegable, haga clic en **Microsoft.Practices.ESB.Services.Routing**.  

6.  Haga clic en el **resolución** colección de la **BindingKeyRoute** elemento del modelo y, a continuación, haga clic en **agregar nueva resolución**. En el **Resolver1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **BindingKeySearch**.  

    2.  En el **implementación de la resolución** la lista desplegable, haga clic en **Uddi3 resolución extensión**.  

    3.  En el **resolución de Moniker** la lista desplegable, haga clic en **UDDI3**.  

    4.  Haga clic en el **clave de enlace** propiedad y, a continuación, escriba **uddi:esb:newposervicebinding**. Para buscar el valor de clave, haga clic en el http://localhost/ESB.CanadianServices/SubmitPOService.asmx de servicios de UDDI y, a continuación, haga clic en más detalles.  

7.  Haga clic en el **BindingKeySearch** resolución y, a continuación, haga clic en **configuración de la resolución de prueba**.  

    > [!NOTE]
    >  Compruebe el resultado que aparece en la ventana de salida.  

8.  En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **TransformNAOrder** elemento de modelo para el **BindingKeyRoute** elemento de modelo.  

9. En el cuadro de herramientas, arrastre un **fuera de rampa** elemento a la superficie de diseño del modelo y, a continuación, colóquelo a la derecha de la **BindingKeyRoute** elemento de modelo. En el **OffRamp1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendCNOrder**.  

    2.  En el **extensor** la lista desplegable, haga clic en **fuera de rampa ESB extensor**.  

    3.  En el **aplicación de BizTalk** la lista desplegable, haga clic en **GlobalBank.ESB**.  

    4.  En el **puerto de envío** la lista desplegable, haga clic en **DynamicResolutionSolicitResp**.  

10. En el cuadro de herramientas, arrastre un **itinerario servicio** elemento a la superficie de diseño del modelo y, a continuación, colóquelo entre la **BindingKeyRoute** elemento de modelo y la **SendCNOrder** elemento de modelo. En el **ItineraryService1** ventana Propiedades, configure las siguientes propiedades:  

    1.  Haga clic en el **nombre** propiedad y, a continuación, escriba **SendPortFilter**.  

    2.  En el **extensor del servicio de itinerarios** la lista desplegable, haga clic en **fuera de rampa extensor**.  

    3.  En el **fuera de rampa** desplegable lista, expanda **SendCNOrder**y, a continuación, haga clic en **controladores de envío**.  

11. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **BindingKeyRoute** elemento de modelo para el **SendPortFilter** elemento de modelo.  

12. En el cuadro de herramientas, haga clic en **conector**. Arrastre una conexión desde el **SendPortFilter** elemento de modelo para el **SendNAOrder** elemento de modelo.  

#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a>Para exportar el modelo para su uso con el cliente de prueba de itinerario  

1.  En Visual Studio, haga clic en la superficie de diseño de la **NewBindingKeySearch** itinerario y, a continuación, haga clic en **Exportar modelo**.  

    > [!NOTE]
    >  La versión XML del itinerario se abre en Visual Studio.  

2.  Guarde todos los artefactos de proyecto.  

3.  En el Explorador de Windows, vaya a C:\HowTos\Itineraries y tenga en cuenta la creación de su itinerario XML (NewBindingKeySearch.xml).  

#### <a name="to-test-the-itinerary"></a>Para probar el itinerario  

1.  Abra la aplicación de ejemplo de cliente de prueba de itinerario mediante el acceso directo que se creó durante la [requisitos previos para las actividades de desarrollo](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB. Itinerary.Test.exe - acceso directo).  

2.  En el cliente de prueba de itinerario, en el **opciones del servicio Web** grupo, desactive la **usar el servicio de WCF** cuadro y, a continuación, seleccione el **servicio bidireccional** casilla de verificación.  

3.  Haga clic en el **carga itinerario** botón.  

4.  En el **abrir archivo itinerario** cuadro de diálogo, vaya a C:\HowTos\Itineraries. Seleccione **NewBindingKeySearch.xml**y, a continuación, haga clic en **abierto** para cargar el itinerario.  

5.  Haga clic en **Aceptar** para borrar el **itinerario se cargó correctamente** mensaje.  

6.  En el cliente de prueba de itinerario, haga clic en el botón de puntos suspensivos (...) junto a la **carga mensaje** cuadro.  

7.  En el **seleccione documento XML para cargar** cuadro de diálogo, vaya a C:\HowTos. Seleccione **NAOrderDoc.xml**y, a continuación, haga clic en **abierto** para cargar el mensaje de prueba.  

8.  Haga clic en el **Submit Request** botón. Cuando se complete la prueba, haga clic en **Aceptar** para descartar la confirmación que aparece.  

9. Compruebe que aparece el mensaje de respuesta correcta en el **resultado** cuadro de texto de la **cliente de prueba Itineray**.  

## <a name="additional-resources"></a>Recursos adicionales  
 Para obtener más información, vea los siguientes temas relacionados:  

-   [Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de claves de enlace de UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search.md)  

-   [Cómo: Resolver un punto de conexión de servicio mediante una búsqueda de categorías de UDDI](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  

-   [Actividades de desarrollo](../esb-toolkit/development-activities.md)