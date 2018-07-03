---
title: Compensación (ejemplo de BizTalk Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- compensations, examples
- examples, compensations
- compensations, orchestrations
ms.assetid: 9d10c7be-6a4c-44cc-bf29-78ecdf147bd1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56675a59714a6fabc1d54fdb594466c7568cfeba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973453"
---
# <a name="compensation-biztalk-server-sample"></a>Compensación (ejemplo de BizTalk Server)
El ejemplo compensación muestra cómo usar el **compensar** forma de una orquestación.  
  
## <a name="what-this-sample-does"></a>Descripción del ejemplo  
 Este ejemplo muestra cómo compensar la transacción que ya se ha confirmado en la orquestación mediante la siguiente secuencia de pasos:  
  
1.  Especifique los datos del cliente en el formulario de InfoPath y envíelos a una orquestación que se haya expuesto como servicio Web.  
  
2.  La orquestación tiene dos acciones paralelas. Una devuelve una confirmación al formulario de InfoPath y la otra actualiza las bases de datos Northwind y BTSCompensationSampleMailingList.  
  
3.  En la segunda acción, la orquestación asigna el mensaje entrante en un formato de mensaje de aplicación de cliente relación management (CRM) y, a continuación, actualiza el **clientes** tabla en la base de datos Northwind. A continuación, se actualiza la tabla Lista de correo de la base de datos BTSCompensationSampleMailingList.  
  
4.  Si alguna de las actualizaciones no se lleva a cabo correctamente, los cambios que se realicen en la base de datos Northwind se compensan llamando a un ensamblado externo para volver a escribir los datos originales del cliente en la base de datos.  
  
## <a name="how-this-sample-is-designed-and-why"></a>Cómo se ha diseñado este ejemplo y por qué  
 Un **ámbito** forma se usa principalmente para la ejecución transaccional y control de excepciones, incluida la compensación. Un ámbito consta de dos bloques. El primer bloque es el bloque de contexto y el segundo bloque puede ser uno o más bloques de compensación o control de excepciones. Esto es similar a la instrucción try-catch del lenguaje de programación .NET. En la orquestación UpdateContact.odx, tienen lugar dos acciones paralelas. En la rama lateral derecha, el bloque try es la **ámbito** forma denominada actualizar sistemas de servidor, que tiene el tipo de una transacción de larga ejecución y un identificador de transacción Upd_Backend. Cuanto más se desciende en el flujo, hay un bloque catch que detecta la excepción general e inicia la compensación.  
  
 Para obtener más información sobre la **ámbito** forma, vea [ámbitos](../core/scopes.md). Consulte también [cómo configurar la forma ámbito](../core/how-to-configure-the-scope-shape.md).  
  
> [!NOTE]
>  La orquestación debe ser una transacción de larga ejecución para establecer el tipo de transacción en atómica o larga ejecución.  
  
 En el bloque try, hay dos ámbitos denominados **actualizar CRM** y **actualizar correo**. Estos dos ámbitos son transacciones atómicas. En el ámbito Actualizar CRM hay bloque try y un bloque de compensación. El bloque try actualiza la base de datos Northwind mediante una llamada de método a un ensamblado externo. En el bloque de compensación tiene lugar la acción de compensación. Cuando se produce una excepción en el ámbito Actualización de sistemas de servidor, el código de la forma Deshacer expresión CRM vuelve a actualizar el registro y lo devuelve a su estado original. Esto desencadena la **compensar** forma en el bloque excepción de filtrado.  
  
> [!NOTE]
>  Las transacciones atómicas garantizan que todas las actualizaciones parciales se revertirán automáticamente si se produce un error durante la actualización de la transacción, y los efectos de la transacción se borrarán (excepto los efectos de cualquier llamada .NET que se haga en la transacción).  
  
> [!NOTE]
>  Una transacción de larga ejecución se considera confirmada cuando se ha completado la última instrucción contenida en ella. No se produce ninguna reversión automática del estado en caso de una anulación de transacción. Estos se puede conseguir mediante la programación de los controladores de excepción y compensación que se muestran en este ejemplo.  
  
 En el bloque catch, hay una **retraso** forma establecida durante diez segundos. Esto retrasa la acción de compensación. También hay un **compensar** forma que inicia la acción de compensación en la transacción Upd_Backend.  
  
 Ocurre lo siguiente cuando la orquestación recibe el mensaje de entrada:  
  
1.  El ensamblado UpdateCrm actualiza una fila de la base de datos Northwind.  
  
2.  El ensamblado UpdateMailingList actualiza un registro coincidente de la base de datos BTSCompensationSampleMailingList.  
  
3.  En caso de que se produzca un error al actualizar la base de datos Northwind, se genera una excepción y la orquestación sale del proceso.  
  
4.  En caso de que se produzca un error durante la actualización de la base de datos BTSCompensationSampleMailingList, se genera una excepción y se produce un retraso de diez segundos antes de volver a escribir los datos originales del cliente en la base de datos Northwind.  
  
## <a name="where-to-find-this-sample"></a>Ubicación del ejemplo  
 \<*Ejemplos de la ruta de acceso*\>\Orchestrations\Compensation\  
  
 En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.  
  
|Archivos|Descripción|  
|---------------|-----------------|  
|Cleanup.bat|Archivo por lotes utilizado para desinstalar el ejemplo.|  
|CompensationOrchestration.btproj|Proyecto de orquestación.|  
|CompensationSample.sln|Solución de ejemplo.|  
|CompensationSampleBinding.xml|Enlazar datos de la orquestación (utilizado durante la instalación).|  
|ContactInfo.xsd|Esquema de mensaje de información de contacto.|  
|ContactInfo.xsx|Archivo de diseño del Diseñador de orquestaciones.|  
|CreateSQLDataStore.sql|Secuencia de comandos SQL para crear y rellenar la base de datos de ejemplo.|  
|CrmSchema.xsd|Esquema de mensaje de actualización de CRM.|  
|MailingListSchema.xsd|Esquema de actualización de mensajes de lista de correo.|  
|RemoveVirDir.vbs|Secuencia de comandos de Microsoft Visual Basic Scripting Edition (VBScript) para eliminar directorios virtuales y físicos de servicio Web (utilizados durante la desinstalación).|  
|Request2Crm.btm|Asignación de mensajes para traducir de una solicitud (información de contacto) al mensaje de actualización de CRM.|  
|Request2MailingList.btm|Asignación de mensajes para traducir de una solicitud (información de contacto) al mensaje de lista de correo.|  
|Setup.bat|Archivo por lotes para instalar este ejemplo.|  
|UpdateContact.odx|Archivo de orquestación.|  
|UpdateRequest2UpdateResponse.btm|Asignación de mensajes para traducir de una solicitud (información de contacto) al mensaje de respuesta.|  
|UpdateResponse.xsd|Esquema de mensajes de respuesta.|  
|InfoPath\Información de contacto Update.xsn|Archivo de Microsoft InfoPath utilizado para enviar formularios al servicio web de la orquestación.|  
|UpdateCrm\AssemblyInfo.cs|Archivo de origen de información del ensambladoUpdateCrm. (El ensamblado UpdateCrm actualiza la base de datos Northwind.)|  
|UpdateCrm\UpdateCrm.cs|Código de origen principal del ensamblado UpdateCrm.|  
|UpdateCrm\UpdateCRM.csproj|Archivo de proyecto UpdateCrm.|  
|UpdateMailingList\AssemblyInfo.cs|Archivo de origen de información del ensamblado UpdateMailingList. (El ensamblado UpdateMailingList actualiza la base de datos de ejemplo.)|  
|UpdateMailingList\UpdateMailingList.cs|Código de origen principal del ensamblado UpdateMailingList.|  
|UpdateMailingList\UpdateMailingList.csproj|Archivo de proyecto UpdateMailingList.|  
  
## <a name="building-and-initializing-this-sample"></a>Crear e inicializar este ejemplo  
  
#### <a name="to-build-and-initialize-the-compensation-sample"></a>Para crear e iniciar el ejemplo Compensación  
  
1. En una ventana de comandos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Orchestrations\Compensation\  
  
2. Ejecute el archivo Setup.bat, que realiza las acciones siguientes:  
  
   -   Generar e implementar el ensamblado de ejemplo.  
  
   -   Cuando se inicie el Asistente para publicación servicios web de BizTalk, realice las siguientes acciones de forma manual:  
  
   1.  En el **éste es el Asistente para publicar servicios Web de BizTalk** página, haga clic en **siguiente**.  
  
   2.  En el **crear servicio Web** página, seleccione **publicar orquestaciones de BizTalk como servicios web**y, a continuación, haga clic en **siguiente**.  
  
   3.  En el **ensamblado de BizTalk** página, busque y seleccione \< *ruta de ejemplos*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll y, a continuación, haga clic en **Siguiente**.  
  
   4.  En el **orquestaciones y puertos** página, haga clic en **siguiente**.  
  
   5.  En el **propiedades del servicio Web** página **espacio de nombres de destino del servicio web**, tipo **http://Microsoft.BizTalk.Samples.Compensation/** y, a continuación, haga clic en **siguiente**.  
  
   6.  En el **proyecto de servicio Web** página **ubicación**, tipo **http://localhost/CompensationOrchestrationWebServiceProxy**.  
  
   7.  Seleccione el **permitir acceso anónimo al servicio web** casilla de verificación.  
  
   8.  Seleccione el **ubicación de recepción de BizTalk crea en la siguiente aplicación** casilla de verificación.  
  
   9. En el **ubicación de recepción de BizTalk crea en la siguiente aplicación** menú desplegable, seleccione **BizTalk Application 1** desde la lista desplegable y, a continuación, haga clic en **siguiente**.  
  
   10. En el **resumen del proyecto de servicio Web** página, haga clic en **crear**.  
  
   11. En el **completar el Asistente para publicar servicios Web de BizTalk** página, haga clic en **finalizar**.  
  
3. El programa de instalación crea y enlaza puertos, crea la base de datos de servidor del ejemplo y agrega ensamblados de C# a la caché de ensamblados global.  
  
   > [!NOTE]
   >  Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.  
  
## <a name="running-this-sample"></a>Ejecución del ejemplo  
 Después de generar e inicializar este ejemplo, tenga en cuenta lo siguiente antes de ejecutarlo:  
  
- Si ejecuta este ejemplo en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], deberá crear un grupo de aplicaciones de IIS y establecer su identidad en una cuenta que sea miembro del grupo de Windows de usuarios de la aplicación BizTalk. También debe actualizar el directorio virtual del servicio de orquestación Web para ejecutarlo dentro de este grupo de aplicaciones.  
  
- Agregue una cuenta ASPNET al grupo de usuarios de hosts aislados de BizTalk.  
  
- Conceder el permiso de db_owner de grupo de usuarios de la aplicación de BizTalk para el **BTSCompensationSampleMailingList** y **Northwind** bases de datos.  
  
- Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no está instalado en la ubicación predeterminada (BizTalk Server de unidad: \Program Files\Microsoft \<versión\>\\), debe publicar el formulario Contact Info Update.xsn antes de usarlo. Para ello, realice lo siguiente:  
  
  #### <a name="to-publish-the-infopath-form"></a>Para publicar el formulario de InfoPath  
  
  1.  En Internet Explorer, en el **herramientas** menú, haga clic en **opciones de Internet**.  
  
  2.  En el **seguridad** , haga clic **Internet**y, a continuación, haga clic en **nivel personalizado**.  
  
  3.  En el **varios** sección, asegúrese de que el **tener acceso a orígenes de datos entre dominios** está habilitada y, a continuación, haga clic en **Aceptar**. Esta configuración es necesaria para que se ejecute el código de las secuencias de comandos de la solución de interfaz de usuario de InfoPath.  
  
  4.  En el Explorador de Windows, vaya a \< *ruta de ejemplos*\>\Orchestrations\Compensation\InfoPath, haga clic en **Contact Info Update.xsn** y, a continuación, haga clic en  **Diseño**.  
  
  5.  La solución de actualización de la información de contacto de InfoPath se abre en modo de diseño.  
  
  6.  En la aplicación de la actualización de información de contacto de InfoPath, en el **archivo** menú, haga clic en **publicar**.  
  
  7.  Aparece el Asistente de publicación.  
  
  8.  Seleccione **a una carpeta compartida en este equipo o en una red** y publicar la solución en la ruta de acceso \< *ruta de ejemplos*\>\Orchestrations\Compensation\InfoPath\Contact Info Update.xsn.  
  
  9. Cierre el modo de diseño de InfoPath.  
  
- Está listo para ejecutar este ejemplo.  
  
  #### <a name="to-run-the-compensation-sample"></a>Para ejecutar el ejemplo Compensación  
  
  1.  Haga doble clic en **Contact Info Update.xsn** para abrirlo en InfoPath.  
  
  2.  Rellene el formulario de una cuenta que exista en las dos bases de datos. Por ejemplo, utilice un Id. de cuenta existente "ALFKI" desde la tabla Northwind Customers.  
  
  3.  En el **archivo** menú, seleccione **enviar**y haga clic en **enviar**.  
  
  4.  El documento de respuesta debe aparecer en el \< *ruta de ejemplos*\>\Orchestrations\Compensation\Out carpeta y Northwind y las bases de datos BTSCompensationSampleMailingList deberían actualizarse con los nuevos datos del formulario de InfoPath.  
  
      > [!NOTE]
      >  Puede desasociar la base de datos BTSCompensationSampleMailingList o ponerla fuera de conexión para probar la acción de compensación que lleva a cabo la orquestación. Tenga en cuenta que el registro se actualiza en la base de datos Northwind en primer lugar. A continuación, cuando la orquestación intenta actualizar la base de datos BTSCompensationSampleMailingList, porque se ha desasociado la base de datos, se produce un error al intentar llevar a cabo la actualización. Por tanto, se genera una excepción y se produce un retraso de diez segundos antes de que se ejecute la acción de compensación para volver a escribir los datos originales del cliente en la base de datos Northwind.  
  
      > [!NOTE]
      >  Es posible que aparezca el mensaje "Error de inicio de sesión del usuario [APPPOOL de IIS\DefaultAppPool]". Esto puede deberse al error de validación en el acceso al servidor basado en autorización token. Para resolver este error, cree un nuevo grupo de aplicaciones y use la cuenta de administrador en él.  
  
## <a name="uninstalling-this-sample"></a>Desinstalar este ejemplo  
  
#### <a name="to-uninstall-the-compensation-sample"></a>Para desinstalar el ejemplo Compensación  
  
1. En una ventana de comandos de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], desplácese a la siguiente carpeta:  
  
    \<*Ejemplos de la ruta de acceso*\>\Orchestrations\Compensation\  
  
2. Ejecute Cleanup.bat.  
  
## <a name="see-also"></a>Vea también  
 [Orquestaciones (carpetas de ejemplos de BizTalk Server)](../core/orchestrations-biztalk-server-samples-folder.md)