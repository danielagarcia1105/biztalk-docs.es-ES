---
title: "Configurar el puerto de envío de SharePoint Services | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36aadbc2-316f-4e1c-a5a8-b162470acf9e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f424d3ad1b38316802585aefca0a49bf2f67f0a2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="configure-sharepoint-services-send-port"></a>Configurar un puerto de envío de SharePoint Services
En este tema, se compara un puerto de envío estático con un puerto de envío dinámico y también se incluyen los pasos para crear un puerto de envío [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)]. Concretamente:  
  
 [Puerto de envío estático frente a puerto de envío dinámico](../core/configure-sharepoint-services-send-port.md#BKMK_StaticvsDynamic)  
  
 [Crear un puerto de envío estático](../core/configure-sharepoint-services-send-port.md#BKMK_StaticSend)  
  
 [Crear un puerto de envío dinámico](../core/configure-sharepoint-services-send-port.md#BKMK_DynamicSend)  
  
##  <a name="BKMK_StaticvsDynamic"></a>Puerto de envío estático frente a puerto de envío dinámico  
  
||Puerto de envío estático|Puerto de envío dinámico|  
|-|----------------------|-----------------------|  
|Use un puerto de envío individual con diferentes adaptadores.|no<br /><br /> Al crear un puerto de envío estático, es necesario el tipo de transporte.|Sí<br /><br /> Normalmente, se agrega un puerto de envío dinámico a una orquestación. El tipo de transporte se configura en la lógica de la orquestación.|  
|Use un puerto de envío individual con diferentes propiedades como, por ejemplo, la URL.|no<br /><br /> Al crear un puerto de envío estático, se deben configurar algunas propiedades de adaptador como la URL.|Sí<br /><br /> Normalmente, se agrega un puerto de envío dinámico a una orquestación. Las propiedades se configuran en la lógica de la orquestación.|  
|Debe usar el controlador de envío predeterminado.|no<br /><br /> El controlador de envío se puede configurar al crear un puerto de envío.|no<br /><br /> El controlador de envío se puede configurar al crear un puerto de envío.|  
|Úselo cuando no sepa dónde debería ir el mensaje.|no<br /><br /> Al crear un puerto de envío estático, se especifica el tipo de transporte y la ubicación de llegada.|Sí<br /><br /> La ubicación de llegada se puede configurar en una orquestación y en un escenario de enrutamiento por contenidos. Las reglas también se pueden usar para filtrar dónde se envía el mensaje.|  
|Use un puerto de envío individual para enviar mensajes a varios socios.|no<br /><br /> Al crear un puerto de envío estático, se especifica el tipo de transporte y la ubicación de llegada.|Sí<br /><br /> Normalmente, se agrega un puerto de envío dinámico a una orquestación. Las propiedades se configuran en la lógica de la orquestación y se basan en reglas que el usuario especifica; los mensajes se pueden enviar a varios socios.|  
  
##  <a name="BKMK_StaticSend"></a>Crear un puerto de envío estático  
 Al crear un puerto de envío estático, este usa el controlador de envío predeterminado asociado al tipo de transporte. Cuando se usa el [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adaptador, el controlador de envío predeterminado es **BizTalkServerApplication**. Para que conocer los pasos agregar un nuevo controlador de envío, vaya a [cómo crear un controlador de adaptador](http://go.microsoft.com/fwlink/p/?LinkId=263646).  
  
 Cree el puerto de envío estático:  
  
1.  En el **administración de BizTalk Server** de la consola, expanda **grupo de BizTalk [*GroupName*]**, expanda **aplicaciones**y, a continuación, expanda la aplicación que contendrá el puerto de envío.  
  
2.  Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
    > [!IMPORTANT]
    >  A **puerto de envío de petición-respuesta estático** no es configurable con el [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adaptador.  
  
3.  En **propiedades**, haga clic en **Windows SharePoint Services** en el **tipo** lista desplegable. Escriba el **nombre**, **controlador de envío**, y **canalización de envío** propiedades.  
  
4.  Haga clic en **configurar**. En **propiedades**, configure lo siguiente:  
  
    |||  
    |-|-|  
    |Puerto del servicio Web del adaptador|**Requiere**. Puerto configurado en el sitio web de IIS que hospeda el servicio web de adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].<br /><br /> Puerto predeterminado es **80**, que es el puerto HTTP estándar. Actualice este valor si utiliza un puerto distinto del 80.|  
    |Timeout|**Requiere**. En milisegundos, este valor determina el tiempo transcurrido cuando el adaptador recibe una respuesta del servicio web.<br /><br /> Valor predeterminado es **100000 ms** (100 segundos).<br /><br /> Aumente este valor si el tamaño del lote o el mensaje es mayor de lo esperado.<br /><br /> Tiempo de espera, en milisegundos, de las llamadas del servicio Web de tiempo de ejecución del adaptador que se realizan al servicio Web del adaptador de Windows SharePoint Services. Puede que tenga que aumentar este valor si el tamaño del mensaje o del lote es mayor que el promedio que espera el adaptador.|  
    |Utilizar modelo de objetos del cliente|**Requiere**. Determina si se utiliza el modelo de objetos del cliente de SharePoint (CSOM) o el modelo de objetos del servicio (SSOM).<br /><br /> Valor predeterminado es **Sí**. Establecido en **Sí** para utilizar el CSOM de SharePoint en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. No hay ningún requisito para el equipo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].<br /><br /> Establecido en **No** utilizar el SSOM de SharePoint que incluye el servicio web instalado en el [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] equipo.<br /><br /> [Apéndice B: instalar el adaptador de SharePoint de Microsoft](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) proporciona información específica acerca de los componentes SSOM y CSOM utilizados por el [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adaptador.|  
    |Dirección URL de carpeta de destino|**Requiere**. La URL de carpeta de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] para almacenar documentos. Escriba una ruta de acceso relativa al sitio de SharePoint. Por ejemplo, **documentos compartidos** o **pedidos de compra/documentos compartidos /**. También se puede usar una lista como destino. Por ejemplo, **listas/tareas**. Si especifica una lista, el cuerpo del mensaje no se guarda con el elemento de lista. Los valores extraídos del mensaje se promueven en las columnas de SharePoint. **Nota:** la URL de carpeta o biblioteca de documentos de SharePoint puede ser diferente de su nombre. Compruebe la dirección en el explorador web para obtener la dirección URL correcta.|  
    |Nombre de archivo|**Opcional**. Escriba el nombre de archivo de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)].<br /><br /> Escriba un nombre de archivo, como **Pedido0001.XML** o una expresión. Las expresiones incluyen cualquier combinación de valores literales, macros y consultas XPATH. Por ejemplo, escriba **PurchOrd-%XPATH=//po:PurchaseOrderId%-%MessageID%.xml**. Cuando no se proporciona un nombre, se usa el nombre de archivo del archivo original, el valor proporcionado por la orquestación o 'Msg-%MessageID%.xml'. Vea [expresiones del adaptador de Windows SharePoint Services](../core/windows-sharepoint-services-adapter-expressions.md) para obtener más información. **Nota:** al enviar mensajes a una lista, este valor de nombre de archivo se omiten y no se guarda en una columna de SharePoint. En su lugar actualice la columna 'Título' con alguna de las 16 columnas disponibles. Las listas de SharePoint no tienen una columna Nombre de archivo.|  
    |Alias de espacios de nombres|**Opcional**. Lista separada por comas o punto y coma de definiciones de alias de espacios de nombres.<br /><br /> Use este campo para definir los alias de espacios de nombres que usan las consultas XPATH introducidas en los campos como 'Nombre de archivo' o 'Valor de columna'. Por ejemplo, escriba **po = 'http://OrderProcess/POrder', conf = 'http://OrderProcess/Confirmation' xmlns = ""; ipsol = '{D8217CF1-4EF7-4bb5-A30D-765ECB09E0D9}'**. **Nota:** esta propiedad no anula el WSS. Propiedad de contexto de mensaje de ConfigNamespacesAliases definido por la orquestación. En lugar de eso, se combinan los dos valores.|  
    |Sobrescribir|**Requiere**. Si existe un archivo, determina si el archivo se sobrescribe.<br /><br /> Valor predeterminado es **No**. Las opciones son:<br /><br /> -   **Ya no**: genera un error y suspende el mensaje si existe un archivo con el mismo nombre.<br />-   **Orquestación**: usa el valor definido en la orquestación si existe un archivo con el mismo nombre.<br />-   **Cambiar el nombre de**: cambia el nombre del nuevo archivo si existe un archivo con el mismo nombre.<br />-   **Sí**: sobrescribe un archivo existente si tiene el mismo nombre.<br />     Cuando se establece en **Sí**, envíe un gran número de mensajes con el mismo nombre puede dar lugar a errores de Visor de eventos de SharePoint. Estos errores no influyen en el adaptador y se volverán a intentar los mensajes que no se envíen correctamente.|  
    |Dirección URL del sitio de SharePoint|**Requiere**. Dirección URL completa del sitio web de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]. Por ejemplo, http://*SharePointServer*  /sites/TestSite. **Nota:** ubicación de recepción o puerto de envío de un URI no puede superar los 256 caracteres.|  
    |Integración con Microsoft Office|**Requiere**. Para mensajes binarios, debe usar **No** o **opcional**.<br /><br /> Valor predeterminado es **opcional**. Las opciones son:<br /><br /> <ul><li>**Ya no**: guarda el documento **como-es**. Puede usar esta opción para los mensajes binarios.</li><li>**Opcional**: modifica el documento de manera que se abre automáticamente en una aplicación de Office, como InfoPath. Si no se encuentran las instrucciones de procesamiento, se procesa el documento **como-es**. Puede usar esta opción para los mensajes binarios.</li><li>**Orquestación**: usa el valor definido en la orquestación.</li><li>**Sí**: modifica el documento de manera que se abre automáticamente en una aplicación de Office, como InfoPath. Si no se encuentran las instrucciones de procesamiento, el mensaje se suspende.<br /><br />     Cuando se establece en **Sí**, se requiere al menos uno de los siguientes pares de propiedad:<br /><br /> <ul><li>*Biblioteca de documentos de plantillas de* y *plantillas Namespace columna*</li><li>*Biblioteca de documentos de reserva de plantillas* y *columna Namespace reserva de plantillas*</li></ul></li><li>**Sí (biblioteca de formularios de InfoPath)**: si una solución de InfoPath reside en la biblioteca de formularios, el documento se modifica para evitar que se abre automáticamente en una aplicación de Office, como InfoPath. Si la Biblioteca de documentos no tiene una solución, el mensaje se suspende.</li></ul>|  
    |Biblioteca de documentos de plantillas|**Requiere *sólo* cuando *plantillas Namespace columna* se rellena**. La biblioteca de documentos de SharePoint que almacena las soluciones de InfoPath. Por ejemplo, **soluciones mi**. El adaptador busca en el *biblioteca de documentos de plantillas de* una solución de InfoPath coincidente. Si no se encuentra una solución, el adaptador busca en el *biblioteca de documentos de reserva de plantillas*. **Nota:** el *biblioteca de documentos de plantillas* requiere al menos una columna de SharePoint 'Una línea de texto' rellenada con lo siguiente: <ul><li>El espacio de nombres y el nodo raíz de los documentos XML que se abren con la solución de InfoPath</li><li>O bien, el nodo raíz del documento XML</li></ul> Para obtener más información, consulte [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md).|  
    |Biblioteca de documentos de reserva de plantillas|**Requiere *sólo* cuando *columna Namespace de reserva de plantillas* se rellena**. La biblioteca de documentos de SharePoint que almacena las soluciones de InfoPath. Por ejemplo, **plantillas**.<br /><br /> Si una solución no se encuentra en la *biblioteca de documentos de plantillas de*, el adaptador busca en *biblioteca de documentos de reserva de plantillas* una solución de InfoPath coincidente. El *biblioteca de documentos de reserva de plantillas* y *biblioteca de documentos de plantillas* campos se pueden usar con dos conjuntos de soluciones de InfoPath. Hay soluciones de InfoPath genéricas que funcionan para todos los fines y soluciones de InfoPath especializadas que se usan únicamente para un socio concreto. El *biblioteca de documentos de reserva de plantillas* campo debe apuntar a las soluciones genéricas y el *biblioteca de documentos de plantillas* debe apuntar a las soluciones especializadas para ese socio concreto. **Nota:***biblioteca de documentos de reserva de plantillas* requiere al menos una columna de SharePoint 'Una línea de texto' rellenada con lo siguiente: <ul><li>El espacio de nombres y el nodo raíz de los documentos XML que se abren con la solución de InfoPath</li><li>O bien, el nodo raíz del documento XML</li></ul> Para obtener más información, consulte [Tutorial: módulo 2: integrar Office con el adaptador de Windows SharePoint Services](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md).|  
    |Columna de espacio de nombres de reserva de plantillas|**Requiere *sólo* cuando *biblioteca de documentos de reserva de plantillas* se rellena**. La biblioteca de documentos de SharePoint que almacena el espacio de nombres de las soluciones de InfoPath. Por ejemplo, **myNamespace**. **Nota:** este campo distingue mayúsculas de minúsculas.|  
    |Columna de espacio de nombres de plantillas|**Requiere *sólo* cuando *biblioteca de documentos de plantillas de* se rellena**. SharePoint *biblioteca de documentos de plantillas de* una columna que almacena el espacio de nombres de la solución de InfoPath. Por ejemplo, **myNamespace**. **Nota:** este campo distingue mayúsculas de minúsculas.|  
    |Contraseña de SharePoint Online|**Opcional**. Contraseña de la cuenta de SharePoint Online.|  
    |Nombre de usuario de SharePoint Online|**Opcional**. Nombre de usuario de la cuenta de SharePoint Online.|  
    |Columna `n`|**Opcional**. La columna de SharePoint que existe en el *biblioteca de documentos de destino*. Actualizar esta columna con el valor extraído del mensaje o especificado en el *valor de la columna* campo. **Nota:** se puede especificar hasta 16 columnas. Este campo distingue mayúsculas de minúsculas.|  
    |Columna `n` Valor|**Opcional**. Escriba el valor de columna que se establecerá para este mensaje. Puede escribir un valor literal como 'Pedido' o una expresión. Las expresiones pueden incluir cualquier combinación de valores literales, macros y consultas XPATH. Por ejemplo, escriba **"% XPATH=//po:POAmount%" "% SendingOrchestrationID %"**. **Nota:** se puede especificar hasta 16 columnas.|  
  
5.  Haga clic en **Aceptar** guardar la configuración.  
  
6.  Entre las opciones de configuración adicionales del puerto de envío se incluyen:  
  
    1.  [Cómo configurar opciones avanzadas de transporte para un puerto de envío](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
    2.  [Cómo configurar opciones de copia de seguridad de transporte para un puerto de envío](../core/how-to-configure-backup-transport-options-for-a-send-port.md)  
  
    3.  [Cómo configurar asignaciones de salida para un puerto de envío](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
    4.  [Cómo configurar filtros para un puerto de envío](../core/how-to-configure-filters-for-a-send-port.md)  
  
    5.  [Cómo asignar un certificado a un puerto de envío](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
    6.  [Cómo configurar el seguimiento de un puerto de envío](../core/how-to-configure-tracking-for-a-send-port.md)  
  
##  <a name="BKMK_DynamicSend"></a>Crear un puerto de envío dinámico  
 Al crear un puerto de envío dinámico, el controlador de envío se puede configurar para cada adaptador. Varios adaptadores pueden usar un puerto de envío dinámico individual. Vea [controlador de puerto de envío dinámico es Configurable](../core/dynamic-send-port-handler-is-configurable.md) para conocer los pasos configurar el controlador de puerto de envío dinámico.  
  
1.  En el **administración de BizTalk Server** de la consola, expanda **grupo de BizTalk [*GroupName*]**, expanda **aplicaciones**y, a continuación, expanda la aplicación que contendrá el puerto de envío.  
  
2.  Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, elija **puerto de envío unidireccional dinámico** o **puerto de envío de petición-respuesta dinámico**  
  
3.  En **propiedades**, escriba la **nombre** y **canalización** propiedades  
  
     Haga clic en **configurar**.  
  
4.  En el **Configurar controlador de envío** ventana, elija la **controlador de envío** para los adaptadores individuales. El valor predeterminado es el controlador de envío **BizTalkServerApplication**. Para que conocer los pasos agregar un nuevo controlador de envío, vaya a [cómo crear un controlador de adaptador](http://go.microsoft.com/fwlink/p/?LinkId=263646).  
  
     Hay muchos motivos para usar hosts independientes, que incluyen:  
  
    -   **Requisitos de 32 bits**: algunos adaptadores requieren un host de 32 bits, al igual que los adaptadores de FTP y POP3. Puede agrupar todos los adaptadores de 32 bits individual o conjuntamente en su propio host.  
  
         [Compatibilidad de BizTalk Server con 64 bits](../core/biztalk-server-64-bit-support2.md)  
  
    -   **Host por propósito**: crear un host para el envío, un host de recepción, un host para las orquestaciones de procesamiento y un host para el seguimiento.  
  
    -   **Distintas configuraciones de host**: muchas configuraciones se implementan en el nivel de host. En consecuencia, se pueden configurar diferentes parámetros de limitación para cada host. Por ejemplo, se puede deshabilitar la limitación del HostA. Realizar un seguimiento de los eventos del HostB. Modificar la configuración de .NET CLR del HostC. Aumentar el uso de memoria del HostD.  
  
    -   **Seguridad**: la seguridad se implementa en el nivel de host. Cada host se ejecuta bajo su propia cuenta de Windows. Por ejemplo, el HostA usa el adaptador de archivo para tener acceso al recurso compartido de archivos. Conceda a la cuenta de usuario del HostA permisos para el recurso compartido de archivos. El HostB usa un servicio web hospedado en un servidor de IIS. Conceda a la cuenta de usuario del HostB autorización para el servicio web. De este modo, también se evita que otras cuentas de host tengan acceso a entidades a las que no necesitan tener acceso.  
  
    -   **Distintos adaptadores**: por ejemplo, si tiene varios artefactos (ubicación de recepción y puertos de envío) con el adaptador de HTTP. Desea que todo esté asociado con el adaptador HTTP en su propio host.  
  
    -   **Orquestaciones independientes**: orquestaciones individuales pueden estar en su propio host. Por ejemplo, si una orquestación usa mucha memoria o una CPU elevada, coloque dicha orquestación en su propio host.  
  
     [Guía de optimización de rendimiento de BizTalk Server](http://msdn.microsoft.com/library/dn775063\(v=bts.10\).aspx) y [cómo mantener y solucionar problemas de las bases de datos de BizTalk Server](http://support.microsoft.com/kb/952555) proporcionan sugerencias de rendimiento.  
  
5.  Haga clic en **Aceptar** guardar la configuración.  
  
6.  Entre las opciones de configuración adicionales del puerto de envío se incluyen:  
  
    1.  [Cómo configurar opciones avanzadas de transporte para un puerto de envío](../core/how-to-configure-transport-advanced-options-for-a-send-port.md)  
  
    2.  [Cómo configurar asignaciones de salida para un puerto de envío](../core/how-to-configure-outbound-maps-for-a-send-port.md)  
  
    3.  [Cómo configurar filtros para un puerto de envío](../core/how-to-configure-filters-for-a-send-port.md)  
  
    4.  [Cómo asignar un certificado a un puerto de envío](../core/how-to-assign-a-certificate-to-a-send-port.md)  
  
    5.  [Cómo configurar el seguimiento de un puerto de envío](../core/how-to-configure-tracking-for-a-send-port.md)  
  
7.  Haga clic en **Aceptar** guardar la configuración.  
  
 Temas adicionales sobre el puerto de envío:  
  
 [Creación y configuración de puertos de envío](../core/creating-and-configuring-send-ports.md)  
  
 [Creación y configuración de grupos de puertos de envío](../core/creating-and-configuring-send-port-groups.md)  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de adaptador de SharePoint Services](../core/troubleshooting-sharepoint-services-adapter.md)   
 [Configurar SharePoint servicios de ubicación de recepción](../core/configure-sharepoint-services-receive-location.md)   
 [CSOM: Adaptador de SharePoint Services](../core/csom-sharepoint-services-adapter.md)