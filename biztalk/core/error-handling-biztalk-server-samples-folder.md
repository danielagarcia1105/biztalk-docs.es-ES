---
title: (Carpeta de ejemplos de BizTalk Server) de control de errores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, errors
- errors, examples
- examples, messages
- messages, examples
- messages, errors
ms.assetid: b39791ed-277b-4625-b9a9-72480a1b6ff6
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 386e9729ac32cb08863e2ac3e0699ecda7890dbc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971482"
---
# <a name="error-handling-biztalk-server-samples-folder"></a>Error Handling (carpeta de ejemplos de BizTalk Server)
Este ejemplo tiene como finalidad crear una funcionalidad de control de errores para la aplicación de enrutamiento por contenidos (CBR).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para ejecutar el ejemplo, se recomienda que dispone de Microsoft Office InfoPath 2010 o posterior instalado. Se puede ejecutar el ejemplo sin usar InfoPath pero, en ese caso, no se podrán ver los informes de gastos ni el envío de informes de gastos a través del adaptador de HTTP.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 El ejemplo implementa parte de un sistema de procesamiento de informes de gastos. En concreto, este ejemplo realiza lo siguiente:  
  
1.  Define un esquema de informe de gastos con información sobre un informe de gastos y el enviador individual, incluido el nombre del departamento.  
  
2.  Permite el envío del informe de gastos a través de un directorio o de un servicio Web mediante InfoPath.  
  
3.  Promueve la **departamento** y **correlationID** propiedades en el mensaje de documento para que se puede utilizar en un filtro de puerto para controlar el enrutamiento.  
  
4.  Enruta los informes de gastos del departamento de marketing a un archivo situado en un directorio, que simula la entrega al sistema de servidor del departamento.  
  
5.  Genera un mensaje de error correspondiente a los informes de gastos pertenecientes a otros departamentos distintos del departamento de marketing. El mensaje de error contiene información sobre el error, incluidos el código y la descripción del error.  
  
6.  Enruta los mensajes con errores a un destinatario físico (un usuario empresarial o un operador de la aplicación) para su corrección y reenvío.  
  
7.  Enruta los informes de gastos reenviados por departamento, según se ha explicado anteriormente.  
  
 Gran parte de este trabajo se lleva a cabo mediante una programación de orquestación de BizTalk.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 El diseño se basa en las canalizaciones XML de envío y recepción predeterminadas, la promoción de propiedades, los filtros de suscripción y las programaciones de orquestación en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para enrutar mensajes. Los elementos de diseño y su justificación se enumeran en la tabla siguiente.  
  
|Elemento de diseño|Razones seleccionadas|  
|--------------------|--------------------------|  
|Canalización de recepción XML predeterminada|-La canalización XMLReceive admite la promoción de propiedad; la canalización PassThruReceive no.<br />-El mensaje entrante está en formato XML y no necesita procesamiento más allá de desensamblado básico y la resolución de entidades.|  
|Enrutamiento para mensajes con errores|-Receive puertos suspender mensajes con errores y generar una confirmación negativa de forma predeterminada. Cuando el enrutamiento está activado, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] intenta enrutar los mensajes que no se pueden procesar hacia una aplicación suscriptora (por ejemplo, otro puerto de recepción o una programación de orquestación).|  
|Promoción de propiedades|-BizTalk Server depende de los campos de propiedades para efectuar el enrutamiento. Los campos distintivos los utilizan las orquestaciones y no se pueden usar para enrutamiento.|  
|Filtro de suscripción|-El filtro de suscripción realiza el enrutamiento mediante la captura de mensajes que cumplen uno o varios criterios basados en campos de propiedades.|  
|Programación de orquestación de BizTalk|: Proporciona la oportunidad de agregar información a los mensajes con errores.<br />-Habilita el enrutamiento de mensajes con errores a una ubicación dedicada para la intervención humana.<br />-Procesos informes de gastos reenviados.|  
|XMLTransmit|-Realiza el ensamblado básico de los mensajes XML salientes. La canalización PassThruTransmit no ofrece compatibilidad adicional.|  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 En este ejemplo se encuentra en <`Samples Path>`\Messaging\ErrorHandling\\.  
  
 La siguiente tabla contiene una lista de archivos para este ejemplo.  
  
|Archivo|Description|  
|----------|-----------------|  
|Cleanup.bat|Se utiliza para anular la implementación de ensamblados y quitarlos de la caché de ensamblados global.<br /><br /> Quita los puertos de envío y recepción.<br /><br /> Quita los directorios virtuales de Internet Information Services (IIS) según sea necesario.|  
|ErrorHandling.sln|Archivo de solución de Visual Studio para el ejemplo.|  
|ErrorHandlingBinding.xml|Archivo de enlace para el ejemplo.|  
|Setup.bat|Se utiliza para crear e iniciar este ejemplo.|  
|Expense Report – John Doe.xml|Ejemplo del documento de informe de gastos de InfoPath.|  
|Invalid Expense Report – John Doe.xml|Ejemplo del documento de informe de gastos de InfoPath con datos no válidos.|  
|En la carpeta ErrorHandler:<br /><br /> ErrorHandler.btproj|Proyecto de BizTalk para la orquestación.|  
|En la carpeta ErrorHandler:<br /><br /> ResubmitLogic.odx|Orquestación que se suscribe a los mensajes con errores, los envía al destinatario físico para su corrección y, a continuación, vuelve a enviar los mensajes corregidos al servidor para su enrutamiento.|  
|En la carpeta ErrorHandler:<br /><br /> SuspendMessage.odx|Orquestación usada para suspender mensajes que no se pueden procesar en la orquestación de control de errores.|  
|En la carpeta InfoPathForms:<br /><br /> Expense Report.xsn<br /><br /> Expense Report - Resubmit.xsn|Formulario de InfoPath correspondiente al informe de gastos y formulario utilizado para ver y reenviar los mensajes con errores.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> ExpenseReportSchema.xsd|Esquema XML para el documento de informe de gastos.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> PipelinesAndSchemas.btproj|Proyecto de BizTalk para el ejemplo.|  
|En la carpeta PipelinesAndSchemas:<br /><br /> PropertySchema.xsd|Esquema de propiedad del ejemplo.|  
  
## <a name="how-to-use-this-sample"></a>Uso del ejemplo  
 Este ejemplo proporciona un punto de partida para crear un procedimiento de control de errores propio.  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-compose-sample"></a>Para crear e inicializar el ejemplo de composición  
  
1.  En una ventana de comandos, desplácese a la siguiente carpeta:  
  
     <`Samples Path`>**\Messaging\ErrorHandling**  
  
2.  Ejecutar **Setup.bat**, que realiza las siguientes acciones:  
  
    -   Crea tres carpetas: **ExpenseReportIn**, **ExpenseReportOut**, y **ResubmittedReportIn** en la ruta siguiente:  
  
         <`Samples Path`>**\Messaging\ErrorHandling**  
  
    -   Copia y publica los formularios de InfoPath **Expense Report.xsn** y **Expense Report – Resubmit.xsn** en la carpeta **C:\Temp\InfoPathForms**.  
  
    -   Compila los proyectos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo.  
  
    -   Crea un directorio virtual denominado **ExpenseReports**.  
  
    -   Crea una nueva aplicación de BizTalk denominada **Error Handling Sample** e implementa los ensamblados de ejemplo en ella.  
  
    -   Crea y enlaza las ubicaciones de recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], así como los puertos de envío y recepción.  
  
    -   Da de alta e inicia orquestaciones, habilita las ubicaciones de recepción e inicia los puertos de envío.  
  
         Si opta por abrir y crear los proyectos de este ejemplo sin ejecutar Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la utilidad de nombre seguro de .NET Framework (sn.exe). Utilice este par de claves para firmar los ensamblados de ejemplo.  
  
3.  Antes de intentar ejecutar este ejemplo, confirme que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha notificado ningún error durante el proceso de compilación o inicialización.  
  
    > [!NOTE]
    >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.  
  
4.  Si usa Internet Information Services (IIS) 7,0, deberá llevar a cabo más pasos de configuración para ajustar la definición del directorio virtual que corresponde a la ubicación de recepción HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que usa el ejemplo. Para configurar IIS, lleve a cabo lo siguiente:  
  
    1.  Mediante el administrador de IIS 7.0, cree un nuevo grupo de aplicaciones para el grupo Usuarios de hosts aislados de BizTalk.  
  
    2.  Configure el grupo de aplicaciones para que se ejecute bajo la identidad del usuario de hosts aislados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. (También puede saltarse este paso si ya ha configurado un grupo de aplicaciones para otras ubicaciones de recepción de HTTP de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)  
  
    3.  Configure el directorio virtual **ExpenseReport** para usar la recepción HTTP de grupo de aplicaciones creado en el paso anterior.  
  
     Si todavía no dispone de una extensión de servidor Web para la extensión ISAPI BTSHTTPReceive.dll, créela y habilítela estableciendo su estado como permitido. Puede hacerlo en IIS 7.0 mediante la consola de administración de IIS (bien directamente en **herramientas administrativas** o mediante la consola de administración de equipos) como se indica a continuación:  
  
    1.  Expanda el **Administrador de Internet Information Services** árbol.  
  
    2.  Haga clic en el **extensiones de servicio Web** carpeta.  
  
    3.  En el panel derecho de la consola de administración, haga clic en **agregar una nueva extensión de servicio Web**.  
  
    4.  En el **nueva extensión de servicio Web** cuadro de diálogo, haga clic en **agregar**.  
  
    5.  En el **Agregar archivo** cuadro de diálogo, haga clic en **examinar** para seleccionar el archivo <`BizTalkInstallPath>`**\HttpReceive\BTSHTTPReceive.dll**y, a continuación, haga clic en **Aceptar**.  
  
    6.  Configure el directorio virtual **ExpenseReport** usar ruta de acceso local [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]HTTPReceive  
  
     Para obtener más información, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  
 Antes de ejecutar el ejemplo con el informe de gastos correcto, use el procedimiento siguiente para verificar que el ejemplo "sin errores" funciona correctamente.  
  
#### <a name="to-verify-that-the-no-errors-case-sample-works-correctly"></a>Para verificar que el ejemplo "sin errores" funciona correctamente  
  
1.  Abra el formulario de InfoPath **Expense Report - John Doe.xml**. Mire el **departamento** campo dentro del formulario. Este campo debe estar establecido como "Marketing".  
  
2.  En la esquina superior izquierda de la ventana de InfoPath, haga clic en **enviar** o haga clic en **volver a enviar el informe de gastos**. Espere a que aparezca una ventana de confirmación que indique que el informe de gastos se ha enviado correctamente.  
  
     -OR-  
  
     Copie y pegue este archivo en el **ExpenseReportIn** carpeta.  
  
3.  Debería ver un nuevo archivo colocado en el **ExpenseReportOut** carpeta. Este archivo es el mismo formulario de informe de gastos que se ha enviado en los pasos anteriores.  
  
 Después de confirmar el funcionamiento del ejemplo "sin errores", use el procedimiento siguiente para ejecutar el ejemplo con un informe de gastos incorrecto con el fin de desencadenar la funcionalidad de control de errores.  
  
#### <a name="to-trigger-error-handling"></a>Para desencadenar el control de errores  
  
1.  Abra el formulario de InfoPath **Invalid Expense Report - John Doe.xml**. Mire el **departamento** campo dentro del formulario. Este campo está establecido con un valor no válido.  
  
2.  En la esquina superior izquierda de la ventana de InfoPath, haga clic en **enviar**. Espere a que aparezca una ventana de confirmación que indique que el informe de gastos se ha enviado correctamente.  
  
     -OR-  
  
     Copie y pegue este archivo en el **ExpenseReportIn** carpeta.  
  
3.  Debería ver un nuevo archivo denominado **ErrorReport_\<***fecha*_*tiempo***\>.xml** coloca en el  **ExpenseReportOut** carpeta.  
  
     Abra el archivo y observe que se trata del informe de gastos enviado en el paso anterior, pero con la información de errores agregada al principio.  
  
4.  Sustituya el valor incorrecto del departamento por "Marketing" y, a continuación, haga clic en **enviar** en la esquina superior izquierda de la ventana de InfoPath.  
  
     -OR-  
  
     Copie y pegue este archivo en el **ResubmittedReportIn** carpeta.  
  
5.  Debería ver un nuevo archivo creado en el **ExpenseReportOut** carpeta. Este archivo es el informe de gastos corregido que se ha enviado al servidor.  
  
## <a name="see-also"></a>Vea también  
 [Usar el enrutamiento de mensajes con errores](../core/using-failed-message-routing.md)   
 [Messaging (carpeta de ejemplos de BizTalk Server)](../core/messaging-biztalk-server-samples-folder.md)