---
title: "Asistente para publicar esquemas como servicios Web de publicación de servicios de cómo utilizar la Web de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Web Services Publishing Wizard, publishing
- BizTalk Web Services Publishing Wizard, schemas
ms.assetid: b22de720-1416-486a-988f-e52527ad9ab1
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba7f93eae8866212546f5daa3b9ed1a5b653c983
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-the-biztalk-web-services-publishing-wizard-to-publish-schemas-as-a-web-service"></a>Cómo usar el Asistente para publicar los servicios Web de BizTalk para publicar esquemas como servicios Web
El Asistente para publicar servicios Web de BizTalk permite publicar esquemas como servicio Web.  
  
### <a name="to-publish-schemas-as-a-web-service"></a>Para publicar esquemas como servicio Web  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Asistente para publicación de BizTalk Web Services**.  
  
    > [!IMPORTANT]
    >  Antes de ejecutar el Asistente para publicar servicios Web de BizTalk, debe crear los proyectos de BizTalk.  
  
2.  En el **bienvenida** página, haga clic en **siguiente**.  
  
3.  En el **crear servicio Web** página, seleccione **publicar esquemas como servicios web** y, a continuación, haga clic en **siguiente**.  
  
4.  En el **servicio Web** , defina los servicios Web que se van a publicar. Utilice el árbol en el **descripción de servicio Web** cuadro de diálogo para agregar, quitar, cambiar el nombre y editar los nodos de descripción del servicio Web. El **información** cuadro de diálogo proporciona información sobre el nodo seleccionado y muestra todos los errores en el nodo actual o cualquier subnodos:  
  
    -   El nodo raíz del árbol (Descripción del servicio Web) describe el nombre del proyecto del servicio Web. El nombre del directorio virtual usa el nodo raíz como nombre predeterminado. Puede modificar la descripción del servicio Web mediante la selección **cambiar el nombre de descripción del servicio web**.  
  
    -   Para agregar un nuevo servicio Web, haga clic en el **descripción de servicio Web** nodo y, a continuación, haga clic en **Agregar servicio web**. Se creará un servicio Web nuevo sin ningún método Web. Para modificar el nombre del servicio Web, haga clic en el nodo de servicio Web y seleccione **cambiar servicio web**, y, a continuación, presione ENTRAR para aceptar el nuevo nombre.  
  
    -   Para agregar un nuevo método Web, haga clic en el nodo de servicio Web, seleccione **Agregar método Web**y, a continuación, haga clic en **unidireccional** (para una solicitud de método Web) o **solicitud-respuesta** (para un método de Web de solicitud-respuesta) en el menú contextual.  
  
    -   Para establecer tipos de esquemas de solicitud y respuesta, haga clic en el **solicitud** o **respuesta** nodo y, a continuación, haga clic en **Seleccionar tipo de esquema**. En el **tipo de mensaje de solicitud** cuadro de diálogo, escriba el nombre del ensamblado que contiene el esquema de documento en el **archivo de ensamblado de BizTalk** cuadro de texto o haga clic en **examinar** para buscar para el ensamblado. El **tipos de esquemas disponibles** vista de lista muestra cada elemento raíz del esquema. Seleccione un nodo raíz para agregar como el tipo de esquema de solicitud o de respuesta.  
  
        > [!NOTE]
        >  Si ha instalado el archivo de ensamblado de BizTalk en la caché de ensamblados Global (GAC), asegúrese de que el ensamblado en la GAC se ha actualizado con el ensamblado que seleccionará en el **tipo de mensaje de solicitud** cuadro de diálogo. Si la GAC tiene el mismo nombre completo, el Asistente para publicar servicios Web de BizTalk utiliza el archivo de ensamblado en la GAC en lugar del que ha seleccionado.  
  
    -   Puede cambiar el nombre de la **solicitar** y **respuesta** nodos sin afectar al código generado. Después de definir los esquemas, puede cambiar el nombre a los elementos de parte, lo que modifica el nombre de parámetro del método Web. Los cambios se pueden ver al consultar el código del servicio Web generado.  
  
    > [!NOTE]
    >  No se pueden usar espacios cuando se cambia el nombre de alguno de los nodos de descripción del servicio Web.  
  
5.  Haga clic en **siguiente** para continuar con el asistente.  
  
6.  En el **propiedades del servicio Web** página, en la **espacio de nombres de destino del servicio web** cuadro de diálogo, escriba un espacio de nombres de destino para el servicio Web y seleccione las casillas adecuadas para especificar cómo debe el Asistente controlar encabezados SOAP y la compatibilidad con el inicio de sesión único para el servicio Web. Si desea personalizar aún más la implementación del servicio Web, haga clic en **avanzadas** botón. Mostrará más opciones disponibles:  
  
    |Opción|Valor|Description|  
    |------------|-----------|-----------------|  
    |Estilo de parámetro SOAP|Predeterminado|Esta opción especifica el modo en que se da formato a los parámetros de un mensaje SOAP. Para obtener más información, vea SoapParameterStyle Enumeration en [http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259).|  
    |Estilo de parámetro SOAP|Reconstrucción|Esta opción especifica el modo en que se da formato a los parámetros de un mensaje SOAP. Para obtener más información, vea SoapParameterStyle Enumeration en [http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259).|  
    |Estilo de parámetro SOAP|Ajustado|Esta opción especifica el modo en que se da formato a los parámetros de un mensaje SOAP. Para obtener más información, vea SoapParameterStyle Enumeration en [http://go.microsoft.com/fwlink/?LinkId=62259](http://go.microsoft.com/fwlink/?LinkId=62259).|  
    |Afirmaciones de conformidad|Ninguno|Esta opción especifica la interoperabilidad de servicios Web (WSI) en la que se afirma que el enlace se ajusta. Para obtener más información, vea WebServiceBindingAttribute.ConformsTo Property en [http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064).|  
    |Afirmaciones de conformidad|Perfil básico de servicios Web WS-I, versión 1.1|Esta opción especifica la interoperabilidad de servicios Web (WSI) en la que se afirma que el enlace se ajusta. Para obtener más información, vea WebServiceBindingAttribute.ConformsTo Property en [http://go.microsoft.com/fwlink/?LinkId=193064](http://go.microsoft.com/fwlink/?LinkId=193064).|  
    |Forzar solicitud-respuesta|[Predeterminado]|Esta opción especifica si se deben exponer las operaciones de BizTalk unidireccionales como métodos Web de solicitud-respuesta. El valor predeterminado es no forzar el indicador unidireccional.|  
  
    > [!NOTE]
    >  La selección de algunas de las opciones de encabezado SOAP se aplica globalmente a todos los servicios Web y los métodos Web que se crean al ejecutar esta instancia del asistente.  
  
7.  En el **propiedades del servicio Web** página, haga clic en **siguiente**.  
  
8.  Si seleccionó **agregar encabezados SOAP adicionales**, **encabezados SOAP de solicitud** y **encabezados SOAP de respuesta** páginas aparecen. Puede agregar y quitar encabezados SOAP de solicitud y respuesta mediante la **agregar** y **quitar** botones en los cuadros de diálogo siguientes:  
  
    -   Para agregar un encabezado SOAP, haga clic en **agregar**. En el **nombre de ensamblado de BizTalk (\*.dll)** cuadro de texto, escriba el nombre del ensamblado o busque el ensamblado que contiene el esquema de encabezado SOAP en el **archivo de ensamblado de BizTalk** cuadro de texto. El **tipos de esquemas disponibles** vista de lista muestra cada elemento raíz del esquema. Seleccione un nodo raíz para agregar como un encabezado SOAP de solicitud o de respuesta. Para seleccionar varios elementos, mantenga presionada la tecla CTRL y haga clic en **Aceptar**.  
  
    -   Para quitar un encabezado SOAP de la lista, selecciónelo en la lista de encabezados SOAP agregados y, a continuación, haga clic en **quitar**.  
  
    -   Haga clic en **siguiente** en cada página de encabezado SOAP para continuar con el asistente.  
  
    > [!NOTE]
    >  El espacio de nombres de destino y el nombre de elemento raíz definen un encabezado SOAP.  
  
    > [!NOTE]
    >  Si se agrega la misma combinación de espacio de nombres de destino/nombre de elemento raíz como un encabezado SOAP de solicitud y de respuesta, no se tratará como un encabezado de entrada o salida. Debe copiar manualmente el encabezado entrante en el encabezado saliente en el interior de una orquestación.  
  
    > [!NOTE]
    >  La misma combinación de espacio de nombres de destino/nombre de elemento raíz sólo se puede agregar una vez como un encabezado SOAP de solicitud y una vez como encabezado SOAP de respuesta.  
  
9. En el **proyecto de servicio Web** página, en la **ubicación del proyecto** texto, escriba la ubicación del proyecto. Puede aceptar la ubicación predeterminada (http://localhost/ <*Nombre_proyecto*>), escriba una ubicación para el proyecto o haga clic en **examinar** y seleccione un directorio Web. Seleccione cualquiera de las siguientes opciones:  
  
    -   **Sobrescribir proyecto existente.** Esta opción únicamente está disponible si la ubicación del proyecto ya existe. Podrá publicar en la misma ubicación sólo si selecciona esta opción. De lo contrario, debe especificar una ubicación de proyecto diferente.  
  
    -   **Permitir el acceso anónimo al servicio web.** Esta opción agrega acceso anónimo al directorio virtual creado. De forma predeterminada, el directorio virtual hereda los privilegios de acceso de su directorio virtual principal o del sitio Web (si existe un directorio virtual de nivel superior).  
  
    -   **Crear BizTalk ubicaciones de recepción.** esta opción crea de forma automática los puertos y las ubicaciones de recepción del adaptador de SOAP que correspondan a cada archivo .asmx generado. Si ya existe otra ubicación de recepción, no se sustituirá. Ubicaciones de recepción para el adaptador de SOAP se resuelven mediante el formato "/\<*nombre del directorio virtual*\>/\<*namespace_typename_portname de orquestación*  \>.asmx ". Después de seleccionar esta opción, elija la aplicación donde se generarán los puertos y las ubicaciones de recepción.  
  
        > [!NOTE]
        >  La ubicación del proyecto puede producirse en un servidor distinto. Para publicar un servicio Web en un servidor diferente, escriba el nombre del proyecto como  **http://<*servername*>/<*Nombre_proyecto*> **.  
  
        > [!NOTE]
        >  La ubicación del proyecto puede producirse en un sitio Web que no sea predeterminado. Al publicar en un sitio Web no predeterminado, incluya el número de puerto del sitio Web en la dirección URL: http://localhost: 8080 / <*Nombre_proyecto*>.  
  
        > [!NOTE]
        >  Al usar el asistente para crear ubicaciones de recepción, éstas se crean mediante muchos valores predeterminados. Los valores predeterminados para las canalizaciones de envío y recepción son **Microsoft.BizTalk.DefaultPipelines.PassThruReceive** y **Microsoft.BizTalk.DefaultPipelines.PassThruTransmit**. Si los mensajes recibidos a través del servicio Web publicado requieren algún procesamiento de canalización especial (por ejemplo, validación, correlación o asignaciones de entrada/salida), debe establecer el envío y recepción de canalizaciones para  **Microsoft.BizTalk.DefaultPipelines.XMLReceive**, **Microsoft.BizTalk.DefaultPipelines.XMLSend**, o en una canalización personalizada.  
  
10. Haga clic en **siguiente** para revisar la configuración para el proyecto de servicio Web de ASP.NET.  
  
11. Haga clic en **crear** para crear el servicio Web de ASP.NET.  
  
12. Haga clic en **finalizar** para completar el Asistente para publicación de servicios Web de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Publicación de esquemas como un servicio web](../core/publishing-schemas-as-a-web-service.md)