---
title: Ensamblar un intercambio EDI por lotes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18f64595-935e-4d52-9ec2-5edf7c2b9e83
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c4274362e5ec8441e203d0b2b97f27e95235fd9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="assembling-a-batched-edi-interchange"></a>Ensamblar un intercambio EDI por lotes
Para ensamblar elementos por lotes de conjunto de transacción individual en un intercambio EDI, las funcionalidades EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizan lo siguiente:  
  
-   Identifican elementos por lotes para su procesamiento.  
  
-   Validan y almacenan en búfer elementos por lotes individuales tras la recepción.  
  
-   Recuperan elementos por lotes específicos y ensamblan un intercambio por lotes cuando se cumplen los criterios de versión.  
  
 La hora de inicio para la colección de mensajes individuales para obtener acceso a un lote está determinada por los criterios de activación por lotes. La hora en el que el lote se libera está determinada por los criterios de versión por lotes. Para obtener más información acerca de estos dos conjuntos de criterios, vea [configurar un lote saliente](../core/configuring-an-outgoing-batch.md).  
  
## <a name="message-flow-for-outgoing-batched-messages"></a>Flujo de mensajes para mensajes por lotes salientes  
 Cuando se configura [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar el procesamiento por lotes de un mensaje saliente, los componentes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] realizarán las siguiente series de pasos para preparar el mensaje por lotes para el envío. Estas series de pasos describen el caso en el que la canalización EDIReceive con el componente de canalización de BatchMarker procesa los intercambios recibidos que contienen los conjuntos de transacciones que se van a procesar por lotes para el envío.  
  
1.  El componente de canalización BatchMarker en la canalización EDIReceive determina los mensajes necesarios que se van a procesar a partir de la configuración de filtro por lotes de EDI en las propiedades de entidad. (Este es el único componente por lotes que examina la configuración de filtro de lotes y actúa en ellos).  
  
2.  Si los valores de filtro de la configuración de un solo lote se suscriben a un mensaje, el componente BatchMarker promocionará la propiedad `EDI.ToBeBatched = True`. Esto asegura que la orquestación de procesamiento por lotes recogerá el mensaje.  
  
3.  Si los valores de filtro de la configuración de más de un lote coinciden con el contexto de un mensaje, el componente BatchMarker promociona las propiedades .`EDI.ToBeRouted = True` y establece la propiedad `EDI.BatchIds` en una lista delimitada por espacios que contiene los identificadores de lote coincidentes.  Esto asegura que la orquestación de enrutamiento se suscribirá al mensaje.  
  
    > [!NOTE]
    >  Puede promocionar las propiedades de contexto apropiadas en una canalización de recepción personalizada o una orquestación personalizada. La canalización de recepción personalizada puede usar el componente de canalización BatchMarker o puede promocionar las propiedades sin usar el componente de canalización BatchMarker.  
  
4.  La orquestación de enrutamiento recoge cualquier conjunto de transacciones para el que se haya promocionado `EDI.ToBeRouted = True` y `EDI.BatchIds` y, a continuación, crea copias del conjunto de transacciones. De ese modo, se garantiza de que existe una copia de cada identificador de lote incluido en `EDI.BatchIds`. La orquestación de enrutamiento establece `EDI.ToBeBatched = True`, y `EDI.BatchId` se establece para el identificador de lote de la configuración de lote coincidente de cada copia del conjunto de transacciones. Esto garantiza que los conjuntos de transacciones se recogerán mediante la orquestación por lotes para el procesamiento por lotes.  
  
5.  La orquestación por lotes recoge todos los mensajes para los que las siguientes propiedades se han promocionado:  
  
    -   `EDI.ToBeBatched = True` y EDI.BatchId = el identificador del lote asociado con esta instancia de la orquestación de procesamiento por lotes.  
  
    -   `EDI.ToBeBatched = True` y EDI.BatchName = nombre del lote configurado y EDI.DestinationPartyName = nombre de la entidad que contiene la configuración de lote.  
  
     Al procesar los mensajes entrantes mediante la canalización EDIReceive (con el componente de canalización BatchMarker), la orquestación por lotes realizará el procesamiento de los conjuntos de transacciones con codificación EDIFACT o X12.  
  
    > [!NOTE]
    >  Habrá una instancia de la orquestación por lotes por cada configuración de lotes activa, y cada una se suscribe a un identificador de lote concreto. El valor de identificador de lote se establece automáticamente al crear una nueva configuración de lote en el **identificación** sección de la **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el  **Propiedades del acuerdo de** cuadro de diálogo.  
  
6.  La orquestación por lotes valida cada conjunto de transacciones de los que se va realizar el procesamiento por lotes. Si se produce un error en la validación del conjunto de transacciones, la propiedad de contexto `EDI.BatchItemValidationFailure` se establece en "True". El **BatchSuspend** orquestación recoge el mensaje en función de esa propiedad de contexto, registra la información de error y, a continuación, se suspende.  
  
7.  Cuando se cumplen los criterios de liberación de lotes, la orquestación de procesamiento por lotes ensambla los elementos de lote en un lote y crea un sobre.  
  
8.  Una vez que la orquestación por lotes finaliza el procesamiento por lotes de un intercambio, promociona las siguientes propiedades en ese intercambio: EDI.DestinationPartyName = %PartyName%, EDI.BatchEncodingType = X12 o EDIFACT, y EDI.ToBeBatched = False.  
  
9. Un puerto de envío recoge los conjuntos de transacciones por lotes en función de EDI. DestinationPartyName = \<PartyName\>, EDI. BatchEncodingType = EDIFACT o X12 y EDI. ToBeBatched = False.  
  
## <a name="batching-orchestration-control-messages"></a>Mensajes de control de orquestaciones por lotes  
 La orquestación por lotes se activa, finaliza o reemplaza mediante los siguientes mensajes de control:  
  
-   **BatchActivation**: cuando la orquestación recibe este mensaje, se crea una instancia de la orquestación por lotes y la orquestación se activa para recibir los elementos por lotes (si cumple con los criterios de activación por lotes). Se envía este mensaje de control, haga clic en el **iniciar** botón de una configuración de lote en el **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo.  
  
-   **BatchTermination**: cuando la orquestación recibe este mensaje, crea un lote a partir de elementos por lotes existentes, publica el mensaje en el cuadro de mensajes y finaliza. Se envía este mensaje de control, haga clic en el **detener** botón de una configuración de lote en el **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo.  
  
    > [!NOTE]
    >  La orquestación también se termina si alcanza el tiempo especificado para la **final por** propiedad en el **terminación** sección de la **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional del **propiedades del acuerdo de** cuadro de diálogo.  
  
-   **BatchOverride**: cuando la orquestación recibe este mensaje, crea un lote a partir de los elementos existentes, publica el mensaje en el cuadro de mensajes y, a continuación, espera para los mensajes para el siguiente lote. Se envía este mensaje de control, haga clic en el **invalidar** botón de una configuración de lote en el **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo.  
  
 La orquestación por lotes recibe los mensajes de control a través de la ubicación de recepción BatchControlMessageRecvLoc. El intervalo de sondeo para esta ubicación de recepción SQL se establece en 30 segundos de forma predeterminada, pero puede cambiarse en el **propiedades de transporte SQL** cuadro de diálogo de la ubicación de recepción. El descenso del intervalo de sondeo garantizará que la ubicación de recepción BatchControlMessageRecvLoc recibirá un mensaje de control poco después de que realice una acción que se envíe al mensaje de control (por ejemplo, cuando inicie la orquestación por lotes).  
  
 Se producen los siguientes pasos cuando inicia una orquestación de lotes:  
  
1.  Al hacer clic en el **iniciar** botón, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea un registro en una tabla que indica qué entidad e identificador de lote a activar la orquestación de lotes.  
  
2.  El adaptador SQL asociado a los sondeos de la ubicación de recepción BatchControlMessageRecvLo para ver si el registro existe en la base de datos.  
  
3.  Si existe el registro, el adaptador SQL genera un mensaje de control mediante información en el registro.  
  
    > [!NOTE]
    >  Con la generación del mensaje de control de esta forma se garantiza que la orquestación no puede iniciarse mediante un mensaje de control no válido.  
  
4.  La ubicación de recepción BatchControlMessageRecvLoc recibe el mensaje de control y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] activa una instancia de orquestación por lotes.  
  
## <a name="batch-components"></a>Componentes de lotes  
 El EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] procesa por lotes los conjuntos de transacciones XML en intercambios EDI mediante los componentes siguientes:  
  
-   BatchMarkerReceivePipelineComponent en la canalización de recepción EDI  
  
-   Orquestación de enrutamiento  
  
-   Orquestación por lotes  
  
-   Actualizar la orquestación de procesamiento por lotes  
  
-   Orquestación BatchSuspend  
  
-   Canalización de envío EDI  
  
 Estos componentes se instalan como DLL cuando instala y configura la funcionalidad EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
> [!NOTE]
>  Los componentes por lotes en la funcionalidad EDI y AS2 de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no garantizan el orden de los conjuntos de transacciones en un lote.  
  
### <a name="batchmarkerreceivepipelinecomponent"></a>BatchMarkerReceivePipelineComponent  
 BatchMarkerReceivePipelineComponent en la canalización de recepción EDI habilita la orquestación por lotes para recoger los mensajes a los que se les va realizar el procesamiento por lotes. Este componente de canalización se aplica después del desensamblador en la canalización de recepción EDI. El componente evalúa los criterios de filtro establecidos en el **filtro** sección de la **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo y las marcas de que los conjuntos de transacciones con las siguientes propiedades de contexto para el procesamiento mediante el enrutamiento y orquestaciones por lotes  
  
-   Si se suscribe una única entidad a un mensaje para el procesamiento por lotes, se promociona `ToBeBatched = True` y BatchId se establece en el valor del identificador de lote de la configuración de lote coincidente. Esto habilita la recogida mediante la orquestación por lotes.  
  
-   Si se suscriben varios lotes en un mensaje que se va a procesar por lotes, promociona `ToBeRouted = True` y establece la propiedad `EDI.BatchIds` en una lista delimitada por espacios de los identificadores de lote. Esto habilita la recogida mediante la orquestación de enrutamiento.  
  
-   Si no existe ninguna suscripción, no promociona una propiedad de contexto. Esto indica que no se va a realizar el procesamiento por lotes del conjunto de transacciones.  
  
 El componente de canalización no tiene en cuenta los mensajes que no sean XML ni los mensajes con la propiedad `ReuseEnvelope` (lotes conservados). Si las confirmaciones no se van a procesar por lotes, el componente de canalización ignorará los tipos de mensajes de confirmación (CONTRL, TA1 y 997). Para optimizar el procesamiento de las orquestaciones por lotes y de enrutamiento, BatchMarkerPipelineComponent aprueba el mensaje a través del cuadro de mensajes si el desensamblador establece en “SuspendedQueue” la propiedad de contexto de mensaje `MessageDestination`.  
  
 Si está usando una canalización personaliza, en lugar de la canalización EDIReceive, puede usar el componente BatchMarker en su canalización personalizada. Si no usa la canalización EDIReceive y publica mensajes desde una orquestación, deberá promocionar `ToBeBatched = True` y `BatchID` en el identificador de un lote activo de uno de sus componentes.  
  
### <a name="routing-orchestration"></a>Orquestación de enrutamiento  
 La orquestación de enrutamiento se suscribe en cualquier mensaje con la propiedad de contexto `ToBeRouted = True` y `EDI.BatchIds` establecidos en una lista de identificadores de lote delimitada por espacios. Esto se produce cuando se suscriben varios filtros de lote en un mensaje que se va a procesar por lotes. La orquestación de enrutamiento realizará una copia del mensaje para cada identificador de lote incluido en `EDI.BatchIds`. Marca cada copia con dos nuevas propiedades de contexto:  
  
-   `EDI.BatchID`, que se establece en el identificador del lote para el que se ha creado el mensaje.  
  
-   `EDI.ToBeBatched`, que se establece en True.  
  
 A continuación, enruta las copias en el cuadro de mensajes que la orquestación por lotes va a recoger. Cada identificador de lote de destino usa una instancia singleton de la misma orquestación, con un filtro en el identificador de lote específico.  
  
### <a name="batching-orchestration"></a>Orquestación por lotes  
 La orquestación por lotes es un servicio con estado que almacena en búfer los elementos de lotes (conjuntos de transacciones) durante un período de tiempo, los ensambla en un intercambio y, a continuación, libera el intercambio a la canalización de recepción basada en los criterios de versión.  
  
 Después de que se active, una instancia de la orquestación por lotes puede iniciar el procesamiento por lotes de mensajes de un tipo de codificación determinado en una entidad determinada (si la **iniciar** datetime haya pasado). En cualquier momento puede haber varias instancias de la orquestación por lotes para cada entidad, una por cada configuración de lotes activa. Una única instancia de la orquestación por lotes puede liberar varios lotes para una configuración de lotes única. Después de que se satisfagan los criterios finales, se terminará la instancia de orquestación por lotes. Una nueva instancia de la orquestación por lotes deberá crearse de forma manual de la administración de socios comerciales (TPM) mediante el **iniciar** botón.  
  
 Si inicia la orquestación del lote antes del inicio de fecha y hora se muestra en el **activación** sección en el de la **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el **acuerdo Propiedades** cuadro de diálogo, sólo recibirá mensajes que se especifican en el intervalo de activación. No recibirá mensajes enviados antes de la hora y fecha de inicio.  
  
 La orquestación por lotes realiza lo siguiente:  
  
-   Se suscribe a elementos de lotes XML con las propiedades de contexto `EDI.ToBeBatched = True` y `EDI.BatchId`, el identificador de configuración de lotes o `EDI.ToBeBatched = True` y EDI.BatchName = el nombre del lote configurado y EDI.DestinationPartyName = el nombre de la entidad que contiene la configuración de lote. Recibe elementos de lotes mediante una **recepción** operación de acción en un bucle.  
  
    > [!NOTE]
    >  La orquestación por lotes no procesa por lotes los conjuntos de transacciones en función de los criterios de filtro establecidos en la sección Filtro de la **configuración de procesamiento por lotes** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de** cuadro de diálogo. Se suscribe a los conjuntos de transacciones que tengan las propiedades de contexto anteriores establecidas en ellos. El componente de canalización BatchMarker establece y promociona las propiedades de contexto que se basan en la configuración de filtrado en las propiedades de entidades.  
  
-   Recupera los valores de configuración de lotes para la entidad identificada en la propiedad de contexto `BatchId`.  
  
-   Valida el elemento de lote (conjunto de transacciones) que se basa en la configuración de entidades.  
  
-   Si se produce un error en un elemento de lote, la orquestación por lotes promocionará la siguiente propiedad en ese conjunto de transacciones: `EDI.BatchItemValidationFailure = True` El **BatchElementSuspend** orquestación se suscribe a cualquier conjunto de transacciones para que se ha promocionado esta propiedad. Esta orquestación proporcionará información de error detallada para el primer error encontrado en el procesamiento por lotes del intercambio.  
  
-   Si no se produce un error en un elemento por lotes, mantiene una referencia a ese elemento de lotes.  
  
-   Cuando se recibe el mensaje de control adecuado o se cumple los criterios de versión por lotes, se interrumpe fuera de la **recepción** bucle de una acción, recupera todos los elementos por lotes del cuadro de mensajes y ensambla el intercambio.  
  
-   Establece la propiedad de contexto `ToBeBatched = False` para el intercambio y la propiedad de contexto DestinationPartyName = %PartyName% donde %PartyName% es el nombre de la entidad para el que está pensado el mensaje.  
  
    > [!NOTE]
    >  Si un puerto de envío se suscribe a alguna o ambas propiedades, `EDI.ToBeBatched = False` y EDI.DestinationPartyName = %PartyName%, el puerto de envío puede recoger el intercambio por lotes. Compruebe que los filtros del puerto de envío se configuran de modo que el puerto de envío recoge solo dichos intercambios procesados por lotes para lo que ha sido diseñado.  
  
    > [!NOTE]
    >  Los intercambios que coloca la orquestación por lotes en el cuadro de mensajes solo tiene las propiedades `EDI.ToBeBatched = False`, EDI.DestinationPartyName = %PartyName% y EDI.BatchEncodingType = "X12" o "EDIFACT" promocionadas en el contexto. Se pierden todas las propiedades de contexto de los conjuntos de transacciones originales.  
  
-   Se aplican las siguientes propiedades al sobre para un intercambio con codificación X12:  
  
    -   ISA6: identificador del remitente del intercambio  
  
    -   ISA8: identificador del receptor del intercambio  
  
    -   ISA15: indicador de uso  
  
    -   ISA_Blob (escrito en el contexto)  
  
-   Se aplican las siguientes propiedades al sobre para un intercambio con codificación EDIFACT:  
  
    -   UNB2.1: identificador del remitente del intercambio  
  
    -   UNB3.1: identificador del destinatario del intercambio  
  
    -   UNB2.3: dirección para el enrutamiento inverso  
  
    -   UNB11: indicador de uso  
  
    -   UNA_Blob (escrito en el contexto)  
  
    -   UNB_Blob (escrito en el contexto)  
  
-   Entrega el intercambio por lotes al cuadro de mensajes para que la canalización de recepción EDI lo recoja.  
  
### <a name="upgradebatching-orchestration"></a>Orquestación UpgradeBatching  
 La orquestación UpgradeBatching trata los mensajes que tienen la propiedad `EDI.ToBeBatched` establecida en true, pero que no tienen la propiedad `EDI.BatchID` establecida.  
  
 En versiones anteriores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cada entidad podía tener solo una configuración de procesamiento por lotes.  Al procesar mensajes que tenían `EDI.ToBeBatched` establecido en true, `EDI.DestinationPartyId` se usaba para determinar la entidad y, a continuación, se leía la configuración de lotes de las propiedades del acuerdo.  
  
 En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], cada entidad puede tener varias configuraciones de lotes asociadas, de modo que `EDI.DestinationPartyId` no proporciona información suficiente para determinar qué configuración de lotes se debe usar.  Cuando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe un mensaje, la propiedad `EDI.BatchId` se usa para identificar qué configuración de lotes específica se debe usar al procesar un mensaje.  
  
 Después de actualizar a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], es posible que todavía tenga canalizaciones personalizadas que usan la propiedad `EDI.DestinationPartyId` para especificar la configuración de la entidad. Cuando se recibe un mensaje que tiene `EDI.ToBeBatched` establecido en true y que tiene `EDI.DestinationPartyID` establecido en lugar de EDI.BatchID, la orquestación UpgradeBatching intenta determinar qué configuración de lotes se debe usar.  
  
 La orquestación UpgradeBatching usa los filtros de suscripción siguientes para suscribirse en documentos que están marcados para el procesamiento por lotes, pero que no especifican ningún identificador de lote:  
  
-   `EDI.ToBeBatched=True`  
  
-   `EDI.EncodingType` existe  
  
-   `EDI.DestinationPartyId` existe  
  
 Si la orquestación recibe un mensaje, usará el nombre de la entidad y el tipo de codificación para intentar buscar una configuración de lote coincidente para el mensaje.  El `EDI.DestinationPartyID` propiedad se utiliza para determinar el nombre de la entidad y, a continuación, la orquestación busca un nombre de lote que coincida con \<PartyName\>+\<EncodingType\>+ Default.  Por ejemplo, si el nombre de la entidad es Contoso, y el valor de `EDI.EncodingType` es X12, la orquestación buscará un lote con el nombre ContosoX12Default.  
  
 Si se encuentra una configuración de lote coincidente, el mensaje se coloca de nuevo en el cuadro de mensajes, con las siguientes propiedades:  
  
-   `EDI.ToBeBatched = True`  
  
-   `EDI.ToBeRouted = False`  
  
-   EDI.BatchId = el identificador de lote para el lote coincidente  
  
 A continuación, la orquestación de procesamiento por lotes procesa el mensaje.  
  
> [!NOTE]
>  Si no se encuentra ningún lote que coincida, sucederá lo siguiente:  
>   
>  -   No se enviará el mensaje a la orquestación BatchSuspend.  
> -   Se suspenderá la instancia de orquestación UpgradeBatching y el mensaje.  
> -   Se registrará un error en el registro de eventos, lo que indica que no se ha encontrado ningún lote.  
  
### <a name="batchsuspend-orchestration"></a>Orquestación BatchSuspend  
 La orquestación BatchSuspend controla los mensajes no válidos que recibe la orquestación por lotes. La orquestación BatchSuspend es necesaria porque no hay forma directa de suspender un mensaje de una orquestación (en este caso, la orquestación por lotes) sin detener la ejecución de la instancia de la orquestación.  
  
 Cuando una instancia de orquestación por lotes recibe un mensaje, intenta validarlo. Si se produce un error en la validación del mensaje, la orquestación por lotes crea una instancia de la orquestación BatchSuspend y establece la propiedad de contexto `EDI.BatchItemValidationFailure` en True. La orquestación BatchSuspend se suscribe a todos los mensajes con la propiedad de contexto establecida en True. Después de que el conjunto de transacciones no válidas se enrutan en la orquestación BatchSuspend, se suspende la instancia de orquestaciones BatchSuspend.  
  
 La orquestación BatchSuspend proporciona la información de error detallada para el primer error que se haya encontrado.  
  
 Puede usar la propiedad `EDI.BatchElementValidationFailure` en un filtro para crear una orquestación personalizada con el fin de controlar los conjuntos de transacciones que produzcan un error en la validación mediante la orquestación por lotes.  
  
### <a name="edi-send-pipeline"></a>Canalización de envío EDI  
 Después de recibir un intercambio de lotes para la orquestación por lotes, la canalización de envío EDI realiza lo siguiente:  
  
-   Para un intercambio con codificación X12, la canalización de envío aplica las siguientes propiedades al sobre:  
  
    -   ISA2: información de autorización  
  
    -   ISA4: información de seguridad  
  
    -   ISA9: fecha del intercambio  
  
    -   ISA10: hora del intercambio  
  
    -   ISA13: número de control del intercambio  
  
    -   GS4: fecha  
  
    -   GS5: hora  
  
    -   GS6: número de control de grupo  
  
    -   ST2: número de control de conjunto de transacciones  
  
-   Para un intercambio con codificación EDIFACT, la canalización de envío aplica las siguientes propiedades al sobre:  
  
    -   UNB4.1: fecha  
  
    -   UNB4.2: hora  
  
    -   UNB5: referencia de control del intercambio  
  
    -   UNB6.1: contraseña de referencia de destinatario  
  
    -   UNG4.1: fecha  
  
    -   UNG4.2: hora  
  
    -   UNG5: referencia de grupo funcional  
  
    -   UNG8: contraseña de aplicaciones  
  
-   Entrega el mensaje a través del adaptador asociado.  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento por lotes mensajes EDI salientes](../core/batching-outgoing-edi-messages.md)