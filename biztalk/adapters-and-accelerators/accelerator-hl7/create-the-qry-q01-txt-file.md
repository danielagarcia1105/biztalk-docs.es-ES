---
title: Crear el archivo QRY^Q01.txt | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ac96587-264f-4743-a90b-4763d330e320
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57380a36759d9cf0139f295779b8e1f2628c554f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-qryq01txt-file"></a>Crear el archivo QRY^Q01.txt
Utilice el procedimiento siguiente para crear el archivo de mensaje de consulta paciente QRY^Q01.txt. Más adelante usará este archivo para comprobar el escenario del tutorial.  
  
### <a name="to-create-the-qryq01txt-file"></a>Para crear el archivo QRY^Q01.txt  
  
1.  Abra un editor, como el Bloc de notas y copie el texto siguiente en el editor:  
  
    ```  
    MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
    QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
    ```  
  
2.  Guarde el archivo como **QRY^Q01.txt** en el \< *unidad*: > \Program BizTalk \<versión > Accelerator for carpeta HL7\SDK\Interrogative Tutorial y, a continuación, Cierre el editor.  
  
 Continúe con [crear el archivo DSR.txt](../../adapters-and-accelerators/accelerator-hl7/create-the-dsr-txt-file.md).