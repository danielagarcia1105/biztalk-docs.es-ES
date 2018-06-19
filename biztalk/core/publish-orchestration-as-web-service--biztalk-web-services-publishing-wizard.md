---
title: Asistente para publicar una orquestación como un servicio Web de publicación de servicios de cómo utilizar la Web de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard
- Web services, orchestrations
- BizTalk Web Services Publishing Wizard, orchestrations
- BizTalk Web Services Publishing Wizard, about BizTalk Web Services Publishing Wizard
- orchestrations, publishing
ms.assetid: d990f8e4-88ce-4718-8a94-63796b8d92dc
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c86721091b9a0c9e8436b42a7489e228dbb7e0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25975346"
---
# <a name="how-to-use-the-biztalk-web-services-publishing-wizard-to-publish-an-orchestration-as-a-web-service"></a>Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar una orquestación como servicio Web
El Asistente para publicar servicios Web de BizTalk se utiliza para publicar orquestaciones como servicios Web.  
  
> [!NOTE]
>  Debe generar los proyectos de BizTalk antes de ejecutar al Asistente para publicación de servicios Web de BizTalk.  
  
> [!NOTE]
>  Puede utilizar una herramienta de línea de comandos, BTSWebSvcPub.exe, para publicar orquestaciones como servicios Web. Para obtener más información, consulte [referencia de línea de comandos de BTSWebSvcPub](../core/btswebsvcpub-command-line-reference.md).  
  
### <a name="to-publish-an-orchestration-as-a-web-service"></a>Para publicar una orquestación como un servicio Web  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **BizTalk Web Asistente para publicar servicios**.  
  
2.  En el **éste es el Asistente para publicación de servicios Web de BizTalk** página, haga clic en **siguiente**.  
  
3.  En el **crear servicio Web** página, seleccione **publicar orquestaciones de BizTalk como servicios web**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **ensamblado de BizTalk** página, en el archivo de ensamblado de BizTalk (\*.dll) cuadro de texto, escriba el nombre del archivo de ensamblado de BizTalk o haga clic en **examinar** para buscar el ensamblado que contiene el las orquestaciones para publicar y, a continuación, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  Antes de seleccionar un archivo de ensamblado de BizTalk, copie todos los ensamblados dependientes en la misma carpeta con el ensamblado de BizTalk o instale los ensamblados dependientes en la caché de ensamblados global (GAC).  
  
    > [!NOTE]
    >  Si ha instalado el archivo de ensamblado de BizTalk en la GAC, asegúrese de que el ensamblado en la GAC se ha actualizado con el ensamblado que seleccionará en el **ensamblado de BizTalk** cuadro de diálogo. Si la GAC tiene el mismo nombre completo, el Asistente para publicar servicios Web de BizTalk utiliza el archivo de ensamblado en la GAC en lugar del que ha seleccionado.  
  
    > [!NOTE]
    >  Si abre el Asistente para publicar servicios Web de BizTalk en el Visual Studio que contiene una orquestación, el archivo de ensamblado de BizTalk rellena con el ensamblado que contiene la orquestación.  
  
    > [!NOTE]
    >  Las rutas que contienen más de 260 caracteres pueden obtener un mensaje de error que informa que la ruta es demasiado larga.  
  
5.  En el **orquestaciones y puertos** página, expanda los nodos de árbol para cada ensamblado y orquestación haciendo clic en el signo más. Seleccione las orquestaciones y puertos para publicar mediante la activación de las casillas de verificación de nodo de árbol correspondientes. Si desea crear un servicio Web (.asmx) para todos los puertos de recepción seleccionados en lugar de un servicio Web para cada puerto de recepción, seleccione el **combinar todos los puertos seleccionados en un solo servicio web** opción y, a continuación, haga clic en **siguiente** .  
  
    > [!NOTE]
    >  Cuando combina todos los puertos seleccionados en un único servicio Web, todos los puertos seleccionados tiene el mismo tipo de puerto y los nombres de operaciones en los puertos son únicos.  
  
6.  En el **propiedades del servicio Web** página, en la **espacio de nombres de destino del servicio web** cuadro, escriba un espacio de nombres de destino para el servicio Web, seleccione las casillas adecuadas para especificar cómo debe controlar el Asistente SOAP encabezados y SharePoint Portal Server 2007 Single Sign-On (SSO) se admiten para el servicio Web. Si desea personalizar aún más la implementación del servicio Web, haga clic en **avanzadas** botón. Mostrará más opciones disponibles:  
  
    |Opción|Value|Description|  
    |------------|-----------|-----------------|  
    |Estilo de parámetro SOAP|Predeterminado|Esta opción especifica el modo en que se da formato a los parámetros de un mensaje SOAP. Para obtener más información, vea SoapParameterStyle Enumeration en [ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259).|  
    |Estilo de parámetro SOAP|Reconstrucción|Esta opción especifica el modo en que se da formato a los parámetros de un mensaje SOAP. Para obtener más información, vea SoapParameterStyle Enumeration en [ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259).|  
    |Estilo de parámetro SOAP|Ajustado|Esta opción especifica el modo en que se da formato a los parámetros de un mensaje SOAP. Para obtener más información, vea SoapParameterStyle Enumeration en [ http://go.microsoft.com/fwlink/?LinkId=62259 ](http://go.microsoft.com/fwlink/?LinkId=62259).|  
    |Afirmaciones de conformidad|None|Esta opción especifica la interoperabilidad de servicios Web (WSI) en la que se afirma que el enlace se ajusta. Para obtener más información, vea WebServiceBindingAttribute.ConformsTo Property en [ http://go.microsoft.com/fwlink/?LinkId=193064 ](http://go.microsoft.com/fwlink/?LinkId=193064).|  
    |Afirmaciones de conformidad|Perfil básico de servicios Web WS-I, versión 1.1|Esta opción especifica la interoperabilidad de servicios Web (WSI) en la que se afirma que el enlace se ajusta. Para obtener más información, vea WebServiceBindingAttribute.ConformsTo Property en [ http://go.microsoft.com/fwlink/?LinkId=193064 ](http://go.microsoft.com/fwlink/?LinkId=193064).|  
    |Forzar solicitud-respuesta|[Predeterminado]|Esta opción especifica si se deben exponer las operaciones de BizTalk unidireccionales como métodos Web de solicitud-respuesta. El valor predeterminado es no forzar el indicador unidireccional.|  
    |Forzar solicitud-respuesta|no|Esta opción especifica si se deben exponer las operaciones de BizTalk unidireccionales como métodos Web de solicitud-respuesta. El valor predeterminado es no forzar el indicador unidireccional.|  
    |Forzar solicitud-respuesta|Sí|Esta opción especifica si se deben exponer las operaciones de BizTalk unidireccionales como métodos Web de solicitud-respuesta. El valor predeterminado es no forzar el indicador unidireccional.|  
  
7.  En el **propiedades del servicio Web** página, haga clic en **siguiente**.  
  
    > [!NOTE]
    >  La selección de algunas de las opciones de encabezado SOAP se aplican globalmente a todos los servicios Web y los métodos Web que se crean al ejecutar esta instancia del asistente.  
  
8.  Si seleccionó **agregar encabezados SOAP adicionales** opción, el **encabezados SOAP de solicitud** y **encabezados SOAP de respuesta** páginas aparecen. Puede agregar y quitar encabezados SOAP de solicitud y respuesta mediante la **agregar** y **quitar** botones en los cuadros de diálogo siguientes:  
  
    -   Para agregar un encabezado SOAP, haga clic en **agregar**. En el **archivo de ensamblado de BizTalk (\*.dll)** cuadro de texto, escriba o busque el ensamblado que contiene el esquema de encabezado SOAP. El **tipos de esquemas disponibles** vista de lista muestra cada elemento raíz del esquema. Seleccione un nodo raíz para agregar como un encabezado SOAP de solicitud o de respuesta. Para seleccionar varios elementos, mantenga presionada la tecla CTRL y haga clic en **Aceptar**.  
  
    -   Para quitar un encabezado SOAP de la lista, selecciónelo en la lista de encabezados SOAP agregados y, a continuación, haga clic en **quitar**.  
  
    -   Haga clic en **siguiente** en cada **encabezado SOAP** página para continuar con el asistente.  
  
    > [!NOTE]
    >  Un espacio de nombres de destino y un nombre de elemento raíz definen un encabezado SOAP.  
  
    > [!NOTE]
    >  Si se agrega la misma combinación de espacio de nombres de destino/nombre de elemento raíz como un encabezado SOAP de solicitud y de respuesta, no se tratará como un encabezado de entrada o salida. Debe copiar manualmente el encabezado entrante en el encabezado saliente en el interior de una orquestación.  
  
    > [!NOTE]
    >  La misma combinación de espacio de nombres de destino/nombre de elemento raíz sólo se puede agregar una vez como un encabezado SOAP de solicitud y una vez como encabezado SOAP de respuesta.  
  
9. En el **proyecto de servicio Web** página, en la **nombre del proyecto** texto, escriba el nombre para el proyecto. Puede aceptar la ubicación predeterminada (http://localhost/<*Nombre_proyecto*>), escriba una ubicación para el proyecto en el **ubicación del proyecto** cuadro de texto o haga clic en **examinar** y Seleccione un directorio Web. Seleccione cualquiera de las siguientes opciones:  
  
    -   **Sobrescribir proyecto existente.** Esta opción únicamente está disponible si la ubicación del proyecto ya existe. Podrá publicar en la misma ubicación sólo si selecciona esta opción. De lo contrario, debe especificar una ubicación de proyecto diferente.  
  
    -   **Permitir el acceso anónimo al servicio web.** Esta opción agrega acceso anónimo al directorio virtual creado. De forma predeterminada, el directorio virtual hereda los privilegios de acceso de su directorio virtual principal o del sitio Web (si existe un directorio virtual de nivel superior).  
  
    -   **Crear BizTalk ubicaciones de recepción.** esta opción crea de forma automática los puertos y las ubicaciones de recepción del adaptador de SOAP que correspondan a cada archivo .asmx generado. Si ya existe una ubicación de recepción, no se sustituirá. Ubicaciones de recepción para el adaptador de SOAP se resuelven mediante el formato /\<*nombre del directorio virtual*\>/\<*namespace_typename_portname de orquestación*  \>.asmx. Después de seleccionar esta opción, elija la aplicación donde se generarán los puertos y las ubicaciones de recepción.  
  
        > [!NOTE]
        >  La ubicación del proyecto puede producirse en un servidor distinto. Para publicar un servicio Web en un servidor diferente, escriba el nombre del proyecto como **http://<*servername*>/<*Nombre_proyecto*>**.  
  
        > [!NOTE]
        >  La ubicación del proyecto puede producirse en un sitio Web que no sea predeterminado. Cuando se publique en un sitio Web que no sea predeterminado, incluya el número de puerto del sitio Web en la URL. Por ejemplo, http://localhost:8080/< *Nombre_proyecto*>.  
  
        > [!NOTE]
        >  Al utilizar el asistente para crear ubicaciones de recepción, éstas se crean mediante los valores predeterminados. El valor predeterminado para la canalización de recepción es el **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** canalización. Si los mensajes recibidos a través del servicio Web publicado requieren algún procesamiento de canalización especial (por ejemplo, validación, correlación o promoción de propiedades o asignaciones de entrada/salida), a continuación, debe establecer la canalización de recepción en  **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, o en una canalización personalizada.  
  
        > [!NOTE]
        >  Cuando consume servicios Web (llamada) desde una orquestación, el adaptador de SOAP sólo admite canalizaciones de envío de paso a través de estilo. Puede usar una canalización de envío personalizada, pero no puede contener componentes que modifican las partes del cuerpo del mensaje. Estos componentes incluyen el ensamblador de XML y los componentes de codificación.  
  
        > [!NOTE]
        >  Cuando llegue a esta página y si decide revertir de la elección de **publicar esquemas como servicios web** opción, en la **servicios Web** página, es posible que vea el **dedescripcióndeservicioWeb** muestra los nombres de servicio y método desde el ensamblado de BizTalk anterior seleccionada antes de revertir de **publicar orquestaciones de BizTalk como servicios web** opción. Esto es así porque la descripción del servicio Web en memoria no se desactiva cuando se cambia el método de publicación.  
  
10. Haga clic en **siguiente** para revisar la configuración para el proyecto de servicio Web de ASP.NET.  
  
11. Haga clic en **crear** para crear el servicio Web de ASP.NET.  
  
12. Haga clic en **finalizar** para completar el Asistente para publicación de servicios Web de BizTalk.  
  
> [!NOTE]
>  Si va a publicar una orquestación como un servicio Web en Windows Vista, debe actualizar el directorio virtual que aloja el servicio. Para ello, ejecute el siguiente comando desde el símbolo del sistema, reemplazando \<vdir\> con el nombre del directorio virtual: **% systemroot%\system32\inetsrv\APPCMD. EXE migrar configuración "Default Web Site /\<vdir nombre\>"**.  
  
## <a name="see-also"></a>Vea también  
 [Publicar una orquestación como servicio Web](../core/publishing-an-orchestration-as-a-web-service.md)   
 [Cómo asignar orquestaciones a servicios Web](../core/how-to-map-orchestrations-to-web-services.md)