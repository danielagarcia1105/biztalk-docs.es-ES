---
title: Extender las funcionalidades del Kit de herramientas de BizTalk ESB con gobierno de SOA | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b66a121b-d86f-4f97-a05f-5141ffe719e8
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a770599e082d2f25062588247acfeb6a0449b974
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977509"
---
# <a name="extending-biztalk-esb-toolkit-capabilities-with-soa-governance"></a>Extender las funcionalidades del Kit de herramientas de BizTalk ESB con gobierno de SOA
El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y es una colección de herramientas y bibliotecas que extienden [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] capacidades de admitir una arquitectura de mensajería con acoplamiento flexible y dinámica. Funciona como el software intermedio que proporciona herramientas para mediación rápido entre servicios y sus consumidores. Habilitar la máxima flexibilidad en tiempo de ejecución, el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] simplifica la composición de acoplamiento flexible de los extremos de servicio y la administración de las interacciones del servicio.  
  
 Extensiones de servidor BizTalk Sentinet mejoran las capacidades de [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] integrando con Sentinet un gobierno de SOA y solución de software de administración de API para la plataforma de Microsoft. La primera versión de la Sentinet [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ofertas de extensiones una [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] resolución de repositorio de SOA que se integra con BizTalk Server 2013, [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]y Visual Studio 2012.  
  
 Esta notas del producto se habla de cómo Sentinet SOA resolución extiende [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] capacidades, cómo configurar la resolución de SOA Sentinet y, finalmente, un ejemplo que demuestra cómo utilizar el Solucionador de SOA Sentinet.  
  
## <a name="esb-toolkit-and-sentinet-soa-resolver"></a>Kit de herramientas ESB y resolución de SOA de Sentinet  
 Entre otras cosas, una resolución del Kit de herramientas ESB debe proporcionar lo siguiente:  
  
- Resolución de tiempo de ejecución de los extremos de servicio y sus configuraciones  
  
- Soluciones de BizTalk ESB con mensajería con acoplamiento flexible.  
  
  Sentinet ofrece una sólida y completa [SOA repositorio](http://www.nevatech.com/sentinet/soa-repository) que proporciona soluciones de integración SOA junto con el tiempo de ejecución y gobierno de SOA avanzados capacidades de administración. En combinación con Sentinet SOA repositorio, resolución de SOA de Sentinet proporciona [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] arquitecturas ESB con configuraciones de ESB avanzadas y fácil de usar, el enrutamiento de mensajes dinámico y capacidades de implementación de seguridad de mensaje.  
  
  Un diagrama de alto nivel a continuación muestra cómo se ajusta la resolución de SOA Sentinet el [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] arquitectura.  
  
  ![Sentinet con el Kit de herramientas ESB de BizTalk](../technical-guides/media/sentinetwp-arch.png "SentinetWP_Arch")  
  
  En tiempo de ejecución, el **resolución de punto de conexión y enrutamiento** componente en la ilustración anterior (que es parte del marco de resolución del Kit de herramientas de ESB) usa un documento de itinerario (creado en el Diseñador de itinerario de Visual Studio) para crear instancias Resolución específica y solicitar la resolución para proporcionar el punto de conexión de servicio y su configuración. Itinerario propio debe configurarse con la referencia al extremo de servicio, para que el solucionador puede usar esta referencia para buscar un punto de conexión solicitada en el repositorio o de registro. En tiempo de diseño (cuando se crea el itinerario), no se conoce la dirección física real del extremo del servicio, y tampoco lo son las directivas de seguridad que requiere el servicio. En las fases posteriores, Kit de herramientas de ESB en tiempo de ejecución usa resuelve el extremo de servicio para configurar fuera de rampa de puerto de envío dinámico para enviar el mensaje a la dirección de servicio física real con la configuración de seguridad de servicio requerido. Si la dirección del punto de conexión de servicio, protocolos de comunicación o los requisitos de seguridad cambian solo la configuración del registro o el repositorio debe actualizarse. La configuración en tiempo de ejecución de los artefactos de BizTalk Server o de ESB no requiere actualizarse.  
  
## <a name="how-does-the-sentinet-resolver-add-value-to-an-esb-toolkit-application"></a>¿Cómo agregar la resolución de Sentinet valor a una aplicación de Kit de herramientas ESB?  
 Las dos principales ventajas de utilizar a la resolución de Sentinet junto con el repositorio SOA son:  
  
- Asignación de identidades de cliente al punto de conexión de servicio externo resuelta: la mayoría de los casos, el punto de conexión ESB resuelto requiere identidad específica del cliente para llamar a un servicio externo (por ejemplo, el nombre de usuario/contraseña, credenciales de cuenta de Windows específicas o X.509 específico certificado). Se trata de un requisito muy común de seguridad que no se controla correctamente por otros registros y las resoluciones ESB.  
  
- Restringir el acceso a información de seguridad: para evitar la limitación anterior, otras resoluciones podrían usar la configuración manual de estructuras tModel para incluir XML complejos con las identidades de seguridad necesarios. Sin embargo, no es el enfoque correcto al guardar la información de seguridad como parte de los registros y repositorios. Esto proporciona servicio un acceso sencillo a los consumidores a los detalles de seguridad, como el nombre de usuario, contraseña, etc. para acceder al servicio.  
  
  Sentinet resolución y Sentinet SOA repositorio proporcionan funcionalidades para manera flexible y segura asignar cualquier identidad específica del cliente al punto de conexión ESB resolver a través de los comportamientos de extremo WCF estándar o personalizados. Sentinet consigue esto mediante la configuración de resolución de Sentinet y no el repositorio de SOA Sentinet con la información de seguridad. Todas las credenciales de cliente que están configuradas con la resolución de Sentinet se almacenan en un formato cifrado.  
  
  Además, las siguientes son algunas de las ventajas del uso de la resolución de Sentinet y el repositorio de Sentinet SOA.  
  
- Proporciona un amplio repositorio SOA. El repositorio proporciona acceso a los metadatos del servicio contenido, las identidades de servicio y las directivas, compatibilidad con versiones del servicio, etcetera.  
  
- Facilidad de registrar servicios físicos en el registro de Sentinet mediante la carga de WSDL del servicio.  
  
- Consola de administración Sentinet completa y fácil de usar. La consola proporciona acceso administrativo a todos los metadatos del servicio y asociados, los artefactos de interfaz de usuario sencilla para las operaciones de servicio de acceso y sus esquemas de datos, los puntos de conexión de servicio, las directivas de seguridad, etcetera.  
  
- Administración y configuración de comportamientos personalizados para los puntos de conexión resueltos. Resolución de Sentinet proporciona los comportamientos de extremo totalmente personalizable y fácil de configurar para los puntos de conexión resueltos.  
  
- Opción para configurar a la resolución de Sentinet con una variedad de criterios de búsqueda. Itinerarios pueden definir cualquier palabra clave que se asigna a un extremo de servicio, o usar una ruta de acceso de servicio que apunta a un servicio en la jerarquía de servicios de repositorio.  
  
- Resolución avanzada capacidades de pruebas. Pueden probar las configuraciones de resolución de Sentinet directamente desde el Diseñador de itinerario de Visual Studio. Mientras que otras resoluciones solo pueden proporcionar información sobre las propiedades básicas del punto de conexión, resolución de Sentinet proporciona información extendida sobre los puntos de conexión resueltos. Además de las propiedades básicas de punto de conexión, resolución de Sentinet revela las propiedades que identifican resuelven la ubicación de servicio y el punto de conexión en el repositorio de Sentinet. Los diseñadores de itinerarios pueden probar cómo Sentinet resolución y sus criterios de búsqueda diferentes afectan a los resultados de resolución antes de itinerario propio se utiliza en tiempo de ejecución.  
  
## <a name="installing-the-sentinet-biztalk-server-extensions"></a>Instalar las extensiones de servidor Sentinet BizTalk  
 Puede descargar e instalar las extensiones de BizTalk Sentinet desde [aquí](http://www.nevatech.com/download). Instalar la extensión instala a la resolución de Sentinet para el Kit de herramientas ESB, documentación y ejemplos sobre cómo usar la extensión.  
  
 Un documento que detalla cómo instalar y configurar la extensión de Sentinet BizTalk Server está disponible como parte de la descarga del producto.  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Uso de las extensiones de servidor Sentinet BizTalk  
 En esta sección, veremos cómo usar las extensiones de servidor de BizTalk Sentinet y mostrar las capacidades mencionadas anteriormente.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Instrucciones en estas notas del producto asumen que dispone de lo siguiente instalado y configurado:  
  
-   Visual Studio 2012.  
  
-   BizTalk Server 2013. Para obtener instrucciones, consulte [instalar BizTalk Server 2013](http://msdn.microsoft.com/library/jj248688\(v=bts.80\).aspx).  
  
-   Kit de herramientas ESB de BizTalk Server. Para obtener instrucciones, consulte [instalar y configurar Microsoft BizTalk ESB Toolkit](http://msdn.microsoft.com/library/jj684558\(v=bts.80\).aspx).  
  
-   Extensiones de servidor Sentinet BizTalk. Para obtener instrucciones, consulte la documentación disponible como parte de la descarga de producto [aquí](http://www.nevatech.com/download).  
  
### <a name="register-a-web-service"></a>Registrar un servicio web  
 Servicios Web que están administrados por la infraestructura de Sentinet deben estar registrados en el repositorio. Estas notas del producto usa un servicio de ejemplo de búsqueda de clientes de WCF que se distribuye con el paquete de instalación Sentinet.  
  
1. Iniciar el **búsqueda de clientes** servicio instalado por el paquete de instalación de Sentinet de ejemplo. Iniciar el ejemplo de búsqueda de clientes como administrador, seleccione un enlace de la directiva (por ejemplo, **wsHttpBinding**) y, a continuación, haga clic en **iniciar**.  
  
2. Una vez que se está ejecutando el servicio, haga clic en el **vista Wsdl** vínculo para abrir un explorador con la dirección URL de metadatos de servicio y el servicio WSDL. Copie la URL de metadatos de la barra de direcciones del explorador.  
  
3. Abra un explorador y escriba la dirección URL (`https://[computer-name]/sentinet`) para iniciar la consola administrativa de Sentinet. Inicio de sesión y seleccione el **repositorio** elemento raíz en el **repositorio** vista en el panel. Haga clic en el **repositorio** elemento raíz y haga clic en el **Agregar > servicio > SOAP** opción de menú.  
  
4. En el **Agregar servicio** cuadro de diálogo para la **WSDL desde dirección URL** opción, pegue la dirección URL de metadatos de servicio que copió anteriormente y, a continuación, haga clic en **siguiente**.  
  
    ![Agregar dirección URL del servicio](../technical-guides/media/sentinetwp-addserviceurl.png "SentinetWP_AddServiceURL")  
  
5. Inicia el Asistente para descargar los metadatos del servicio. Una vez completada la descarga, el asistente muestra la estructura de árbol del servicio Web. Proporcione un nombre para el servicio y haga clic en **finalizar** para cargar los metadatos del servicio en el repositorio de Sentinet.  
  
    ![Estructura del servicio Web](../technical-guides/media/sentinetwp-servicestructure.png "SentinetWP_ServiceStructure")  
  
6. El servicio se importa en el repositorio como la versión 1. Seleccione la versión y, a continuación, seleccione el punto de conexión. En el **los detalles del extremo** panel en la parte inferior, haga clic en el **datos adjuntos** pestaña y, a continuación, haga clic en **modificar**.  
  
    ![Modificar el extremo de servicio](../technical-guides/media/sentinetwp-serviceendpoint.png "SentinetWP_ServiceEndpoint")  
  
7. En la ficha Detalles del punto de conexión, haga clic en el (**+**) inicie sesión en **palabras clave**, escriba una palabra clave para asociar el punto de conexión (por ejemplo, **TestKeyword**), y a continuación, haga clic en **guardar**. La palabra clave se usa como una etiqueta de punto de conexión (o identificador) en el repositorio SOA.  
  
    ![Especifique una palabra clave](../technical-guides/media/sentinetwp-enterkeyword.png "SentinetWP_EnterKeyword")  
  
   Repita los pasos anteriores para agregar una nueva versión de la **CustomerSearch** service, pero con un enlace diferente, por ejemplo, **basicHttpBinding**. Más adelante en este artículo, le mostramos cómo puede resolver la resolución de Sentinet servicios diferentes (o versiones diferentes del mismo servicio) asociando una palabra clave de búsqueda para el extremo de servicio.  
  
### <a name="configure-sentinet-resolver"></a>Configurar la resolución de Sentinet  
 En esta sección se muestra cómo configurar a la resolución de Sentinet en el proyecto simple de diseñador de itinerarios de ESB de BizTalk y, concretamente, cómo usar palabras clave para resolver de forma única a un extremo de servicio. Esta sección también muestra cómo probar a la resolución del propio Visual Studio, sin necesidad de enviar los mensajes ESB.  
  
1.  Inicie Visual Studio y cree un **el Diseñador de itinerarios de ESB de BizTalk** proyecto.  
  
2.  En el Explorador de soluciones, haga doble clic en el itinerario para abrirlo en el Diseñador de itinerario.  
  
3.  En el cuadro de herramientas, arrastre y coloque el **itinerario servicio** forma en la superficie del diseñador.  
  
4.  Seleccione el **itinerario servicio** y dar forma a cambiar el **extensor del servicio de itinerarios** propiedad **mensajería extensor** en la lista desplegable.  
  
     ![Establecer la propiedad de extensor mensaje](../technical-guides/media/sentinetwp-setmessageextender.png "SentinetWP_SetMessageExtender")  
  
5.  Haga clic en el **resolución** elemento en el **itinerario servicio** dar forma y haga clic en **agregar nueva resolución**.  
  
     ![Agregar una nueva resolución](../technical-guides/media/sentinetwp-addnewresolver.png "SentinetWP_AddNewResolver")  
  
6.  Seleccione el nuevo elemento de la resolución, cámbiele el nombre (p. ej., **MyResolver**) y para el **implementación de la resolución** propiedad, seleccione **Sentinet resolución extensión**.  
  
     ![Establecer la implementación de la resolución](../technical-guides/media/sentinetwp-addresolverimplementation.png "SentinetWP_AddResolverImplementation")  
  
7.  Especifique el **acción** y **palabras clave** las propiedades de la extensión de la resolución de Sentinet. Vamos a usar estas propiedades para resolver de forma exclusiva a los servicios que se agregó anteriormente en el repositorio de Sentinet. Hay también otras propiedades que se pueden especificar para la extensión de la resolución de Sentinet. Para más información sobre estas propiedades, consulte la Guía de usuario de las extensiones de Sentinet BizTalk.  
  
    |Property|Descripción|  
    |--------------|-----------------|  
    |Acción|Encabezado de acción del mensaje que identifica la operación de servicio que se llama. Este encabezado de acción es parte del servicio de WSDL y puede encontrarse en el WSDL del servicio, o bien desde la interfaz de usuario de consola administrativa de Sentinet (en las propiedades de mensaje de solicitud de la operación.|  
    |Palabras clave|Proporcionar la palabra clave (por ejemplo, **TestKeyword**) que asignó al servicio en la consola administrativa de Sentinet.|  
  
     Captura de pantalla siguiente muestra la propiedad de las palabras clave y la acción especificada para el **MyResolver** configuración.  
  
     ![Configuración de resoluciones de Sentinet](../technical-guides/media/sentinetwp-resolverconfig.png "SentinetWP_ResolverConfig")  
  
8.  Guarde los cambios en la configuración.  
  
#### <a name="advanced-resolver-configuration"></a>Configuración de la resolución avanzada  
 Modifica la aplicación de configuración de las extensiones de BizTalk Sentinet **Sentinet.BizTalk.config** archivo se encuentra en la raíz de la carpeta de instalación del paquete (la ubicación predeterminada es `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Sentinet.BizTalk.config`). Se puede modificar el archivo fuera de **configuración de las extensiones de BizTalk Sentinet** aplicación para proporcionar opciones de configuración avanzada. Por ejemplo, en muchos escenarios prácticos de ESB resolver los puntos de conexión tienen que proporcionarse no solo con direcciones de punto de conexión de servicio y los enlaces, sino también con las identidades de cliente específico (nombre de usuario/contraseña, credenciales de cuenta de Windows específicas o un cliente X.509 certificado). Sin la identidad del cliente adecuado, puertos de envío fuera de rampa de ESB producirá un error al llamar a servicios externos. Resolución de Sentinet permite developer itinerario asignar el comportamiento de punto de conexión específico que proporciona identidad de extremo de cliente adecuado. Varios comportamientos de extremo se pueden configurados previamente como comportamientos de extremo WCF estándares en el **Sentinet.BizTalk.config** archivo y el comportamiento de punto de conexión concreto, a continuación, pueden hacer referencia en el itinerario de la resolución de Sentinet configuración, especificando el nombre del comportamiento de la **resuelve el comportamiento de extremo** propiedad.  
  
### <a name="test-the-resolver-configuration"></a>Probar la configuración de resolución  
 Después de haber configurado a la resolución de Sentinet especificando los valores de propiedad pertinentes, puede probar a la resolución del propio Visual Studio.  
  
1. La superficie de diseño, haga clic en la resolución de Sentinet ha agregado a la **itinerario servicio** dar forma y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
    El panel de resultados muestra los resultados de pruebas, es similar a un extracto de los cuales se muestra a continuación:  
  
   ```  
   ***** Resolved Service Endpoint *****  
  
   Service Path and Name          : /CustomerSearch  
   Service Id                     : 2b6d686a-cae1-4b7b-93da-99affef98478  
   Service Version                : 1  
   Endpoint Name                  : WSHttpBinding_ICustomerSearch  
   Endpoint Address               : http://btscloudcar/CustomerSearch/1  
   ```  
  
    Tenga en cuenta que la resolución devuelve el punto de conexión para el **CustomerSearch** servicio **versión 1** a la que los criterios de búsqueda (**TestKeyword**) está asociado.  
  
2. Quitar el **TestKeyword** asociado con el **versión 1** de la **CustomerSearch** de servicio y su asociación con el punto de conexión de la segunda versión del servicio.  
  
   1.  Abra la consola administrativa de Sentinet, haga clic en **versión 1** bajo el **CustomerSearch** de servicio, haga clic en el punto de conexión de wsHttpBinding y, a continuación, haga clic en el **datos adjuntos** pestaña y, a continuación, haga clic en **modificar**.  
  
        ![Quite la palabra clave del servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
   2.  Haga clic en el botón de la palabra clave que escribió antes de eliminar la palabra clave, haga clic en **Sí** en el cuadro de mensaje y, a continuación, haga clic en **guardar**.  
  
        ![Quite la palabra clave de servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
   3.  Ahora, asigne la misma palabra clave (**TestKeyword**) a la **basicHttpBinding** extremo bajo el **versión 2** del mismo servicio.  
  
3. Vuelva a Visual Studio y vuelva a la configuración de la resolución de prueba. Haga clic en la resolución de Sentinet ha agregado a la **itinerario servicio** dar forma y, a continuación, haga clic en **configuración de la resolución de prueba**.  
  
    El panel de resultados muestra los resultados de pruebas, es similar a un extracto de los cuales se muestra a continuación:  
  
   ```  
   ***** Resolved Service Endpoint *****  
  
   Service Path and Name          : /CustomerSearch  
   Service Id                     : 5b9e5878-7016-44ab-9f0e-5282a8c3e508  
   Service Version                : 2  
   Endpoint Name                  : BasicHttpBinding_ICustomerSearch  
   Endpoint Address               : http://btscloudcar/CustomerSearch/2  
   ```  
  
4. Observe cómo la resolución ahora devuelve los detalles de la **versión 2** del servicio, aunque no ha cambiado nada en la aplicación de itinerarios de ESB.  
  
   Asignar la palabra clave (**TestKeyword**) a la versión 1 del servicio (con el **WSHttpBinding** punto de conexión).  
  
## <a name="using-the-sentinet-biztalk-server-extensions"></a>Uso de las extensiones de servidor Sentinet BizTalk  
 En esta sección, veremos cómo puede utilizar la BizTalk extensión Sentinet, junto con la resolución de ESB, para identificar de forma única un servicio y enrutar el mensaje a ese servicio, con el mínimo o ningún cambio en el servicio o el cliente que envía el mensaje. Probaremos dos escenarios:  
  
- Enviar un mensaje de ejemplo a un servicio registrado en el repositorio de Sentinet (con la palabra clave adjuntada). A continuación, cambie el enlace de la directiva para el servicio utilizando la consola administrativa Sentinet y enviar otro mensaje de ejemplo. Este escenario muestra cómo cambiar la directiva de seguridad del servicio no afecta a la aplicación cliente ni los itinerarios ESB.  
  
- Enviar un mensaje de ejemplo a un punto de conexión de servicio registrado en el repositorio de Sentinet (con la palabra clave adjuntada). A continuación, adjuntar la misma palabra clave a otra versión del mismo servicio y vuelva a enviar el mensaje. Este escenario muestra cómo asociar una palabra clave a una versión de servicio diferente automáticamente enruta los mensajes a una nueva versión de servicio.  
  
  Para probar estos escenarios, vamos a usar los ejemplos siguientes:  
  
- **Servicio de búsqueda al cliente** proporcionado con el instalador de Sentinet. Este servicio se puede iniciar desde el menú Inicio.  
  
- **Nevatech.Vsb.BizTalk.Samples** solución proporcionada con el instalador de Sentinet. Este ejemplo está disponible en `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples`.  
  
- ESB. Ejemplo Itinerary.Test acompaña [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]. Esta opción está disponible en `<install drive>:\Program Files (x86)\Microsoft BizTalk ESB Toolkit\ESBSource.zip\Source\Samples\Itinerary\Source\ESB.Itinerary.Test` y se usa para probar los ejemplos de mensajes para el servicio de búsqueda al cliente.  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-the-service-policy-binding"></a>Para probar a la resolución de Sentinet cambiando el enlace de la directiva de servicio  
  
1. Asegúrese de que el **CustomerSearch** se está ejecutando el servicio que ha implementado con wsHttpBinding.  
  
2. Desde el **Nevatech.Vsb.BizTalk.Samples** ejemplo, abra **CustomerSearch.Search.itinerary**, seleccione **resolver el extremo de servicio** bajo el **mensaje Extensor** dentro de la **enrutar el mensaje** forma y para el **palabras clave** propiedad, especifique una palabra clave, como **TestKeyword**.  
  
    ![Asignar palabra clave](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3. Guarde los cambios en el itinerario y exportar el modelo. Haga doble clic en cualquier lugar en la superficie del Diseñador de itinerarios y haga LIC **Exportar modelo**.  
  
4. En la consola de administración de BizTalk Server, haga clic en el **Microsoft.Practices.ESB** aplicación, haga clic en Importar y, a continuación, haga clic en enlaces. Vaya a la ubicación del ejemplo de resolución de ESB en `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`y abra el **BizTalk.Bindings.xml** archivo. Esto crea el **Sentinet petición-respuesta** y **Sentinet unidireccional** necesarios para los itinerarios de ejemplo de puertos de envío.  
  
    Además, asegúrese de que todos los puertos de envío y recepción de las ubicaciones de la **Microsoft.Practices.ESB** están dadas de alta y se inician la aplicación de BizTalk.  
  
5. Abra el **ESB. Itinerary.Test** aplicación, compílelo y ejecútelo. En el cliente de prueba de itinerario se inicia, realice los pasos siguientes:  
  
   1.  En el cliente de prueba de itinerario en **opciones del servicio Web**, desactive **usar el servicio de WCF**y seleccione **dos servicios de manera**.  
  
   2.  Desde el **tipo de servicio** lista desplegable, seleccione **mensajería**.  
  
   3.  Haga clic en **carga itinerario** y navegue hasta la **CustomerSearch.Search.Itinerary.xml** archivo se encuentra en el proyecto de ejemplo **ExportedItineraries** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
   4.  Haga clic en el botón de puntos suspensivos (**...** ) en **carga mensaje** de grupo y vaya a **CustomerSearch.Search.Request.xml** ubicado en el proyecto **SampleMessages** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
   5.  Haga clic en **Submit Request** y compruebe que recibe la respuesta en.  
  
6. En el **CustomerSearch** cuadro de diálogo, tenga en cuenta que el contador se incrementa en uno.  
  
7. En la consola administrativa Sentinet, actualice los detalles del extremo que se use basicHttpBinding en lugar de wsHttpBinding.  
  
   1.  Seleccione el punto de conexión de servicio, haga clic en el **detalles** pestaña y, a continuación, haga clic en **modificar**.  
  
   2.  En el **detalles** pestaña, haga clic en el botón de puntos suspensivos (**...** ) en el **directiva** sección, para iniciar el **modificar directiva** asistente.  
  
        ![Iniciar el Asistente para modificar la directiva](../technical-guides/media/sentinetwp-modifypolicy-1.png "SentinetWP_ModifyPolicy_1")  
  
   3.  En la primera página, conservar el tipo de directiva como **privada** y, a continuación, haga clic en **siguiente**.  
  
   4.  En la segunda página, cambie la **wsHttpBinding** elemento XML que se **basicHttpBinding** (distingue mayúsculas de minúsculas) y, a continuación, haga clic en **finalizar**.  
  
        ![Actualizar el enlace de la directiva](../technical-guides/media/sentinetwp-modifypolicy-2.png "SentinetWP_ModifyPolicy_2")  
  
   5.  Haga clic en **guardar** para guardar los cambios en los detalles del extremo.  
  
8. Detener el **CustomerSearch** de servicio, cambie el enlace de **wsHttpBinding** a **basicHttpBinding**, y, a continuación, vuelva a iniciar el servicio.  
  
    ![Reinicie el servicio con otro enlace](../technical-guides/media/sentinetwp-restartcustservice.png "SentinetWP_RestartCustService")  
  
9. Desde el **probar itinerario cliente**, enviar un mensaje de prueba de nuevo para el servicio de búsqueda de clientes. Tenga en cuenta que el contador en el cuadro de diálogo de servicio de búsqueda de cliente nuevo se incrementa en 1.  
  
     Una vez que el mensaje se recibe correctamente desde la consola de administración Sentinet cambiar la directiva de copia de los detalles en **wsHttpBinding**. De forma similar, detenga el **búsqueda de clientes** de servicio, cambie la directiva al wsHttpBinding e iniciar el servicio.  
  
   Este ejemplo muestra cómo se pueden actualizar los detalles del servicio en el repositorio de Sentinet sobre la marcha para un punto de conexión de servicio actualizada de destino sin cambiar el itinerario o el cliente.  
  
#### <a name="to-test-the-sentinet-resolver-by-changing-keyword-assignments"></a>Para probar a la resolución de Sentinet cambiando las asignaciones de la palabra clave  
  
1.  Asegúrese de que las dos instancias de **CustomerSearch** se ejecuten los servicios que implementan con el wsHttpBinding y basicHttpBinding.  
  
2.  Desde el **Nevatech.Vsb.BizTalk.Samples** ejemplo, abra **CustomerSearch.Search.itinerary**, seleccione **resolver el extremo de servicio** bajo el **mensaje Extensor** dentro de la **enrutar el mensaje** forma y para el **palabras clave** propiedad, especifique una palabra clave, como **TestKeyword**.  
  
     ![Asignar palabra clave](../technical-guides/media/sentinetwp-assignkeyword.png "SentinetWP_AssignKeyword")  
  
3.  Guarde los cambios en el itinerario y exportar el modelo. Haga doble clic en cualquier lugar en la superficie del Diseñador de itinerarios y haga LIC **Exportar modelo**.  
  
4.  En la consola de administración de BizTalk Server, haga clic en el **Microsoft.Practices.ESB** aplicación, haga clic en Importar y, a continuación, haga clic en enlaces. Vaya a la ubicación del ejemplo de resolución de ESB en `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver`y abra el **BizTalk.Bindings.xml** archivo. Esto crea el **Sentinet petición-respuesta** y **Sentinet unidireccional** necesarios para los itinerarios de ejemplo de puertos de envío.  
  
     Además, asegúrese de que todos los puertos de envío y recepción de las ubicaciones de la **Microsoft.Practices.ESB** están dadas de alta y se inician la aplicación de BizTalk.  
  
5.  Abra el **ESB. Itinerary.Test** aplicación, compílelo y ejecútelo. En el cliente de prueba de itinerario se inicia, realice los pasos siguientes:  
  
    1.  En el cliente de prueba de itinerario en **opciones del servicio Web**, desactive **usar el servicio de WCF**y seleccione **dos servicios de manera**.  
  
    2.  Desde el **tipo de servicio** lista desplegable, seleccione **mensajería**.  
  
    3.  Haga clic en **carga itinerario** y navegue hasta la **CustomerSearch.Search.Itinerary.xml** archivo se encuentra en el proyecto de ejemplo **ExportedItineraries** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\ExportedItineraries`.  
  
    4.  Haga clic en el botón de puntos suspensivos (**...** ) en **carga mensaje** de grupo y vaya a **CustomerSearch.Search.Request.xml** ubicado en el proyecto **SampleMessages** carpeta `<installation drive>:\Program Files\Nevatech\Sentinet BizTalk Extensions\Samples\ESB Resolver\SampleMessages`.  
  
    5.  Haga clic en **Submit Request** y compruebe que recibe la respuesta en.  
  
6.  En el **CustomerSearch** cuadro de diálogo, tenga en cuenta que el contador se incrementa en uno.  
  
7.  En la consola de administración Sentinet, quite el **TestKeyword** asociado con el **versión 1** de la **CustomerSearch** de servicio y asociarla a **Versión 2** del servicio.  
  
    1.  Abra la consola administrativa de Sentinet, haga clic en **versión 1** bajo el **CustomerSearch** de servicio, haga clic en el punto de conexión de wsHttpBinding y, a continuación, haga clic en el **datos adjuntos** pestaña y, a continuación, haga clic en **modificar**.  
  
         ![Quite la palabra clave del servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword.png "SentinetWP_RemoveKeyword")  
  
    2.  Haga clic en el botón de la palabra clave que escribió antes de eliminar la palabra clave, haga clic en **Sí** en el cuadro de mensaje y, a continuación, haga clic en **guardar**.  
  
         ![Quite la palabra clave de servicio CustomerSearch](../technical-guides/media/sentinetwp-removekeyword-2.png "SentinetWP_RemoveKeyword_2")  
  
    3.  Ahora, asigne la misma palabra clave (**TestKeyword**) a la **basicHttpBinding** extremo bajo el **versión 2** del mismo servicio.  
  
8.  Enviar un mensaje de prueba de nuevo desde el **probar itinerario cliente** y tenga en cuenta que esta vez, el contador se incrementa en el cuadro de diálogo que representa la versión 2 del servicio, implementado con basicHttpBinding.