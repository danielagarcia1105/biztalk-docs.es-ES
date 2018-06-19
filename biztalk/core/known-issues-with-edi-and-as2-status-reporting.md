---
title: Problemas conocidos con EDI y AS2 informes de estado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d755dca-a4b6-44be-bc45-88c0b17685a0
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 691a10671c4c8ff5f2ff77065455c100784ddd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008277"
---
# <a name="known-issues-with-edi-and-as2-status-reporting"></a>Problemas conocidos de los informes de estado de EDI y AS2
En este tema se describe problemas conocidos con estado de EDI en BizTalk Server.  
  
## <a name="batch-status-reporting-data-may-not-be-updated-if-the-batch-orchestration-is-stopped-outside-of-the-partner-agreement-manager"></a>Puede que no se actualicen los datos de registro de estado del lote si la orquestación de lotes se detiene fuera del Administrador de acuerdos de socios comerciales.  
 Una instancia de orquestación de lotes puede desactivarse a través de la página Lotes del cuadro de diálogo Propiedades de EDI para una entidad. Si desactiva una instancia de orquestación de esa forma, el servidor BizTalk Server actualizará los datos de informe de estado para ese lote. Sin embargo, si detiene la orquestación de lotes de otra forma, por ejemplo, si detiene la orquestación de una de las páginas de consulta en la página Información general de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede que no se actualicen los datos de informe de estado y tenga que terminar con un informe de estado que no esté actualizado. Por ejemplo, el informe de estado puede indicar que el lote está aún activo aunque se haya desactivado la instancia de orquestación de lote.  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-edi-status-reporting-has-been-enabled"></a>El servicio de BizTalk necesita reiniciarse después de que se haya habilitado el informe de estado de EDI.  
 **Síntoma**  
  
 Se ha activado el informe de estado de EDI pero los informes no se generan.  
  
 **Causa posible**  
  
 El servicio de BizTalk necesita reiniciarse después de que se haya activado o desactivado el informe de estado de EDI para que se aplique el cambio. Si se está utilizando la canalización AS2EdiReceive o AS2EdiSend en la solución, el servicio de BizTalk y el servicio IIS deben reiniciarse para que se aplique el cambio.  
  
 **Resolución**  
  
 Reinicie el servicio BizTalk (en el cuadro de diálogo Administración de equipos). Si se utiliza la canalización AS2EdiReceive o la canalización AS2EdiSend en la solución, reinicie el servicio de administración de IIS (mediante la *iisreset* comando), así como.  
  
> [!NOTE]
>  No es necesario reiniciar el servicio de BizTalk o el del administrador de IIS si habilita el informe de estado de AS2.  
  
## <a name="the-status-report-will-display-9999-for-the-year-when-the-as2-message-date-time-in-the-message-is-a-null-value"></a>El informe de estado mostrará “9999” para el año en el que la fecha y hora del mensaje AS2 sea un valor nulo.  
 Si el campo de la hora y fecha del mensaje AS2 en un mensaje AS2 entrante está configurado como Nulo, un valor de “9999” se mostrará para el año en el campo de fecha y hora del mensaje AS2 para ese mensaje en el informe de estado de AS2.  
  
 Si el campo de la hora y fecha del mensaje AS2 en un mensaje AS2 entrante no puede analizarse (como Mon, 21 May 2007 10:08:28 NZST), el campo de fecha y hora de mensaje AS2 para ese mensaje en el informe de estado de AS2 se establecerá en la hora actual.  
  
## <a name="status-reporting-is-still-configured-after-bam-tools-have-been-uninstalled"></a>El informe de estado está todavía configurado después de que se hayan desinstalado las herramientas de BAM.  
 Para instalar el informe de estado de EDI, debe instalar las herramientas de BAM. Sin embargo, si desinstala las herramientas BAM, el informe de estado aún estará configurado. es así por diseño.  
  
 Después de que se quiten las herramientas de BAM, no volverá a ser posible buscar tablas de informe de estado a través de la interfaz de usuario. Sin embargo, si el informe de estado se habilita, el servidor BizTalk Server seguirá creando registros en las tablas de informe de estado.  
  
## <a name="only-one-edi-interchange-will-be-correlated-to-an-as2-message-in-the-status-report-ui"></a>Se correlacionará sólo un intercambio EDI en un mensaje AS2 en la interfaz de usuario de informe de estado.  
 Si un mensaje AS2 contiene varios intercambios EDI e intenta que se muestre el estado de éstos en el mensaje AS2, sólo se mostrará el último intercambio EDI en el informe de estado de intercambios y confirmaciones. Además, el **n de Control de intercambio de EDI** campo en el informe de estado de AS2 y MDN sólo mostrará el último número de control de intercambio. (El número de control de intercambio correlaciona el mensaje AS2 y su carga de intercambio EDI).  
  
 Los datos para todos los intercambios EDI en un mensaje AS2 se guardan en la base de datos de informe de estado. Puede mostrar todos los intercambios en un mensaje de AS2 en el informe de estado de confirmación y del intercambio si la **Control Id. es igual a todos** cláusula es la consulta de informe de estado. Esto también puede hacer que se muestren otros intercambios que no se encuentren en el mensaje AS2, sin embargo, puede determinar los intercambios EDI que son en un único mensaje AS2 si busca en otros campos, como en Entidad remitente, Entidad receptora y Fecha y hora de intercambio.  
  
## <a name="removing-the-bam-tools-from-a-group-will-prevent-you-from-viewing-edi-or-as2-status-reports"></a>Si quita las herramientas de BAM de un grupo evitará que se visualicen los informes de estado de EDI o AS2.  
 Si quita las herramientas de BAM de un grupo e intenta visualizar los informes de estado de EDI o AS2 se producirán errores. Uno de estos errores indicaría que no se encuentran los procedimientos almacenados bts_GetBatchStatusRecords. Si obtiene un error cuando intente visualizar informes de estado de EDI o AS2, compruebe que el grupo, el tiempo de ejecución y las herramientas de BAN se configuran correctamente para EDI y AS2.  
  
 Puede evitar este problema si quita la configuración de las herramientas de BAM en lugar de simplemente eliminarlas. Si quita la configuración de las herramientas de BAM, se le solicitará que también lo haga en la característica dependiente EDI o AS2. No se le solicitará que lo haga si quita las herramientas de BAM.  
  
## <a name="status-reporting-will-not-work-after-an-upgrade-if-the-bam-tools-are-not-configured"></a>El estado de informe no funcionará después de la actualización si no se han configurado las herramientas de BAM.  
 Para que funcione el informe de estado de EDI y AS2, las herramientas de BAM deben estar configuradas. Si efectúa una actualización de la instalación de [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] a una versión posterior sin configurar, en este proceso, las herramientas de BAM, la funcionalidad de informe de estado de EDI y AS2 no funcionará correctamente en la instalación actualizada.  
  
 Si desea utilizar el estado de creación de informes después de actualizar a BizTalk Server, asegúrese de que las herramientas BAM estén configuradas antes de realizar la actualización.  
  
 Si el informe de estado no funciona tras la actualización, revise los registros de actualización para determinar si las herramientas de BAM se configuraron antes de comenzar el proceso. Si no es así, puede configurar las herramientas BAM y, a continuación, implementar la actividad de BAM BusinessMessageJournal incluida en el archivo edistatusreportingactivitydefs.XML que encontrará en  *\<unidad\>*: \Program Servidor BizTalk Server.  
  
## <a name="disabling-transaction-set-storage-affects-an-activated-batch-but-enabling-storage-does-not"></a>Si deshabilita el almacenamiento de conjuntos de transacciones afecta a un lote activado; si habilita el almacenamiento, no.  
 Si deshabilita el almacenamiento de los conjuntos de transacciones cuando se activa una instancia de la orquestación de procesamiento por lotes, el cambio se aplicará inmediatamente. El servidor BizTalk Server almacenará conjuntos de transacciones para el lote cuando se habilite el almacenamiento pero no se almacenarán conjuntos de transacciones después de que se haya deshabilitado el almacenamiento. Puede deshabilitar el almacenamiento de conjuntos de transacciones si desactiva la propiedad “Almacenar carga y conjunto de transacciones para el informe” en el panel General del cuadro de diálogo Propiedades de EDI.  
  
 Sin embargo, si activa una instancia de la orquestación o procesamiento por lotes cuando está deshabilitado el almacenamiento de conjuntos de transacciones y, a continuación, habilita el almacenamiento, no se almacenarán transacciones para el lote que se está creando.  
  
## <a name="unicode-as2-messages-will-not-be-displayed-completely-in-text-wire-format"></a>Los mensajes AS2 en UNICODE no se mostrarán completos en el formato de mensaje en texto.  
 Si el servidor de BizTalk procesa un mensaje AS2 o un MDN que se codifica en formato UNICODE e intenta visualizar el mensaje en formato de mensaje en texto legible, BizTalk Server no mostrará el mensaje completo. Esto se produce porque el byte “00” del formato UNICODE se interpreta como el final de la secuencia. Sin embargo, si intenta visualizar el mensaje en formato binario, BizTalk Server mostrará el mensaje completo.  
  
 Esto se produce cuando el informe de estado se activa para los mensajes AS2 (en el panel General del cuadro de diálogo Propiedades de AS2) y cuando se habilita el almacenamiento de mensajes AS2 o MDN de entrada o salida (en el panel Entidad como receptora del mensaje AS2 o el panel Entidad como remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2).  
  
## <a name="enabling-as2-status-reporting-and-send-port-body-tracking-simultaneously-may-cause-an-error"></a>Si habilita un informe de estado de AS2 y un seguimiento de un cuerpo de puerto de envío de forma simultánea puede producirse un error.  
 Si habilita la generación de informes de estado de AS2 y cuerpo de puerto de envío se seguimiento al mismo tiempo, el siguiente error podría mostrarse en el Visor de eventos: "El motor de mensajería detectó un error al eliminar uno o más mensajes." Esto se produce cuando el puerto de envío es un puerto estático de envío AS2 petición-respuesta con canalizaciones AS2Send y AS2Receive. Se produce cuando se habilitan las siguientes propiedades:  
  
-   La propiedad "Activar informe AS2" del panel General del cuadro de diálogo Propiedades de AS2.  
  
-   La propiedad “Almacenar los mensajes AS2 salientes codificados en la base de datos sin repudio” del panel Entidad como receptora del mensaje AS2 del cuadro de diálogo Propiedades de AS2.  
  
-   La propiedad “Mensaje de solicitud después del procesamiento de puerto” en el panel Seguimiento del cuadro de diálogo Propiedades de puerto de envío.  
  
 La solución a este problema es desactivar la propiedad “Almacenar los mensajes AS2 salientes codificados en la base de datos sin repudio” o la propiedad “Mensaje de solicitud después del procesamiento de puerto”. Le recomendamos que deshabilite “Mensaje de solicitud después del procesamiento de puerto” para que el seguimiento de AS2 pueda capturar la información del cuerpo junto con otras informaciones para el informe de estado de AS2.  
  
## <a name="edi-and-as2-message-context-properties-are-not-available-after-upgrading-to-biztalk-2009"></a>Las propiedades de contexto de mensajes de EDI y AS2 no están disponibles después de actualizar a BizTalk 2009  
 Después de actualizar a BizTalk Server, ninguna propiedad de contexto se muestra en informes de estado de cualquier mensaje EDI o AS2 recibido antes de realizar la actualización.  Los mensajes recibidos tras la actualización mostrarán correctamente las propiedades de contexto.  
  
 Las colecciones de propiedades de contexto de EDI y AS2 no se almacenaron como parte del mensaje en versiones anteriores de BizTalk Server y no están disponibles tras una actualización. Después de actualizar a BizTalk Server, AS2 propiedades de contexto se almacenan como parte del mensaje, sin embargo las propiedades de contexto EDI no son.  
  
## <a name="interchange-date-for-received-documents-may-display-the-wrong-year-in-status-reports"></a>La fecha de intercambio de documentos recibidos puede mostrar el año incorrecto en los informes de estado  
 Si un documento recibido especificaba la fecha en formato AAMMDD, BizTalk Server utiliza la lógica siguiente para determinar el valor de año:  
  
-   Si AA es mayor o igual a 75, el año se mostrará como 19YY.  
  
-   Si AA es menor que 75, el año se mostrará como 20YY.  
  
 Por ejemplo, si el valor de ISA09 de un mensaje entrante contiene 991113, el informe de estado mostrará la fecha como 11/13/1999.  
  
## <a name="error-message-may-be-displayed-as-a-string-of-question-marks"></a>El mensaje de error puede mostrarse como cadena de signos de interrogación.  
 En las compilaciones de BizTalk Server localizadas, si un mensaje de error se muestra como cadena de signos de interrogación, es necesario cambiar la configuración regional del sistema según el idioma del sistema operativo para poder ver correctamente el mensaje de error esperado. Para obtener más información acerca de cómo cambiar la configuración regional del sistema, consulte [cambiar la configuración regional del sistema](http://windows.microsoft.com/en-IN/windows-vista/Change-the-system-locale).  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de soluciones EDI y AS2](../core/troubleshooting-edi-and-as2-solutions.md)   
 [Informes de estado de EDI y AS2](../core/edi-and-as2-status-reporting.md)