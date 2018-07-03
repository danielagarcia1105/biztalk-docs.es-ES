---
title: Crear el archivo DSR.txt | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6947af7-c5ce-4ee6-9fe9-5c1094d0aee0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f5fd535b1a4db0a960c8f993cd6daf22ee9d1b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976885"
---
# <a name="create-the-dsrtxt-file"></a>Crear el archivo DSR.txt
Use el procedimiento siguiente para crear el archivo de mensaje de respuesta DSR.txt. Más adelante usará este archivo para comprobar el escenario del tutorial.  
  
### <a name="to-create-the-dsrtxt-file"></a>Para crear el archivo DSR.txt  
  
1. Abra un editor, como el Bloc de notas y copie el texto siguiente en el editor:  
  
   ```  
   MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
   MSA|AA|MSG00003  
   QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
   DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
   DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
   DSP|||ELECTROLYTES  
   DSP||| SODIUM 136 [135-148] MEQ/L STAT  
   DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
   DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
   DSP||| CO2 25 [20-30] MEQ/L STAT  
   DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
   ```  
  
2. Guarde el archivo como **DSR.txt** en el \< *unidad*:\>\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Carpeta tutorial y, a continuación, cierre el editor.  
  
   Continúe con [paso 1: crear e implementar esquemas de confirmación y de encabezado común](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md).