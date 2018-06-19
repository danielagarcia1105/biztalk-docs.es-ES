---
title: Problemas conocidos relacionados con el procesamiento por lotes de EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510ac82b-8a02-4135-87b7-0a5f288f5317
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537a0591ba45a209fd3f22c0a993a99baac58d7f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008221"
---
# <a name="known-issues-with-edi-batching"></a>Problemas conocidos del procesamiento por lotes de EDI
En este tema se describen problemas conocidos relacionados con el procesamiento por lotes en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a>La división de subdocumentos no se realizó aunque la anotación de subdocumentos se estableció en Sí  
 **Síntoma**  
  
 Un intercambio HIPAA no se ha dividido en subdocumentos aunque la anotación subdocument_creation_break en el esquema HIPAA para dicho intercambio se estableció en "Sí".  
  
 **Causa posible**  
  
-   La opción de procesamiento por lotes entrantes para la entidad remitente se estableció en "Conservar intercambio". Dado el caso, un documento HIPAA no se dividirá en subdocumentos aunque la anotación subdocument_creation_break en el esquema HIPAA se haya establecido en "Sí".  
  
-   La anotación subdocument_break se estableció en "Sí", pero la anotación subdocument_creation_break no se estableció en "Sí".  
  
 **Resolución**  
  
-   En el **validación y configuración de la generación de confirmación** página de la **propiedades de EDI** cuadro de diálogo para la entidad remitente, establezca el **procesamiento por lotes de entrada** opción propiedad a cualquier **dividir intercambio como conjuntos de transacciones: suspender conjuntos de transacciones en caso de Error** o **dividir intercambio como conjuntos de transacciones: suspender intercambio en caso de Error**.  
  
-   Un documento HIPAA no se dividirá en subdocumentos a menos que la anotación de subdocument_creation_break se establezca en “Sí”.  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a>Se puede producir un error en la validación de un lote si se realizan cambios en los ajustes de configuración del lote mientras que la orquestación de procesamiento por lotes está activada.  
 Si cambia la configuración de lotes mientras la orquestación de procesamiento por lotes está procesando un lote, éste no reflejará la nueva configuración. Esto puede dar como resultado errores de validación en la canalización de envío.  
  
 Estas opciones de configuración se encuentran en la página Lotes del cuadro de diálogo Propiedades de EDI.  
  
 Para resolver este problema, reinicie las instancias de host asociadas a las orquestaciones de procesamiento por lotes. Esto hace que el cambio en los parámetros de configuración del lote se aplique de forma inmediata.  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a>La ubicación de recepción BatchControlMessageRecvLoc sólo se puede ejecutar en un equipo de 32 bits o en WOW en un equipo de 64 bits.  
 Los adaptadores de SQL sólo funcionan en equipos de 32 bits o cuando se ejecutan en el emulador WOW64 en equipos de 64 bits. Como resultado, la ubicación de recepción BatchControlMessageRecvLoc, que se instala mediante el programa de configuración y usa el adaptador de SQL, sólo funcionará en un equipo de 32 bits o al ejecutarse en WOW en un equipo de 64 bits. Se requiere esta ubicación de recepción para el procesamiento por lotes.  
  
 Al ejecutar la ubicación de recepción BatchControlMessageRecvLoc en WOW en un equipo de 64 bits, debe ejecutar las orquestaciones de procesamiento por lotes en un host distinto. Si se ejecutan en el mismo host como ubicación de recepción, las orquestaciones de procesamiento por lotes también se ejecutarán en WOW y perderá las ventajas de ejecutarlas en un equipo de 64 bits.  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a>Un puerto de envío no esperado puede recoger un lote.  
 Cuando la orquestación por lotes publica un intercambio, promueve dos propiedades: ToBeBatched = False y DestinationPartyName = \< *PartyName*\>. Un puerto de envío que se suscribe a una de estas propiedades o ambas puede recoger estos intercambios procesados por lotes. Compruebe que los filtros del puerto de envío se configuran de modo que el puerto de envío recoge dichos intercambios procesados por lotes para lo que ha sido diseñado.  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a>Un número de elementos de lotes superior al número de conjuntos de transacciones requerido para un lote puede que no solicite la versión del lote.  
 Si los criterios de versión del lote se basan en el número de conjuntos de transacciones por grupo o intercambio, es posible que un lote no se lance aunque el número de elementos de lotes sea superior al número de conjuntos de transacciones requerido para el lote que se va a lanzar. Esto puede suceder si habilita las confirmaciones y configura los criterios de filtro de lotes para agregar dichas confirmaciones al lote. En esta instancia, el número de elementos por lotes del grupo (o intercambio) será superior al número de conjuntos de transacciones por grupo (o intercambio). En dicha instancia, se lanzará un lote si el número de conjuntos de transacciones por grupo (o intercambio) es inferior al número requerido para el lanzamiento del lote, aunque al mismo tiempo el número de elementos por lotes puede ser superior al número de conjuntos de transacciones requerido para el lanzamiento del lote.  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a>No se han guardado elementos por lotes cuando se ha hecho clic en Iniciar.  
 **Síntoma**  
  
 Cuando **iniciar** se hizo clic en la página lotes para una entidad, se recopiló ningún mensaje para el lote.  
  
 **Causa posible**  
  
 La fecha y hora en que **iniciar** se hizo clic era anterior a la fecha y hora especificada en el **activación** sección. Como resultado, la instancia de orquestación se activó, pero no se recopiló ningún mensaje para el lote. Para obtener más información, consulte [configurar un lote saliente](../core/configuring-an-outgoing-batch.md).  
  
 **Resolución**  
  
 Haga clic en **detener** en la página de lotes para la configuración de lote tiene este problema. Establecer el **activación** como **iniciar inmediatamente** o escriba una fecha y hora anterior a la hora actual y, a continuación, haga clic en **iniciar**. Cuando se pregunte si desea restablecer el **iniciar** fecha y hora a la hora actual, haga clic en **Aceptar**. BizTalk Server empezará a recopilar mensajes para un lote en dicho punto.  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a>El número de bytes en un lote EDIFACT puede que dependa del juego de caracteres utilizado.  
 Los caracteres de algunos juegos de caracteres EDIFACT pueden ser caracteres de doble byte, mientras que en otros juegos de caracteres EDIFACT pueden ser caracteres de un solo byte. Debido a ello, al establecer los criterios de versión para lotes basados en el número de caracteres del intercambio, el número de bytes del intercambio puede ser distinto en función del juego de caracteres utilizado.  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a>Los caracteres "<" y "&" se deben representar en forma de codificación en el sobre de un lote  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]no admite los siguientes caracteres en su forma literal al crear los campos de sobre de un intercambio EDI por lotes: "<" y "&".  
  
 El uso de estos caracteres de forma literal en los campos de sobre de un intercambio procesado por lotes saliente dará como resultado un mensaje suspendido si se usa la canalización EdiSend para serializar el intercambio.  
  
 Si es necesario usar uno de estos caracteres en un campo de sobre de un lote, puede usar el valor codificado adecuado en la siguiente tabla al configurar el campo de sobre del administrador de BizTalk:  
  
|Carácter|Codificación|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 Si usa una de estas formas codificadas, los caracteres codificados se contarán como caracteres individuales cuando BizTalk Server valide la restricción de longitud del campo en las pantallas del Administrador de acuerdos de socios comerciales (PAM) de la consola de administración de BizTalk Server. Por ejemplo, aunque la codificación "&lt;"representa un carácter individual"\<" en el intercambio EDI por lotes, BizTalk Server lo contará como cuatro caracteres al validarlo con la restricción de longitud de campo concreto . Éste sólo es un problema de PAM, no del ensamblador EDI.  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a>Se produce una excepción durante la ejecución de la orquestación de actualización por lotes  
 **Síntoma**  
  
 Al usar un componente de canalización personalizado que establece la propiedad EDI.DestinationPartyId en documentos entrantes, es posible que reciba un error en el registro de eventos de la aplicación que indica que se produjo una excepción durante la ejecución de la orquestación del lote de actualización.  
  
 **Causa posible**  
  
 Si ErrorMessage = “No se encontró el lote”, este error indica que la orquestación del lote de actualización no pudo identificar correctamente un lote para el documento de entrada.  
  
 **Resolución**  
  
 La orquestación del lote de actualización usa el EDI.DestinationPartyId para buscar el nombre de la entidad. A continuación, la orquestación construye una cadena mediante el nombre de entidad, EDI.EncodingType y la cadena “Default” y busca una configuración de lote con un nombre de lote que coincida. Si no existe ninguna configuración de lote con este nombre, este error se registra en el registro de eventos de la aplicación y se suspende la instancia de la orquestación.  
  
> [!NOTE]
>  Por ejemplo, si el nombre de la entidad es Contoso y el EDI.EncodingType es X12, la orquestación buscará un lote denominado ‘ContosoX12Default’.  
  
 Para solucionar este problema, asegúrese de que existe un lote con un nombre que coincida con la cadena que construye la orquestación del lote de actualización.  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a>Los mensajes marcados con EDI.ToBeBatched = True y EDI.DestinationParties están suspendidos  
 **Síntomas**  
  
 Al usar un componente de canalización personalizado con el fin de marcar mensajes para lotes al establecer EDI.ToBeBatched = True y EDI.DestinationParties en una lista de identificadores de entidades, el mensaje se suspenderá con un error de enrutamiento que indica que no hay suscriptores.  
  
 **Causa posible**  
  
 En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cuando un mensaje debía procesarse mediante varias configuraciones de lote, debía establecer la propiedad EDI.DestinationParties en una lista delimitada por espacios de identificadores de entidades. La orquestación de enrutamiento se suscribe a mensajes mediante la propiedades EDI.ToBeBatched = True y EDI.DestinationParties y usaba la lista de identificadores de entidad incluidos en la propiedad EDI.DestinationParties para crear un mensaje para cada identificador y luego transferir los mensajes a la orquestación de lote.  Se usaba la determinación del lote mediante el identificador de entidad porque cada configuración de entidad solo podía tener una configuración de lote.  
  
 En BizTalk Server, cada entidad puede tener varias configuraciones de lote, por lo que ya no es suficiente para usar el identificador de la entidad para determinar la configuración de lote para que use.  Para indicar que un mensaje debe ser procesado mediante varias configuraciones de lote, el mensaje debe tener la propiedad EDI.BatchIDs configurada en una lista delimitada por espacios de identificadores de lote a la que debe enviarse el mensaje.  
  
> [!NOTE]
>  Al procesar mensajes marcados solo con un único identificador de entidad mediante la propiedad EDI.DestinationPartyId, el mensaje será procesado por la orquestación del lote de actualización. Para obtener más información, consulte [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).  
  
 **Resolución**  
  
 Actualice el componente de canalización personalizado de modo que establezca la propiedad EDI.BatchIDs en lugar de EDI.DestinationParties.  El identificador de lote para un lote específico puede encontrarse en la página de configuración Lotes de las propiedades de EDI para cada entidad.  
  
> [!NOTE]
>  Este problema no tiene lugar si se usa el componente de canalización BatchMarker para marcar el mensaje para lote.  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a>El tiempo de espera de actualización del filtro de lote está codificado en quince minutos  
 Al modificar los criterios de filtro del lote, transcurrirán 15 minutos hasta que entren en vigor los cambios. Este intervalo de actualización no se puede modificar. Para que el filtro entre en vigor inmediatamente, reinicie el proceso de host de BizTalk Server.  
  
## <a name="the-routingorchestration-suspends-after-reporting-an-uncaught-exception"></a>RoutingOrchestration se suspende después de informar de una excepción no detectada  
 **Síntomas**  
  
 Al procesar documentos destinados para varias configuraciones de lote, es posible que reciba un error en el registro de eventos de la aplicación desde XLANG/s en el que se indica que se ha producido un error en Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService debido a una excepción no detectada.  
  
 **Causa posible**  
  
 Este error puede tener lugar cuando RoutingOrchestration intenta enviar un mensaje a BatchingOrchestration y no se ha iniciado la instancia de BatchingOrchestration.  
  
 **Resolución**  
  
 Asegúrese de que se están ejecutando las instancias de BatchingOrchestration antes de enviar documentos para su procesamiento por lotes.  
  
## <a name="many-active-batches-may-cause-the-biztalkmsgboxdb-logfile-to-grow-large"></a>Muchos lotes activos pueden hacer que el archivo de registro BizTalkMsgBoxDb aumente demasiado de tamaño  
 **Síntomas**  
  
 Tras iniciar varios lotes, es posible que observe que el registro de transacciones de la base de datos de cuadro de mensajes de BizTalk (BizTalkMsgBoxDb) ha crecido demasiado.  
  
 **Causa posible**  
  
 Este problema puede suceder si ha iniciado un elevado número de lotes con criterios de liberación que provocan un corto intervalo entre liberaciones de lotes (por ejemplo, un lote programado para liberarse cada minuto).  
  
 La instancia de la orquestación del lote que se crea al iniciar un lote es un proceso de larga ejecución que persiste en la base de datos tras liberar un lote. Cada vez que persiste la orquestación, el registro de transacciones aumentará de tamaño debido a las transacciones implicadas en la persistencia.  
  
> [!NOTE]
>  La orquestación de lote incrementará el registro de transacciones en unos 30 kb aproximadamente durante la persistencia.  
  
 **Resolución**  
  
 Para resolver este problema, modifique los criterios de liberación de modo que aumente el tiempo entre liberaciones de lotes. Para obtener más información, consulte [configurar el procesamiento por lotes (X12)](../core/configuring-batching-x12.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar confirmaciones EDI](../core/configuring-edi-acknowledgments.md)   
 [Procesamiento por lotes entrantes](../core/processing-incoming-batches.md)   
 [Procesamiento por lotes mensajes EDI salientes](../core/batching-outgoing-edi-messages.md)   
 [Configuración de lotes de EDI](../core/configuring-edi-batches.md)