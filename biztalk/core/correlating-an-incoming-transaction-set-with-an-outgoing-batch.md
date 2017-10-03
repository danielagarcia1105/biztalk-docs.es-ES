---
title: "Poner en correlación una transacción entrante establecida con un lote saliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fbe40f8-7379-42be-b8a7-070ce8a7ce26
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd5a1ec83db1177050711d82bfb465c2bcb7637
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a>Correlacionar un conjunto de transacciones entrante con un lote saliente
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite correlacionar un conjunto de transacciones EDI que se envía a la orquestación de procesamiento por lotes con un lote saliente. Esto se consigue mediante la correlación de una entrada del informe de estado para el conjunto de transacciones que se envía a la orquestación de procesamiento por lotes (BTSInterchangeID) a una entrada del informe de estado para la orquestación (ActivityID). Esta correlación se realiza mediante el uso de entradas en la actividad de BAM BusinessMessageJournal. La orquestación de procesamiento por lotes crea estas entradas cuando se recibe un elemento por lotes.  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creará entradas en la actividad BusinessMessageJournal solo si el informe de estado de EDI y el seguimiento del conjunto de transacciones están habilitados para el acuerdo.  
  
 En las próximas secciones se describe lo siguiente:  
  
-   Cómo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] guarda los datos de seguimiento  
  
-   Cómo puede crear un componente de canalización personalizado para habilitar la correlación.  
  
-   Cómo puede correlacionar un conjunto de transacciones entrante con un lote saliente.  
  
-   Cómo puede consultar la actividad BusinessMessageJournal para determinar el BTSInterchangeID del lote si conoce el BTSInterchangeID del conjunto de transacciones del lote.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="changes-to-the-activities"></a>Cambios en las actividades  
 La orquestación de procesamiento por lotes crea entradas en las actividades BatchingActivity, TransactionSetActivity y BusinessMessageJournal de BAM. Cuando el conjunto de transacciones se mueve por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea las siguientes entradas en estas tablas de actividad para el conjunto de transacciones y el lote que lo incluye:  
  
1.  Cuando el desensamblador EDI procesa un intercambio EDI entrante, crea entradas en las tablas InterchangeStatusActivity y TransactionSetActivity.  
  
    > [!NOTE]
    >  Para obtener más información acerca de las actividades BAM, consulte [las actividades de BAM creadas para realizar un seguimiento de mensajes EDI-AS2](../core/bam-activities-created-to-track-edi-as2-messages.md).  
  
2.  Cuando la orquestación de procesamiento por lotes se inicia, la orquestación crea una entrada en la actividad BatchingActivity. El subsistema BAM crea un valor para ActivityID.  
  
3.  Una vez la orquestación de procesamiento por lotes recoge el conjunto de transacciones, crea una entrada para el conjunto de transacciones en la tabla TransactionSetActivity.  
  
4.  La orquestación crea una entrada en la actividad BusinessMessageJournal. Ésta establece el campo MessageTrackingID de esta actividad en el valor del campo ActivityID de la entrada creada por la orquestación en la tabla TransactionSetActivity. También establece el campo BTSInterchangeID en la propiedad de contexto BTS.InterchangeID para el conjunto de transacciones, y el campo BTSMessageID en la propiedad de contexto BTS.MessageID para el conjunto de transacciones.  
  
5.  La orquestación crea una segunda entrada en la actividad BusinessMessageJournal. Establece el campo MessageTrackingID en el campo ActivityID de la entrada creada por la orquestación en la tabla TransactionSetActivity. Establece el campo BTSInterchangeID en la propiedad de contexto BTS.InterchangeID para el lote. No establece BTSMessageID. Establece ContainerActivityID en el valor de ActivityID en BatchingActivity.  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a>Crear un componente de canalización personalizado para habilitar la correlación  
 Para configurar la correlación de un conjunto de transacciones entrante con un lote saliente que contiene ese conjunto de transacciones, debe crear un componente de canalización personalizado. Este componente de canalización debe ir tras el Desensamblador EDI y antes del componente BatchMarker de la canalización EDIReceive. Este componente de canalización debe crear una entrada en la actividad BusinessMessageJournal. En esta entrada, el campo BTSInterchangeID debe estar establecido en la propiedad de contexto BTS.InterchangeID, y el campo BTSMessageID debe estar establecido en la propiedad de contexto BTS.MessageID.  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a>Buscar InterchangeID para un conjunto de transacciones establecido en un lote  
 Correlacione un intercambio recibido y el lote que contiene el conjunto de transacciones del intercambio mediante el uso de entradas de la tabla BatchingActivity y de la actividad BusinessMessageJournal, según se describe a continuación.  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a>Para correlacionar un conjunto de transacciones entrante con un lote saliente que contiene ese conjunto de transacciones  
  
1.  Determine el valor de ActivityID del lote de la tabla BatchingActivity.  
  
2.  Busque el valor de ActivityID en el campo ContainerActivityID de la tabla de la actividad BusinessMessageJournal.  
  
3.  En el registro identificado por ContainerActivityID, busque el valor del campo MessageTrackingID, que está asociado con el lote.  
  
4.  Mediante el uso del valor del campo MessageTrackingID asociado con el lote de la tabla de la actividad BusinessMessageJournal, busque algún valor en el campo MessageTrackingID de otros registros de la tabla de la actividad BusinessMessageJournal. Algunos registros encontrados están asociados con los conjuntos de transacciones del lote, puesto que están registrados por la orquestación de procesamiento por lotes.  
  
5.  En un registro asociado con el conjunto de transacciones de la tabla de la actividad BusinessMessageJournal, busque el valor del campo BTSInterchangeID.  
  
6.  Mediante el uso del valor de BTSInterchangeID, puede buscar un registro para el conjunto de transacciones creado en la tabla de la actividad BusinessMessageJournal, puesto que está registrado por el componente de canalización personalizado. También puede buscar un registro del conjunto de transacciones en la tabla TransactionSetActivity.  
  
## <a name="querying-businessmessagejournal"></a>Consultar BusinessMessageJournal  
 Si el informe del conjunto de transacciones está habilitado, y conoce el BTSInterchangeID del intercambio recibido, puede usar la siguiente consulta SQL para obtener más información sobre el BTSInterchangeID del lote que contiene el conjunto de transacciones enviado a la orquestación de procesamiento por lotes. Con este código, podrá crear una aplicación personalizada para obtener visibilidad en los mensajes de un lote.  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creará entradas en la actividad BusinessMessageJournal solo si el informe de estado de EDI y el seguimiento del conjunto de transacciones están habilitados para el acuerdo.  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a>Vea también  
 [Actividades BAM creadas para realizar un seguimiento de mensajes EDI-AS2](../core/bam-activities-created-to-track-edi-as2-messages.md)   
 [Habilitar informes de estado de AS2 y EDI](../core/enabling-edi-and-as2-status-reports.md)