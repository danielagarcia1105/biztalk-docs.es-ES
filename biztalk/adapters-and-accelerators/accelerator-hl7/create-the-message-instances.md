---
title: Crear las instancias de mensaje | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d75cb744-99a0-44bc-9a84-d4f8f66fd97e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfd39e1da4e8c730e2ca1c663a5844355ac9cd08
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960218"
---
# <a name="create-the-message-instances"></a>Crear las instancias de mensaje
Utilice los procedimientos siguientes para crear el archivo de mensaje ADT^A03.txt y para crear las instancias de mensaje que debe usar al ejecutar el tutorial de procesamiento por lotes.  
  
> [!NOTE]
>  Al crear estos mensajes en el Bloc de notas, elimine el después de la última línea retorno de carro.  
  
### <a name="to-create-the-fragmented-batch-message-instance-text-file"></a>Para crear el archivo de texto de instancia de mensaje de lote fragmentado  
  
1.  Abra el Bloc de notas.  
  
2.  Copie el texto siguiente en el Bloc de notas:  
  
    ```  
    FHS|^~\&|Tutorial_BatchSource|FileSendingFacility|Tutorial_BatchParty|FileReceivingFacility|20040215115056.2222-0800  
    BHS|^~\&|Tutorial_BatchSource|BatchSendingFacility|Tutorial_BatchParty|BatchReceivingFacility|20040215115056.2222-0800  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000002|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    BTS|2|Batch,MessageCount,Comment,Totals|2  
    FTS|1|File,BatchCount,TrailerComment  
    ```  
  
3.  Guarde el archivo como **FragmentedInboundBatch.txt** en el \< *unidad*:\>\Batching Tutorial\Instances carpeta y, a continuación, cierre el Bloc de notas.  
  
### <a name="to-create-the-batch-inbatch-out-message-instance-text-file"></a>Para crear el lote / archivo de instancia de mensaje de texto de lote  
  
1.  Abra el Bloc de notas.  
  
2.  Copie el texto siguiente en el Bloc de notas:  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|MESA_IS|XYZ_HOSPITAL|20040215115056||ADT^A03|000002|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    ```  
  
3.  Guarde el archivo como **BatchInBatchOut.txt** en el \< *unidad*:\>\Batching Tutorial\Instances carpeta y, a continuación, cierre el Bloc de notas.  
  
### <a name="to-create-the-create-batch-message-instance-text-files"></a>Para crear la instancia de mensaje de lote de crear archivos de texto  
  
1.  Abra el Bloc de notas.  
  
2.  Copie el texto siguiente en el Bloc de notas:  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|Tutorial_BatchDest|XYZ_HOSPITAL|20040215115056||ADT^A03|Msg01|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    ```  
  
3.  Guarde el archivo como **CreateBatchMessage1.txt** en el \< *unidad*:\>\Batching Tutorial\Instances carpeta y, a continuación, cierre el Bloc de notas.  
  
4.  Copie el texto siguiente en una nueva instancia del Bloc de notas:  
  
    ```  
    MSH|^~\&|Tutorial_BatchSource|XYZ_ADMITTING|Tutorial_BatchDest|XYZ_HOSPITAL|20040215115056||ADT^A03|Msg02|T|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|DOE^JOHN||19560129|M|||123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|String^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^JDL&test&DNS^test^test^test^test^test||||004777^DOE^JANE^A.|||SUR||||2|A0  
    ```  
  
5.  Guarde el archivo como **CreateBatchMessage2.txt** en el \< *unidad*:\>\Batching Tutorial\Instances carpeta y, a continuación, cierre el Bloc de notas.  
  
 Continúe con [parte 1: fragmentado por lotes entrantes escenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md).