---
title: Ampliar las capacidades de Kit de herramientas de ESB de BizTalk con el control de SOA | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b66a121b-d86f-4f97-a05f-5141ffe719e8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f872d24c7c792d01f80463da0e3c27f31d76d8ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-biztalk-esb-toolkit-capabilities-with-soa-governance"></a>Ampliar las capacidades de Kit de herramientas de ESB de BizTalk con el control de SOA
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y es una colección de herramientas y bibliotecas que extienden [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] capacidades de admitir una arquitectura de mensajería con acoplamiento flexible y dinámica. Funciona como middleware que proporciona herramientas para mediación rápida entre servicios y sus consumidores. Habilitar la máxima flexibilidad en tiempo de ejecución, el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] simplifica la composición de acoplamiento flexible de extremos de servicio y la administración de las interacciones del servicio.  
  
 Extensiones de servidor de BizTalk de Sentinet mejoran las capacidades de [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] mediante la integración con Sentinet, una regulación de SOA y solución de software de administración de API para la plataforma de Microsoft. La primera versión de la Sentinet [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ofertas de extensiones una [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] resolución de repositorio de SOA que se integra con BizTalk Server 2013, [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]y Visual Studio 2012.  
  
 Extiende el Solucionador de SOA de Sentinet este conferencias de notas del producto acerca de cómo [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] capacidades, cómo configurar la resolución de SOA de Sentinet y, finalmente, un ejemplo que muestra cómo utilizar el Solucionador de SOA de Sentinet.  
  
## <a name="esb-toolkit-and-sentinet-soa-resolver"></a>Kit de herramientas ESB y resolución de SOA de Sentinet  
 Entre otras cosas, una resolución del Kit de herramientas de ESB debe proporcionar lo siguiente:  
  
-   Resolución de tiempo de ejecución de los extremos de servicio y sus configuraciones  
  
-   Soluciones de BizTalk ESB con la mensajería con acoplamiento flexible.  
  
 Sentinet ofrece una sólida y completa [SOA repositorio](http://www.nevatech.com/sentinet/soa-repository) que ofrece soluciones de integración SOA junto con avanzadas regulación de SOA y en tiempo de ejecución de funciones de administración. Se combina con el repositorio de SOA de Sentinet, proporciona resolución de SOA de Sentinet [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitecturas ESB con configuraciones de ESB avanzadas y fáciles de usar, el enrutamiento de mensajes dinámico y capacidades de implementación de seguridad de mensaje.  
  
 Diagrama de alto nivel siguiente muestra cómo se ajusta la resolución de SOA de Sentinet en el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] arquitectura.  
  
 ![Sentinet con el Kit de herramientas de BizTalk ESB](../technical-guides/media/sentinetwp-arch.png "SentinetWP_Arch")  
  
 En tiempo de ejecución, el **resolución de punto de conexión y enrutamiento** componente en la ilustración anterior (que forma parte de la plataforma de resolución de Kit de herramientas ESB) usa un documento de itinerario (creado en el Diseñador de itinerario de Visual Studio) para crear una instancia de Resolución específica y solicitar la resolución que se debe proporcionar el extremo de servicio y su configuración. Itinerario propio debe estar configurado con la referencia al extremo de servicio, para que la resolución puede utilizar esta referencia para buscar el punto de conexión solicitada en el registro o en el repositorio. En tiempo de diseño (cuando se crea el itinerario), no se conoce la dirección física real del extremo del servicio, como tampoco lo son las directivas de seguridad que requiere el servicio. En fases posteriores, Kit de herramientas de ESB en tiempo de ejecución utiliza resuelve el extremo de servicio para configurar fuera de rampa de puerto de envío dinámico para enviar el mensaje a la dirección de servicio física real con la configuración de seguridad de servicio necesario. Dirección del extremo de servicio, protocolos de comunicación o requisitos de seguridad cambian solo la configuración del registro/repositorio debe actualizarse. La configuración en tiempo de ejecución de los artefactos de BizTalk Server o de ESB no requiere actualizarse.  
  
## <a name="how-does-the-sentinet-resolver-add-value-to-an-esb-toolkit-application"></a>¿Cómo agregar la resolución de Sentinet valor a una aplicación del Kit de herramientas ESB?  
 Las dos ventajas principales del uso de la resolución de Sentinet junto con el repositorio SOA son:  
  
-   Asignación de identidades de cliente al punto de conexión de servicio externo resuelto: la mayoría de los casos, el extremo ESB resuelto requiere identidad del cliente específico para llamar a un servicio externo (por ejemplo, nombre de usuario/contraseña, credenciales de cuenta de Windows específicas o X.509 específico certificado). Se trata de un requisito de seguridad muy común que no se controla correctamente por otros registros y resoluciones ESB.  
  
-   Restringir el acceso a información de seguridad: para solucionar la limitación anterior, otras resoluciones podrían usar la configuración manual de estructuras tModel para incluir XML complejos con las identidades de seguridad necesarios. Sin embargo, guardar la información de seguridad como parte de registros/repositorios no es el enfoque correcto. Esto proporciona el servicio de un acceso sencillo a los consumidores a los detalles de seguridad como nombre de usuario, contraseña, etc. para tener acceso al servicio.  
  
 Sentinet resolución y del repositorio de SOA de Sentinet proporcionan capacidades de manera flexible y segura asignar ninguna identidad de cliente específico para el extremo ESB resuelto a través de los comportamientos de extremo WCF estándar o personalizados. Sentinet consigue esto mediante la configuración de resolución de Sentinet y no el repositorio de SOA de Sentinet con la información de seguridad. Todas las credenciales de cliente que se configuran con la resolución de Sentinet se almacenan en un formato cifrado.  
  
 Además, los siguientes son algunas de las otras ventajas del uso de la resolución de Sentinet y el repositorio de SOA de Sentinet.  
  
-   Proporciona un amplio repositorio SOA. El repositorio proporciona acceso a los metadatos del servicio contenido, las identidades de servicio y las directivas, compatibilidad con versiones de servicio, etcetera.  
  
-   Facilidad de registrar servicios físicos en el registro de Sentinet mediante la carga de WSDL del servicio.  
  
-   Consola de administración Sentinet completa y fácil de usar. La consola proporciona acceso de administración para todos los metadatos del servicio y artefactos, asociada a la interfaz de usuario sencilla para las operaciones del servicio de acceso y sus esquemas de datos, los extremos de servicio, las directivas de seguridad, etcetera.  
  
-   Administración y configuración de comportamientos personalizados para resolver extremos. Resolución de Sentinet proporciona comportamientos de extremo totalmente personalizable y fácil de configurar para los extremos resueltos.  
  
-   Opción para configurar a la resolución de Sentinet con una variedad de criterios de búsqueda. Itinerarios pueden definir cualquier palabra clave que se asigna a un extremo de servicio, o utilizar una ruta de acceso de servicio que apunta a un servicio en la jerarquía de servicios de repositorio.  
  
-   Resolución avanzada que prueben las funciones. Para probar las configuraciones de resolución de Sentinet directamente desde el Diseñador de itinerario de Visual Studio. Mientras que otras resoluciones solo pueden proporcionar información sobre las propiedades básicas del punto de conexión, resolución de Sentinet proporciona información adicional acerca de extremos resueltos. Además de las propiedades básicas de punto de conexión, resolución de Sentinet revela las propiedades que identifican resuelven la ubicación de servicio y de extremo en el repositorio de Sentinet. Diseñadores de itinerarios pueden probar cómo Sentinet resolución y sus criterios de búsqueda diferentes afectan a la resolución resultados antes de itinerario propio se utiliza en tiempo de ejecución.  
  
## <a name="installing-the-sentinet-biztalk-server-extensions"></a>Instalar las extensiones de servidor de Sentinet BizTalk  
 Puede descargar e instalar las extensiones de BizTalk Sentinet [aquí](http://www.nevatech.com/download). Instalar la extensión instala a la resolución de Sentinet Kit de herramientas ESB, documentación y ejemplos sobre cómo utilizar la extensión.  
  
 Un documento que detalla cómo instalar y configurar la extensión de Sentinet BizTalk Server está disponible como parte de la descarga del producto.  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Con las extensiones de servidor de Sentinet BizTalk  
 En esta sección, veremos cómo usar las extensiones de servidor de BizTalk de Sentinet y mostrar las capacidades mencionadas anteriormente.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Instrucciones en estas notas del producto, se supone que tiene las siguientes instalado y configurado:  
  
-   Visual Studio 2012.  
  
-   BizTalk Server 2013. Para obtener instrucciones, consulte [instalar BizTalk Server 2013](http://msdn.microsoft.com/library/jj248688\(v=bts.80\).aspx).  
  
-   Kit de herramientas ESB de BizTalk Server. Para obtener instrucciones, consulte [instalar y configurar el Kit de herramientas de Microsoft BizTalk ESB](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).  
  
-   Extensiones de servidor de Sentinet BizTalk. Para obtener instrucciones, consulte la documentación disponible como parte de la descarga del producto disponible [aquí](http://www.nevatech.com/download).  
  
### <a name="register-a-web-service"></a>Registrar un servicio web  
 Los servicios Web que están administrados por la infraestructura de Sentinet deben estar registrados en el repositorio. Estas notas del producto utiliza un servicio de ejemplo de búsqueda de cliente de WCF que se incluye con el paquete de instalación de Sentinet.  
  
1.  Iniciar el **buscar cliente** servicio instalado por el paquete de instalación de Sentinet de ejemplo. Iniciar el ejemplo de búsqueda de cliente como administrador, seleccione un enlace de directiva (por ejemplo, **wsHttpBinding**) y, a continuación, haga clic en **iniciar**.  
  
2.  Una vez que el servicio se está ejecutando, haga clic en el **vista Wsdl** vínculo para abrir un explorador con la dirección URL de metadatos de servicio y el WSDL del servicio. Copie la dirección URL de metadatos de la barra de direcciones del explorador.  
  
3.  Abra un explorador y escriba la dirección URL (`https://[computer-name]/sentinet`) para iniciar la consola de administración de Sentinet. Inicio de sesión y seleccione la **repositorio** elemento raíz de la **repositorio** panel de vista. Haga clic en el **repositorio** elemento raíz y haga clic en el **Agregar > servicio > SOAP** opción de menú.  
  
4.  En el **Agregar servicio** cuadro de diálogo para la **WSDL de dirección URL** opción, pegue la dirección URL de metadatos de servicio que copió anteriormente y, a continuación, haga clic en **siguiente**.  
  
     ![Agregar dirección URL del servicio](../technical-guides/media/sentinetwp-addserviceurl.png "SentinetWP_AddServiceURL")  
  
5.  Inicia el Asistente para descargar los metadatos del servicio. Una vez completada la descarga, el asistente muestra la estructura de árbol de servicio Web. Proporcione un nombre para el servicio y haga clic en **finalizar** para cargar los metadatos del servicio en el repositorio de Sentinet.  
  
     ![Estructura del servicio Web](../technical-guides/media/sentinetwp-servicestructure.png "SentinetWP_ServiceStructure")  
  
6.  El servicio se importa en el repositorio como versión 1. Seleccione la versión y, a continuación, seleccione el punto de conexión. En el **detalles del extremo** panel en la parte inferior, haga clic en el **datos adjuntos** ficha y, a continuación, haga clic en **modificar**.  
  
     ![Modificar el extremo de servicio](../technical-guides/media/sentinetwp-serviceendpoint.png "SentinetWP_ServiceEndpoint")  
  
7.  En la ficha Detalles del extremo, haga clic en el (**+**) iniciar sesión en **palabras clave**, escriba una palabra clave que se va a asociar con el punto de conexión (por ejemplo, **TestKeyword**), y a continuación, haga clic en **guardar**. La palabra clave se utiliza como etiqueta de punto de conexión (o identificador) en el repositorio SOA.  
  
     ![Especificar una palabra clave](../technical-guides/media/sentinetwp-enterkeyword.png "SentinetWP_EnterKeyword")  
  
 Repita los pasos anteriores para agregar una nueva versión de la **CustomerSearch** service, pero con un enlace diferente, por ejemplo, **basicHttpBinding**. Más adelante en estas notas del producto, le mostramos cómo puede resolver la resolución de Sentinet servicios diferentes (o versiones diferentes del mismo servicio) asociando una palabra clave de búsqueda para el extremo de servicio.  
  
### <a name="configure-sentinet-resolver"></a>Configurar la resolución de Sentinet  
 Esta sección muestra cómo configurar a la resolución de Sentinet en el proyecto de BizTalk ESB itinerario diseñador simple y concreto, cómo usar palabras clave para resolver de forma única a un extremo de servicio. Esta sección también muestra cómo probar a la resolución desde Visual Studio, sin necesidad de enviar los mensajes ESB.  
  
1.  Inicie Visual Studio y cree una **el Diseñador de itinerario de BizTalk ESB** proyecto.  
  
2.  En el Explorador de soluciones, haga doble clic en el itinerario para abrirlo en el Diseñador de itinerario.  
  
3.  En el cuadro de herramientas, arrastre y coloque el **itinerario servicio** forma en la superficie del diseñador.  
  
4.  Seleccione el **itinerario servicio** y dar forma a cambiar la **extensor del servicio de itinerario** propiedad **mensajería Extender** en la lista desplegable.  
  
     ![Establezca la propiedad Extender del mensaje](../technical-guides/media/sentinetwp-setmessageextender.png "SentinetWP_SetMessageExtender")  
  
5.  Haga clic en el **resolución** elemento en el **itinerario servicio** forma y haga clic en **agregar nueva resolución**.  
  
     ![Agregar una nueva resolución](../technical-guides/media/sentinetwp-addnewresolver.png "SentinetWP_AddNewResolver")  
  
6.  Seleccione el nuevo elemento de resolución, cambie su nombre (p. ej., **MyResolver**) y para la **implementación de la resolución** propiedad, seleccione **Sentinet resolución extensión**.  
  
     ![Establecer la implementación de la resolución](../technical-guides/media/sentinetwp-addresolverimplementation.png "SentinetWP_AddResolverImplementation")  
  
7.  Especifique el **acción** y **palabras clave** propiedades de la extensión de la resolución de Sentinet. Vamos a usar estas propiedades para resolver de forma exclusiva a los servicios que se agregó anteriormente en el repositorio de Sentinet. Hay también otras propiedades que se pueden especificar para la extensión de la resolución de Sentinet. Para obtener más información sobre las propiedades, consulte la Guía de usuario de las extensiones de BizTalk Sentinet.  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Acción|Encabezado de acción del mensaje que identifica de forma única operación de servicio que se llama. Este encabezado de acción es parte del servicio de WSDL y puede encontrarse en el WSDL del servicio o de la interfaz de usuario de consola administrativa de Sentinet (en Propiedades de mensaje de solicitud de la operación.|  
    |Palabras clave|Proporcionar la palabra clave (por ejemplo, **TestKeyword**) que asignó al servicio en la consola de administración de Sentinet.|  
  
     Captura de pantalla siguiente muestra la propiedad de acción y las palabras clave especificada para el **MyResolver** configuración.  
  
     ![Configuración de resoluciones de Sentinet](../technical-guides/media/sentinetwp-resolverconfig.png "SentinetWP_ResolverConfig")  
  
8.  Guardar cambios en la configuración.  
  
#### <a name="advanced-resolver-configuration"></a>Configuración de la resolución avanzadas  
 Modifica la aplicación de la configuración de extensiones de BizTalk de Sentinet **Sentinet.BizTalk.config** archivo se encuentra en la raíz de la carpeta de instalación de paquete (la ubicación predeterminada es `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Sentinet.BizTalk.config`). El archivo se puede modificar desde fuera de **configuración de las extensiones de BizTalk de Sentinet** aplicación para proporcionar opciones de configuración avanzadas. Por ejemplo, en muchos escenarios ESB resulta muy prácticos resueltos los puntos de conexión deben proporcionarse no solo con enlaces y direcciones de extremo de servicio, sino también con las identidades de cliente específico (nombre de usuario/contraseña, las credenciales de cuenta de Windows específicas o un cliente X.509 certificado). Sin la identidad del cliente correcto, puertos de envío fuera de rampa de ESB producirá un error al llamar a servicios externos. Resolución de Sentinet permite que un desarrollador de itinerario asignar el comportamiento de punto de conexión específico que proporciona identidad del extremo de cliente apropiado. Varios comportamientos de punto de conexión pueden ser configurados previamente como los comportamientos de extremo WCF estándares en el **Sentinet.BizTalk.config** archivo y el comportamiento de punto de conexión concreto, a continuación, pueden hacer referencia en el itinerario de la resolución de Sentinet configuración, especificando el nombre del comportamiento de la **resuelve el comportamiento de extremo** propiedad.  
  
### <a name="test-the-resolver-configuration"></a>Probar la configuración de resolución  
 Después de haber configurado a la resolución de Sentinet especificando los valores de propiedad correspondiente, puede probar a la resolución de Visual Studio.  
  
1.  En la superficie de diseño, haga clic en la resolución de Sentinet ha agregado a la **itinerario servicio** forma y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
     El panel de resultados muestra los resultados de pruebas, es similar a un extracto de la que se muestra a continuación:  
  
    ```  
    ***** Resolved Service Endpoint *****  
  
    Service Path and Name          : /CustomerSearch  
    Service Id                     : 2b6d686a-cae1-4b7b-93da-99affef98478  
    Service Version                : 1  
    Endpoint Name                  : WSHttpBinding_ICustomerSearch  
    Endpoint Address               : http://btscloudcar/CustomerSearch/1  
    ```  
  
     Tenga en cuenta que la resolución de devolver el punto de conexión para el **CustomerSearch** servicio **versión 1** a la que los criterios de búsqueda (**TestKeyword**) está conectado.  
  
2.  Quitar el **TestKeyword** asociados con el **versión 1** de la **CustomerSearch** de servicio y asociarlo con el punto de conexión de la segunda versión del servicio.  
  
    1.  Abra la consola de administración de Sentinet, haga clic en **versión 1** en el **CustomerSearch** de servicio, haga clic en el punto de conexión de wsHttpBinding y, a continuación, haga clic en el **datos adjuntos** pestaña y, a continuación, haga clic en **modificar**.  
  
         ![Quite la palabra clave del servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  Haga clic en el botón con la palabra clave que especificó antes de eliminar la palabra clave, haga clic en **Sí** en el cuadro de mensaje y, a continuación, haga clic en **guardar**.  
  
         ![Quite la palabra clave de servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  A continuación, asignar la misma palabra clave (**TestKeyword**) a la **basicHttpBinding** punto de conexión en el **versión 2** del mismo servicio.  
  
3.  Vuelva a Visual Studio y volver a la configuración de la resolución de prueba. Haga clic en la resolución de Sentinet ha agregado a la **itinerario servicio** forma y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
     El panel de resultados muestra los resultados de pruebas, es similar a un extracto de la que se muestra a continuación:  
  
    ```  
    ***** Resolved Service Endpoint *****  
  
    Service Path and Name          : /CustomerSearch  
    Service Id                     : 5b9e5878-7016-44ab-9f0e-5282a8c3e508  
    Service Version                : 2  
    Endpoint Name                  : BasicHttpBinding_ICustomerSearch  
    Endpoint Address               : http://btscloudcar/CustomerSearch/2  
    ```  
  
4.  Observe cómo la resolución ahora devuelve los detalles de la **versión 2** del servicio, aunque no ha cambiado algo en la aplicación de itinerario ESB.  
  
 Asignar la palabra clave (**TestKeyword**) a la versión 1 del servicio (con el **WSHttpBinding** extremo).  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Con las extensiones de servidor de Sentinet BizTalk  
 En esta sección, veremos cómo se puede utilizar la BizTalk extensión Sentinet, junto con la resolución de ESB, para identificar de forma exclusiva un servicio y enrutar el mensaje a ese servicio, con una o ningún cambio en el servicio o el cliente que envía el mensaje. Probamos dos escenarios:  
  
-   Enviar un mensaje de ejemplo a un servicio registrado en el repositorio de Sentinet (con la palabra clave adjuntada). A continuación, cambie el enlace de directiva para el servicio utilizando la consola de administración de Sentinet y envíe otro mensaje de ejemplo. Este escenario muestra cómo cambiar la directiva de seguridad del servicio no afecta a la aplicación cliente ni el itinerario ESB.  
  
-   Enviar un mensaje de ejemplo a un punto de conexión de servicio registrado en el repositorio de Sentinet (con la palabra clave adjuntada). A continuación, adjuntar la misma palabra clave a otra versión del mismo servicio y envíe el mensaje de nuevo. Este escenario muestra cómo asociar una palabra clave a una versión de servicio diferente automáticamente enruta los mensajes a una nueva versión de servicio.  
  
 Para probar estos escenarios, vamos a usar en los ejemplos siguientes:  
  
-   **Servicio de búsqueda al cliente** proporcionado con el instalador de Sentinet. Este servicio se puede iniciar desde el menú Inicio.  
  
-   **Nevatech.Vsb.BizTalk.Samples** solución proporcionada con el instalador de Sentinet. Este ejemplo está disponible en `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples`.  
  
-   ESB. Ejemplo Itinerary.Test incluidos con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Esta opción está disponible en `<install drive>:\Program Files (x86)\Microsoft BizTalk ESB Toolkit\ESBSource.zip\Source\Samples\Itinerary\Source\ESB.Itinerary.Test` y se usa para mensajes de ejemplo para el servicio de búsqueda de cliente de prueba.  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-the-service-policy-binding"></a>Para probar a la resolución de Sentinet cambiando el enlace de la directiva de servicio  
  
1.  Asegúrese de que el **CustomerSearch** se ejecuta el servicio que ha implementado con el wsHttpBinding.  
  
2.  Desde el **Nevatech.Vsb.BizTalk.Samples** ejemplo, abra **CustomerSearch.Search.itinerary**, seleccione **resolver el extremo de servicio** en el **mensaje Extender** dentro de la **enrutar el mensaje** forma y para la **palabras clave** propiedad, especifique una palabra clave, como **TestKeyword**.  
  
     ![Asignar palabra clave](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  Guarde los cambios en el itinerario y exportar el modelo. Haga doble clic en cualquier lugar en la superficie del Diseñador de itinerarios y haga clic en **Exportar modelo**.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **Microsoft.Practices.ESB** aplicación, haga clic en Importar y, a continuación, haga clic en enlaces. Navegue hasta la ubicación del ejemplo de resolución de ESB en `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`y abra el **BizTalk.Bindings.xml** archivo. Esto crea la **Sentinet petición-respuesta** y **Sentinet unidireccional** enviar puertos necesarios para los itinerarios de ejemplo.  
  
     Además, asegúrese de que todos los puertos de envío y recepción de ubicaciones de la **Microsoft.Practices.ESB** aplicación de BizTalk se da de alta y se inicia.  
  
5.  Abra el **ESB. Itinerary.Test** aplicación, compilarlo y ejecutarlo. En el cliente de prueba de itinerario que se inicia, realice los pasos siguientes:  
  
    1.  En el cliente de prueba de itinerario en **opciones del servicio Web**, desactive **usar el servicio de WCF**y seleccione **dos servicios de manera**.  
  
    2.  Desde el **Service Type** lista desplegable, seleccione **mensajería**.  
  
    3.  Haga clic en **carga itinerario** y navegue hasta la **CustomerSearch.Search.Itinerary.xml** archivo se encuentra en el proyecto de ejemplo **ExportedItineraries** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  Haga clic en el botón de puntos suspensivos (**...** ) en **mensaje de carga** de grupo y vaya a **CustomerSearch.Search.Request.xml** ubicado en el proyecto **SampleMessages** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  Haga clic en **Submit Request** y compruebe que recibe la respuesta en.  
  
6.  En el **CustomerSearch** cuadro de diálogo, tenga en cuenta que el contador se incrementa en uno.  
  
7.  En la consola de administración de Sentinet, actualizar los detalles del extremo que se use basicHttpBinding en lugar de wsHttpBinding.  
  
    1.  Seleccione el extremo de servicio, haga clic en el **detalles** ficha y, a continuación, haga clic en **modificar**.  
  
    2.  En el **detalles** , haga clic en el botón de puntos suspensivos (**...** ) en el **directiva** sección, para iniciar la **modificar directiva** asistente.  
  
         ![Iniciar el Asistente para modificar la directiva](../technical-guides/media/sentinetwp-modifypolicy-1.png "SentinetWP_ModifyPolicy_1")  
  
    3.  En la primera página, conservar el tipo de directiva como **privada** y, a continuación, haga clic en **siguiente**.  
  
    4.  En la segunda página, cambie la **wsHttpBinding** elemento XML en **basicHttpBinding** (distingue mayúsculas de minúsculas) y, a continuación, haga clic en **finalizar**.  
  
         ![Actualizar el enlace de directiva](../technical-guides/media/sentinetwp-modifypolicy-2.png "SentinetWP_ModifyPolicy_2")  
  
    5.  Haga clic en **guardar** para guardar los cambios en los detalles del extremo.  
  
8.  Detener el **CustomerSearch** de servicio, cambie el enlace de **wsHttpBinding** a **basicHttpBinding**, y, a continuación, vuelva a iniciar el servicio.  
  
     ![Reiniciar el servicio con otro enlace](../technical-guides/media/sentinetwp-restartcustservice.png "SentinetWP_RestartCustService")  
  
9. Desde el **probar el cliente de itinerario**, enviar un mensaje de prueba de nuevo al servicio de búsqueda del cliente. Tenga en cuenta que el contador en el cuadro de diálogo de servicio de búsqueda de cliente nuevo se incrementa en 1.  
  
     Una vez que el mensaje se recibe correctamente desde la consola de administración de Sentinet, cambiar la directiva de detalles de nuevo a **wsHttpBinding**. Del mismo modo, detener la **buscar cliente** de servicio, volver a cambiar la directiva a wsHttpBinding e iniciar el servicio.  
  
 Esto muestra cómo se pueden actualizar los detalles de servicio en el repositorio de Sentinet sobre la marcha a un punto de conexión de servicio actualizada de destino sin cambiar el itinerario o el cliente.  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-keyword-assignments"></a>Para probar a la resolución de Sentinet cambiando las asignaciones de palabra clave  
  
1.  Asegúrese de que las dos instancias de **CustomerSearch** se ejecuta el servicio que ha implementado con el wsHttpBinding y basicHttpBinding.  
  
2.  Desde el **Nevatech.Vsb.BizTalk.Samples** ejemplo, abra **CustomerSearch.Search.itinerary**, seleccione **resolver el extremo de servicio** en el **mensaje Extender** dentro de la **enrutar el mensaje** forma y para la **palabras clave** propiedad, especifique una palabra clave, como **TestKeyword**.  
  
     ![Asignar palabra clave](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  Guarde los cambios en el itinerario y exportar el modelo. Haga doble clic en cualquier lugar en la superficie del Diseñador de itinerarios y haga clic en **Exportar modelo**.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **Microsoft.Practices.ESB** aplicación, haga clic en Importar y, a continuación, haga clic en enlaces. Navegue hasta la ubicación del ejemplo de resolución de ESB en `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`y abra el **BizTalk.Bindings.xml** archivo. Esto crea la **Sentinet petición-respuesta** y **Sentinet unidireccional** enviar puertos necesarios para los itinerarios de ejemplo.  
  
     Además, asegúrese de que todos los puertos de envío y recepción de ubicaciones de la **Microsoft.Practices.ESB** aplicación de BizTalk se da de alta y se inicia.  
  
5.  Abra el **ESB. Itinerary.Test** aplicación, compilarlo y ejecutarlo. En el cliente de prueba de itinerario que se inicia, realice los pasos siguientes:  
  
    1.  En el cliente de prueba de itinerario en **opciones del servicio Web**, desactive **usar el servicio de WCF**y seleccione **dos servicios de manera**.  
  
    2.  Desde el **Service Type** lista desplegable, seleccione **mensajería**.  
  
    3.  Haga clic en **carga itinerario** y navegue hasta la **CustomerSearch.Search.Itinerary.xml** archivo se encuentra en el proyecto de ejemplo **ExportedItineraries** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  Haga clic en el botón de puntos suspensivos (**...** ) en **mensaje de carga** de grupo y vaya a **CustomerSearch.Search.Request.xml** ubicado en el proyecto **SampleMessages** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  Haga clic en **Submit Request** y compruebe que recibe la respuesta en.  
  
6.  En el **CustomerSearch** cuadro de diálogo, tenga en cuenta que el contador se incrementa en uno.  
  
7.  En la consola de administración de Sentinet, quite el **TestKeyword** asociados con el **versión 1** de la **CustomerSearch** de servicio y asociarlo con **Versión 2** del servicio.  
  
    1.  Abra la consola de administración de Sentinet, haga clic en **versión 1** en el **CustomerSearch** de servicio, haga clic en el punto de conexión de wsHttpBinding y, a continuación, haga clic en el **datos adjuntos** pestaña y, a continuación, haga clic en **modificar**.  
  
         ![Quite la palabra clave del servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  Haga clic en el botón con la palabra clave que especificó antes de eliminar la palabra clave, haga clic en **Sí** en el cuadro de mensaje y, a continuación, haga clic en **guardar**.  
  
         ![Quite la palabra clave de servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  A continuación, asignar la misma palabra clave (**TestKeyword**) a la **basicHttpBinding** punto de conexión en el **versión 2** del mismo servicio.  
  
8.  Enviar un mensaje de prueba de nuevo desde el **probar el cliente de itinerario** y tenga en cuenta que esta vez, el contador se incrementa en el cuadro de diálogo que representa la versión 2 del servicio, implementada con el basicHttpBinding.