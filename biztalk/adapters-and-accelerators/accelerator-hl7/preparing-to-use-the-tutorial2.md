---
title: Preparación para usar el Tutorial2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, pre-requisites
ms.assetid: 88e6c0b5-5f7d-4fee-a4de-7922cfba917f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d790a53576c4f153265531fca974089eb5292a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978661"
---
# <a name="preparing-to-use-the-tutorial"></a>Preparación para usar el Tutorial
Antes de usar el tutorial, deberá crear un archivo ADT^A03.txt.  
  
### <a name="to-create-the-adta03txt-file"></a>Para crear el archivo ADT^A03.txt  
  
1. Abra un editor como el Bloc de notas y copie el texto siguiente en el editor:  
  
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
   >  Debería haber cinco líneas en .txt, el archivo, cada uno a partir de "MSH", "EVN", "PID", "PD1" y "PV1". Deberá quitar los espacios dentro de la línea "PID" y la línea "PD1". Si es necesario, desactive la opción de ajuste de línea en el Bloc de notas.  
  
2. Guarde el archivo como **ADT^A03.txt** en el \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para Carpeta Tutorial HL7\SDK\End-to-End y, a continuación, cierre el Bloc de notas.  
  
   Continúe con [paso 1: crear e implementar esquemas de encabezado y confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md).