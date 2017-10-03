---
title: Preparando para utilizar el Tutorial2 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: end-to-end tutorial, pre-requisites
ms.assetid: 88e6c0b5-5f7d-4fee-a4de-7922cfba917f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a957bd18fd6defad40d6b04e91bc3028802da1c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="preparing-to-use-the-tutorial"></a>Preparando para utilizar el Tutorial
Antes de utilizar el tutorial, debe crear un archivo ADT^A03.txt.  
  
### <a name="to-create-the-adta03txt-file"></a>Para crear el archivo ADT^A03.txt  
  
1.  Abra un editor como el Bloc de notas y copie el texto siguiente en el editor:  
  
    ```  
    MSH|^~\&|Tutorial_ADTSystem|MCM|BTAHL7InterfaceEngine||199601121005||ADT^A03|000001|P|2.3.1  
    EVN|A03|199601121005||01||199601121000  
    PID|||191919^^^MYHOS^MR~123-45-6789^^^USSSA^SS|253763|SMITH^JOHN^Q||19560129|M|||  
        123MAIN^^BUFFALO^NY^98052^""||(123)555-0100||S|M|10199925^^^MYHOS^AN|123-45-6789  
    PD1|S|F|NormalString^A^+1^-1^ISO^simpletext&Test&HCD^GI^simpletext&NormalString&ISO^I|  
       NormalString^Test&Test^Test^Test^Test^Test^AE^simpletext^simpletext&Test&ISO^P  
       ^NormalString^M10^MC^simpletext&NormalString&HCD^A|N|simpletext|I|I|N|NormalString  
       ^+1^M11^simpletext&NormalString&L,M,N^RRI^simpletext&NormalString&HCD|NOVALUE^NormalString  
       ^Test^Test^NormalString^Test|N  
    PV1|1|I|2000^2012^01^hey&test&DNS^test^test^test^test^test||||004777^MILLER^CONNIE^A.|||SUR||||2|A0  
    ```  
  
    > [!NOTE]
    >  Debería haber cinco líneas en el .txt, archivo, cada uno a partir de "MSH", "EVN", "PID", "PD1" y "PV1". Debe quitar los espacios en la línea "PID" y la línea "PD1". Si es necesario, desactive el ajuste automático de línea en el Bloc de notas.  
  
2.  Guarde el archivo como **ADT^A03.txt** en el \< *unidad*>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión > Accelerator for HL7\SDK\End-to-End Carpeta tutorial y, a continuación, cierre el Bloc de notas.  
  
 Continúe con [paso 1: crear e implementar esquemas de confirmación y de encabezado](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md).