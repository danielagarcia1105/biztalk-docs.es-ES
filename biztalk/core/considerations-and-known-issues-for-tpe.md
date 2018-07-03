---
title: Consideraciones y problemas conocidos del TPE | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, known issues
- planning, Tracking Profile Editor
- Tracking Profile Editor, planning
ms.assetid: e96d85e0-e9ae-434a-b54e-5950f4a2b9c6
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41f728126f14193ad8fc584a94574dab61f7140f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996877"
---
# <a name="considerations-and-known-issues-for-tpe"></a>Consideraciones y problemas conocidos del TPE
Debe tener en cuenta los siguientes problemas a la hora de utilizar perfiles de seguimiento y el TPE.  
  
## <a name="naming-folders-in-the-tpe"></a>Asignar nombres a carpetas en el TPE  
 Tenga en cuenta los siguientes requisitos a la hora de asignar nombres a carpetas en el Editor de perfiles de seguimiento:  
  
-   La longitud total de los valores de nombre de carpeta e instancia de elemento de datos no deberá exceder los 128 caracteres.  
  
-   En el caso de las carpetas Continuación y ContinuationID, el nombre de las carpetas es la clave para correlacionar dos orquestaciones. Por ejemplo, si Orquestación A es la carpeta principal de Orquestación B, Orquestación A contendrá una carpeta de continuación cuyo nombre se asigne directamente a la carpeta ContinuationID de Orquestación B.  
  
## <a name="developing-orchestrations-for-the-tpe"></a>Desarrollar orquestaciones para el TPE  
 No podrá asignar una orquestación a una actividad empresarial si ésta empieza o termina con una forma no válida. El motor de orquestaciones no permite el seguimiento de determinadas formas. Estas sobrecargas son:  
  
- Asignación de mensajes  
  
- Transformación  
  
- Agrupar (Tarea)  
  
- Suspender  
  
- Bucle (While)  
  
- Branch  
  
- Finalizar  
  
- Throw  
  
- Catch  
  
- Forma While  
  
  Tenga en cuenta estas directrices a la hora de asignar actividades empresariales, para que el Editor de perfiles de seguimiento y otras herramientas de BAM puedan utilizarlas:  
  
- Para la forma Agrupar, utilice una forma Ámbito no transaccional.  
  
- En el caso de la forma While, ajústela en una forma Ámbito no transaccional.  
  
- En el caso de las formas Finalizar, no hay un procedimiento alternativo, pues el evento de fin de esta forma nunca se produce en un escenario normal.  
  
- No inicie ni finalice programaciones con ninguna de las formas en las que no estén permitidas las operaciones de arrastrar y colocar.  
  
## <a name="applying-tracking-profiles-that-monitor-running-processes"></a>Aplicar perfiles de seguimiento que controlen procesos en ejecución  
 La actualización de un perfil de seguimiento puede afectar a las instancias de actividad en ejecución si la actividad incluye una continuación de BAM. En concreto, si la actualización del perfil de seguimiento determina una intercepción descendente de datos para un elemento de actividad ya registrado, es posible que se sobrescriba el valor original. Fundamentalmente, una única secuencia de eventos no se verá afectada por la aplicación de las actualizaciones de perfiles de seguimiento, ya que cada objeto de la secuencia está unido a una versión determinada del perfil que ya existía cuando se inició la actividad o secuencia. Sin embargo, ya que las continuaciones son el medio de correlacionar varias secuencias de eventos, las secuencias que todavía no hayan comenzado cuando se actualice el perfil, recogerán los cambios en las actualizaciones, lo que hace que sea posible la mencionada sobrescritura de datos. Para obtener más información acerca de las continuaciones, consulte [continuación de la actividad](../core/activity-continuation.md) y [cómo crear una continuación](../core/how-to-create-a-continuation.md).  
  
## <a name="tracking-profiles-without-a-send-or-receive-shape-from-which-to-draw-message-properties"></a>Perfiles de seguimiento sin una forma Envío o Recepción desde la que dibujar propiedades de mensaje  
 Las continuaciones realizan un seguimiento de actividades mediante propiedades de contexto o datos de carga que coinciden entre actividades. Las propiedades como Id. de mensaje, Id. de servicio e Id. de instancia cambian su valor de una actividad a otra.  
  
 Puede crear perfiles de seguimiento para controlar este escenario utilizando los métodos siguientes:  
  
-   Si una orquestación envía un mensaje a través de un enlace dinámico a otra orquestación, se podrá utilizar un valor de datos de carga exclusivo y global para la continuación.  
  
-   Si no hay datos de carga exclusivos en el mensaje, se podrá utilizar el Id. de intercambio del mensaje. Para utilizar el Id. de intercambio, deberá realizar su seguimiento en la misma forma Recibir. No podrá utilizar el Id. de intercambio si crea un mensaje nuevo, pues el Id. de intercambio cambiará al crear el mensaje nuevo. No es seguro realizar el seguimiento del Id. de intercambio de una forma que no sea Recibir o Enviar.  
  
-   También puede utilizar el Id. de mensaje, siempre que se sea exactamente el mismo mensaje recibido de la canalización el que se utilice en la orquestación; es decir, el puerto de orquestación está vinculado a una canalización, y el seguimiento de la forma Recibir y del Id. de mensaje se efectúa desde dicha ubicación. Si realiza el seguimiento del Id. de mensaje de una forma distinta, el Id. de mensaje no será válido para su uso en las continuaciones.  
  
-   Si una orquestación llama a otra y se pasa ningún mensaje, o una orquestación llama a otra, pero el destinatario no tiene ninguna construcción, recepción, o forma de envío donde se pueden recuperar los valores de datos de carga, el usuario puede utilizar el identificador de instancia. El identificador de instancia para las orquestaciones llamadas no cambia.  
  
-   Si la orquestación carga otra orquestación mediante una llamada de ejecución, en lugar de llamar directamente, no será posible utilizar propiedades de mensaje estáticas para realizar el seguimiento de la actividad. El usuario no puede habilitar una continuación. La única forma de realizar el seguimiento en esta instancia consistiría en pasar un mensaje a través de la canalización que contiene los datos de carga exclusivos en los que efectuar el seguimiento.  
  
## <a name="you-cannot-use-a-session-id-as-a-continuation-token-for-pass-through-pipelines"></a>No podrá usar un Id. de sesión como token de continuación para las canalizaciones de paso a través.  
 En un perfil de seguimiento, cuando se seleccionan elementos de una carga de mensaje, el perfil de seguimiento se enlaza al esquema de dicho mensaje. En una canalización de paso, el valor de nombre de esquema es un valor nulo. Cuando BAM intente cargar la configuración por nombre de puerto y esquema, no encontrará el esquema de Id. de sesión coincidente, y el motor no podrá realizar el seguimiento de datos.  
  
 En canalizaciones de paso, puede eliminar todo el seguimiento de carga del perfil de seguimiento, o bien utilizar canalizaciones XML si, en efecto, necesita realizar el seguimiento de los datos de carga.  
  
## <a name="using-unique-port-names"></a>Usar nombres de puerto únicos  
 Al enumerar puertos bidireccionales, el TPE los muestra como dos puertos lógicos: un puerto de envío y un puerto de recepción. Estos puertos lógicos se muestran con el mismo nombre. BizTalk Server permite crear puertos unidireccionales y bidireccionales con el mismo nombre. Por ejemplo, puede crear un puerto bidireccional denominado "Puerto1" y crear posteriormente un puerto de recepción que tenga el mismo nombre. En estos casos, el TPE muestra el puerto de recepción una vez y el puerto bidireccional dos veces (una vez como puerto de recepción y otra como puerto de envío).  
  
 En este caso, el TPE aplicará perfiles de seguimiento a ambos puertos de recepción. Se recomienda asignar a los puertos un nombre exclusivo para poder identificarlos correctamente.  
  
## <a name="using-tpe-orchestrations-with-a-parallel-shape-as-the-first-shape"></a>Usar orquestaciones del TPE con una forma Paralela como primera forma  
 Si comienza una orquestación con una forma Bifurcar, Paralela o Escuchar, no podrá asignar un Id. de actividad en una de las ramas. En casos de procesamiento paralelo, puede asignar el ActivityID sobre la forma Bifurcar. También puede permitir que BAM genere el Id. de actividad para evitar la emisión de una forma paralela en la parte superior de la orquestación.  
  
> [!IMPORTANT]
>  La asignación de una actividad a más de una ruta, y también la asignación del ActivityID a una ruta de la forma Bifurcar, genera un error cuando el procesamiento sigue la ruta en la que no se ha asignado el ActivityID.  
  
## <a name="availability-of-message-properties-at-design-time"></a>Disponibilidad de las propiedades de mensaje en tiempo de diseño  
 Al crear perfiles de seguimiento, no todas las propiedades de mensajes están disponibles. Esta circunstancia es más probable cuando la forma en la que se asignan las propiedades de mensaje se encuentra en la parte superior de una orquestación. En estas instancias, el valor de las propiedades de mensaje es nulo.  
  
 Por ejemplo, cuando la forma Escuchar es la primera forma de una orquestación. Cuando se asignan las propiedades de mensaje de esta forma, solo las siguientes propiedades tienen valores: InstanceID, ServiceID y ServiceClassID. (MessageID no está en ámbito en este punto, y tiene un valor nulo.)  
  
## <a name="you-cannot-map-shapes-inside-a-loop-shape-to-report-a-milestone"></a>No se pueden asignar formas dentro de una forma Bucle para informar de un hito  
 El TPE bloquea los orígenes de asignación contenidos en una forma Bucle a actividades asignadas a elementos externos del bucle.  
  
 Las actividades en bucle son acciones que se repiten dentro de una orquestación. Existe la posibilidad de capturar los eventos de acciones asociadas en bucle dentro de una orquestación. Para hacerlo, se deberá crear otra actividad y asignar todos los hitos de actividad y datos nuevos del bucle. Este procedimiento es necesario porque el procesamiento de datos del bucle tendrá lugar más de una vez por cada ejecución programada.  
  
 Por ejemplo, si tiene un pedido de compra con varios elementos de línea que se procesan en un bucle, preguntas como "qué pedidos tienen precios de artículos de $100?" son ambiguas. Las preguntas no ambiguas son:  
  
 ¿Qué pedidos tienen elementos de línea con un precio de $100?  
  
 ¿Qué pedidos tienen precios Total/Mín./Máx. de $100?  
  
 La creación de preguntas no ambiguas pasa por concebir los elementos de línea de pedido como elementos independientes del pedido. En el Editor de perfiles de seguimiento, la actividad raíz (por ejemplo, un pedido de compra) se asigna a todas las acciones externas al bucle. La actividad secundaria (por ejemplo, un elemento de línea) se asigna a las acciones internas del bucle.  
  
 El enfoque típico para utilizar con estos tipos de construcciones consiste en descomponer el bucle que se repite y disponer de una actividad relacionada basada en la actividad interna relacionada con la actividad externa.  
  
 Debe utilizar un elemento de carga como ActivityID de la actividad raíz y hacer que dicho elemento de carga esté disponible en algunos de los mensajes dentro del bucle. Asigne la actividad al nodo de relación que se muestra bajo la actividad secundaria, y asígnele el mismo nombre que la actividad raíz.  
  
## <a name="tracking-profiles-spanning-multiple-applications"></a>Perfiles de seguimiento que abarcan varias aplicaciones  
 Si un perfil de seguimiento abarca varias aplicaciones, su implementación debe realizarse tras implementar todas las aplicaciones de la solución. Si el perfil de seguimiento no es el último elemento implementado, recibirá el siguiente mensaje, "**no se encuentra el origen de asignación.**", cuando el Asistente para implementación, llame a BTTDeploy.exe.  
  
## <a name="mapping-multiple-biztalk-server-artifacts-to-a-document-reference-url-or-messageid-nodes"></a>Asignar varios artefactos de BizTalk Server a nodos URL de referencia de documento o MessageID  
 El TPE le permite arrastrar y colocar desde varios artefactos de BizTalk Server hasta el mismo nodo URL de referencia de documento o MessageID.  
  
 En los casos que varios orígenes se asignen al mismo elemento de una actividad de BAM, el último artefacto encontrado durante el procesamiento de BAM será el que se conserve en los datos de seguimiento y pueda verse en el portal de BAM.  
  
## <a name="updating-btt-versions-to-match-biztalk-solution-versions"></a>Actualizar versiones de BTT para adaptarlas a versiones de solución de BizTalk  
 Los programadores y administradores de BAM pueden mantener la sincronización de versiones entre perfiles de seguimiento y soluciones de BizTalk automatizando la actualización del archivo BTT. Para ello, modifique la **versión** atributo en el **DataLevel** elemento del archivo BTT. En el siguiente elemento de ejemplo, se modificaría la información de versión en los atributos TargetAssemblyName y SchemaName.  
  
```  
<DataLevel Name="City" SourceTypeSelected="Messaging Payload" TargetAssemblyName="TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SchemaName="TheImplementationOfOrderMgmt.PurchaseOrder,TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SomXPath="/*[local-name()='<Schema>' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" XPath="/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" IsBeginActivity="true" IsEndActivity="false">  
```  
  
## <a name="some-orchestration-shapes-cannot-be-tracked-in-the-tpe"></a>El TPE no permite realizar el seguimiento de algunas formas de orquestación  
 El motor de orquestaciones no genera eventos para las siguientes formas, por lo que no se pueden realizar tareas de seguimiento ni de asignación para ellas en el TPE:  
  
-   Tarea  
  
-   Todas las ramas  
  
-   Suspender  
  
-   Finalizar  
  
-   Throw  
  
-   Catch  
  
-   MessageAssignment (porque forma parte de la forma Construir)  
  
-   Transformación (porque forma parte de la forma Construir)  
  
-   Bucle  
  
## <a name="tpe-not-retrieving-deployed-tracking-profiles"></a>El TPE no recupera perfiles de seguimiento implementados  
 Tras una actualización o reimplementación, puede tener problemas para recuperar perfiles de seguimiento implementados. Esto puede deberse a que no coincida la forma de almacenarse el nombre del servidor en el que se ejecuta la base de datos BizTalkMgmtDb en el Registro.  
  
 BizTalkMgmtDb se escribe en el Registro durante la configuración de grupos. El TPE usa la entrada para buscar la base de datos de importación principal y filtrar los perfiles de seguimiento.  
  
 Durante la configuración, es posible escribir el nombre de servidor en varios formatos. Por ejemplo:  
  
- mgmtsvr1316267,15001\inst  
  
- MGMTSVR1316267\inst,15001  
  
  El TPE realiza una comparación básica de las cadenas al usar la entrada del Registro. Para recuperar los perfiles de seguimiento implementados es necesario inspeccionar los nombres de servidor y base de datos almacenados y especificarlos en el TPE **establecer base de datos de administración** cuadro de diálogo.  
  
#### <a name="to-determine-the-syntax-for-server-and-database-names-and-enter-it-in-the-biztalk-management-database"></a>Para determinar la sintaxis de los nombres de servidor y base de datos, y especificarlos en la base de datos de administración de BizTalk  
  
1. Abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **Administrador de configuración personalizada**. Para obtener información sobre el uso de la **Administrador de configuración personalizada**, consulte [configurar BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).  
  
2. En el panel de navegación, seleccione **grupo** para abrir la página Configuración del grupo.  
  
3. En el **almacenes de datos** cuadrícula, observar los formatos de la **nombre del servidor** y **nombre de base de datos**.  
  
4. Abra el TPE y seleccione el **herramientas** elemento de menú.  
  
5. Seleccione el **establecer base de datos de administración** elemento de menú para abrir el **establecer base de datos de administración** cuadro de diálogo.  
  
6. En el **SQL Server** texto, escriba el nombre del servidor que se utilizó en el **nombre del servidor** campo de la **almacenes de datos** gridon la **Administrador de configuración personalizada**  página del grupo.  
  
7. En el **nombre de base de datos** texto, escriba el nombre de base de datos que se utilizó en el **nombre de base de datos** campo de la **almacenes de datos** gridon el **configuración personalizada Administrador de** página del grupo.  
  
8. Haga clic en el **Aceptar** botón para guardar las entradas.  
  
## <a name="see-also"></a>Vea también  
 [Uso del TPE](../core/using-the-tpe.md)   
 [Editor de perfiles de seguimiento](../core/tracking-profile-editor.md)