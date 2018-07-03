---
title: ¿Qué es el adaptador de Windows SharePoint Services? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, process flow
- Windows SharePoint Services adapters, receiving documents
- Windows SharePoint Services adapters, sending documents
- Windows SharePoint Services adapters, security
- Windows SharePoint Services adapters
- Windows SharePoint Services adapters, about Windows SharePoint Services adapters
ms.assetid: 1875ac85-46c2-4da5-ad16-8b078cb4cbd7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c5d97c55918b82a639e502681db9289befa9f32
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973533"
---
# <a name="what-is-the-windows-sharepoint-services-adapter"></a>¿Qué es el adaptador de Windows SharePoint Services?
El adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Windows SharePoint Services proporciona una mayor integración con Windows SharePoint Services y Microsoft Office InfoPath. En el siguiente tema se describen las características del adaptador de Windows SharePoint Services, así como una descripción general de su funcionamiento.  
  
## <a name="features-of-the-windows-sharepoint-services-adapter"></a>Características del adaptador de Windows SharePoint Services  
 En la siguiente lista se describen importantes características del adaptador de Windows SharePoint Services:  
  
-   Capacidad para enviar mensajes binarios y XML de BizTalk Server a las bibliotecas de documentos de SharePoint.  
  
-   Integración con InfoPath: puede transformar los mensajes salientes de XML de BizTalk Server para abrir automáticamente en InfoPath cuando se abre desde el sitio Windows SharePoint Services.  
  
-   Promoción de propiedades para mensajes dirigidos a Windows SharePoint Services. Se pueden actualizar hasta 16 columnas de SharePoint con metadatos de BizTalk Server con respecto al Id. de instancia de orquestación de apariencia de mensaje, Id. de mensaje o a los valores extraídos del mensaje.  
  
-   Definición de nombre de archivo basada en el contenido de mensajes y en las propiedades de BizTalk Server.  
  
-   La capacidad para enviar documentos a una lista arbitraria (en lugar de a una biblioteca de documentos): en este caso, el propio documento no se almacena en Windows SharePoint Services pero todavía se produce la promoción de propiedades para que se crea un nuevo elemento de lista y se recuperan los valores de columna desde el mensaje.  
  
-   Capacidad para recibir mensajes desde cualquier vista de cualquier biblioteca y archivarlos en una biblioteca de documentos concreta utilizando el nombre de archivo especificado.  
  
-   La promoción de propiedades del adaptador de Windows SharePoint Services en BizTalk Server: información de archivo de Windows SharePoint Services está disponible en el servidor BizTalk Server como propiedades de contexto de mensaje. Las propiedades de contexto de mensaje se pueden acceder desde las canalizaciones, orquestaciones, etcetera. Columnas personalizadas de SharePoint pueden obtenerse a través de WSS. InPropertiesXml de documento.  
  
-   Compatibilidad completa para los puertos dinámicos: enviar adaptadores pueden admitir enlaces de URI estáticos (definido por el usuario cuando se crea el puerto de envío) o enlaces de URI dinámicos (definido por la orquestación al enviar el mensaje). Toda la información de configuración se puede definir mediante las propiedades de contexto de mensaje, como WSS.Filename y WSS.ConfigTimeout, tanto para puertos de envío dinámicos como para puertos de envío físicos.  
  
-   Contadores de rendimiento  
  
## <a name="how-the-windows-sharepoint-services-adapter-works"></a>Funcionamiento del adaptador de Windows SharePoint Services  
 El adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Windows SharePoint Services se compone de tres componentes principales:  
  
- Servicio Web del adaptador de Windows SharePoint Services  
  
- Adaptador de recepción de Windows SharePoint Services  
  
- Adaptador de envío de Windows SharePoint Services  
  
  En el servidor de Windows SharePoint Services, el servicio Web (BTSharePointAdapterWS.asmx) se instala para proporcionar acceso a las listas y bibliotecas de Windows SharePoint Services. El servicio Web presenta métodos para obtener documentos, colocarlos, eliminarlos y archivarlos desde una biblioteca de SharePoint. El adaptador de recepción recupera archivos desde el servicio Web, mientras que el adaptador de envío le envía archivos.  
  
  La siguiente ilustración muestra los principales componentes del adaptador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para Windows SharePoint Services que ofrecen estas funciones.  
  
  ![](../core/media/bts-dev-adapters-wss-architecture.gif "BTS_Dev_Adapters_WSS_Architecture")  
  
### <a name="receiving-documents-from-windows-sharepoint-services"></a>Recibir documentos desde Windows SharePoint Services  
 El adaptador de recepción efectúa un sondeo de las vistas de bibliotecas de documentos de Windows SharePoint Services. Efectúa una llamada al método Web del servidor de Windows SharePoint Services que utiliza el modelo de objetos de Windows SharePoint Services para examinar la biblioteca, desproteger los archivos y devolver los datos del archivo al adaptador. Seguidamente, el adaptador envía los archivos al cuadro de mensajes de BizTalk Server y efectúa una llamada a otro método Web para eliminar o archivar los archivos desde Windows SharePoint Services. Para filtrar los archivos en una biblioteca de Windows SharePoint Services, el adaptador realiza un sondeo de la biblioteca de Windows SharePoint Services mediante una vista de Windows SharePoint Services.  
  
 El enfoque centralizado (de sondeo) ofrece un modelo de administración sencillo en el que la configuración se efectúa en el servidor BizTalk Server. También ofrece un mejor rendimiento gracias al hecho de que permite procesar los mensajes por lotes.  
  
 Puesto que la compatibilidad de transacción de nivel de plataforma no se encuentra disponible en la totalidad de Windows SharePoint Services, de los servicios Web y de BizTalk Server, el mecanismo de desprotección se utiliza para minimizar los errores asociados a las condiciones de error. En ciertas condiciones (esto es, cuando los archivos se envían correctamente a la base de datos de cuadro de mensajes de BizTalk Server pero no se pueden eliminar de Windows SharePoint Services), los archivos permanecerán desprotegidos en el servidor de Windows SharePoint Services aun cuando se hayan enviado al servidor BizTalk Server. Los errores se recogerán en el registro de sucesos del servidor BizTalk Server.  
  
### <a name="sending-documents-to-windows-sharepoint-services"></a>Enviar documentos a Windows SharePoint Services  
 El adaptador envía documentos a Windows SharePoint Services llamando a un método Web en el servidor de Windows SharePoint Services. El adaptador especifica la dirección URL del sitio de Windows SharePoint Services, de la biblioteca de documentos o de la dirección URL de la lista relacionada con el nombre del elemento de lista, de archivo o de sitio, así como con las propiedades promocionadas que asocian al archivo.  
  
 Se puede establecer el nombre de archivo como una cadena fija o como un nombre derivado de los datos XML del documento. La derivación del nombre puede resultar muy útil para forzar las convenciones de denominación estándar. El adaptador también puede establecer valores de propiedades promocionadas en el archivo como valores de columna. Al igual que ocurre con los nombres de archivo, los valores de propiedades promocionadas se pueden establecer o pueden derivar de los datos XML del documento.  
  
> [!IMPORTANT]
>  Las propiedades promocionadas del adaptador de Windows SharePoint Services son entidades distintas a las propiedades de BizTalk Server o a las propiedades promocionadas de Windows SharePoint Services.  
  
 Las propiedades promocionadas de Windows SharePoint Services se utilizan para hacer que los elementos XML resulten visibles cuando se examina una biblioteca de formularios de Windows SharePoint Services. Cuando se publica un formulario de InfoPath en una biblioteca de formularios de Windows SharePoint Services, InfoPath configura la biblioteca de formularios para promover elementos clave automáticamente. Esta característica se encuentra disponible en Windows SharePoint Services únicamente al utilizar las bibliotecas de formularios de InfoPath (bibliotecas de documentos que almacenan formularios de InfoPath con el mismo esquema XSD y la misma solución InfoPath).  
  
 La promoción de propiedades del adaptador de Windows SharePoint Services permite al usuario promocionar propiedades en Windows SharePoint Services cuando en la misma biblioteca de documentos se almacenan documentos con esquemas diferentes.  
  
 La promoción de propiedades de BizTalk Server es un concepto parecido, con la diferencia de que las propiedades se hacen visibles para la orquestación como propiedades en el mensaje, y no en la UI para el usuario final. Además, BizTalk Server admite un concepto de degradación de propiedades cuando los valores de éstas se vuelven a guardar en el documento.  
  
 Al utilizar el adaptador de Windows SharePoint Services con las bibliotecas de formularios y los formularios de InfoPath (en lugar de con bibliotecas de documentos y XML arbitrarias), no necesita establecer las propiedades promocionadas mediante el adaptador de envío. En lugar de eso, el documento se puede cambiar en la orquestación (directamente cambiando el mensaje, o indirectamente, a través de propiedades que se degradarán). Windows SharePoint Services promocionará los valores automáticamente.  
  
## <a name="security-considerations-for-the-windows-sharepoint-services-adapter"></a>Consideraciones de seguridad para el adaptador de Windows SharePoint Services  
 El adaptador de Windows SharePoint Services se compone de subsistemas, del servicio Web BTSharePointAdapterWS que se ejecuta en el sitio Web de Windows SharePoint Services y del tiempo de ejecución del adaptador que se ejecuta en el servidor BizTalk Server en el proceso de instancia de host de BizTalk Server. El tiempo de ejecución del adaptador invoca el servicio Web BTSharePointAdapterWS, que debe contar con permisos para efectuar ciertas tareas en Windows SharePoint Services. Puesto que este componente se ejecuta como autor de la llamada, hay que conceder los permisos al autor de la llamada. Esto significa que la instancia de host de BizTalk debe realizarse una **colaborador** en el sitio de SharePoint para poder enviar y recibir mensajes desde ese sitio. Se puede invocar el servicio BTSharePointAdapterWS Web únicamente por miembros de la **Hosts habilitados de SharePoint** grupo. Para permitir que una instancia de host de BizTalk, ejecuta el adaptador en tiempo de ejecución, para interactuar con el servicio Web, la cuenta de Windows de la instancia de host debe hacerse miembro de la **Hosts habilitados de SharePoint** grupo. Es responsabilidad del administrador para agregar y quitar cuentas de este grupo, así como hacer que la instancia de host de las cuentas de los miembros de SharePoint **colaborador** rol.  
  
|Componente|Identidad de proceso|Permiso|  
|---------------|----------------------|----------------|  
|Servicio Web BTSharePointAdapterWS|Identidad del autor de la llamada|El permiso de invocación se le concede al grupo Hosts habilitados de SharePoint.|  
|Tiempo de ejecución del adaptador|Identidad del host de BizTalk|N/D|  
|Modelo de objetos de Windows SharePoint Services|N/D|El grupo Hosts habilitados de SharePoint debe ser un miembro de la **colaborador** rol de SharePoint Services.|  
  
 El programa de instalación de BizTalk Server configura los permisos en el servicio BTSharePointAdapterWS Web para que solo las cuentas que son miembros de la **Hosts habilitados de SharePoint** grupo puede tener acceso a este servicio Web. Si desea que los hosts para ejecutar el adaptador de Windows SharePoint Services, el administrador tendrá que agregar el grupo de NT asociado con ese host para el **Hosts habilitados de SharePoint** agrupar y agregar también el **Hosts habilitados de SharePoint**  grupo a Windows SharePoint Services **colaborador** rol.  
  
 Los permisos con respecto a las bibliotecas de documentos, listas y archivos de Windows SharePoint Services se restringen utilizando la seguridad de Windows SharePoint Services. Los mensajes se envían desde Windows SharePoint Services directamente a BizTalk Server. La comunicación entre el tiempo de ejecución del adaptador y el servicio Web se establece mediante HTTP o HTTPS.  
  
 El adaptador asume que el servicio Web BTSharePointAdapterWS utiliza el mismo esquema HTTP (HTTP o HTTPS) que el sitio de Windows SharePoint Services. Esto significa que el adaptador utilizará HTTPS para comunicarse con el servicio Web BTSSharePointAdapterWS cuando el sitio de Windows SharePoint Services se cree en un sitio Web de IIS seguro, o que utilizará HTTP para comunicarse con el servicio Web BTSharePointAdapterWS cuando el sitio de Windows SharePoint Services se cree en un sitio Web de IIS sin un certificado de servidor.  
  
## <a name="see-also"></a>Vea también  
 [Configuración e implementación del adaptador de Windows SharePoint Services](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)   
 [Configuración del adaptador de Windows SharePoint Services](../core/configuring-the-windows-sharepoint-services-adapter.md)   
 [Tutoriales del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-walkthroughs.md)