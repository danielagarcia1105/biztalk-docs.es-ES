---
title: Crear el archivo DSR.txt | Documentos de Microsoft
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
ms.openlocfilehash: 69520639040893aad7f46b29760343afa68073fc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960778"
---
# <a name="create-the-dsrtxt-file"></a><span data-ttu-id="055f0-102">Crear el archivo DSR.txt</span><span class="sxs-lookup"><span data-stu-id="055f0-102">Create the DSR.txt File</span></span>
<span data-ttu-id="055f0-103">Utilice el procedimiento siguiente para crear el archivo de mensaje de respuesta DSR.txt.</span><span class="sxs-lookup"><span data-stu-id="055f0-103">Use the following procedure to create the response DSR.txt message file.</span></span> <span data-ttu-id="055f0-104">Más adelante usará este archivo para comprobar el escenario del tutorial.</span><span class="sxs-lookup"><span data-stu-id="055f0-104">You will use this file later to verify the tutorial scenario.</span></span>  
  
### <a name="to-create-the-dsrtxt-file"></a><span data-ttu-id="055f0-105">Para crear el archivo DSR.txt</span><span class="sxs-lookup"><span data-stu-id="055f0-105">To create the DSR.txt file</span></span>  
  
1.  <span data-ttu-id="055f0-106">Abra un editor, como el Bloc de notas y copie el texto siguiente en el editor:</span><span class="sxs-lookup"><span data-stu-id="055f0-106">Open an editor, such as Notepad, and copy the following text into the editor:</span></span>  
  
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
  
2.  <span data-ttu-id="055f0-107">Guarde el archivo como **DSR.txt** en el \< *unidad*:\>\Program BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Carpeta tutorial y a continuación, cierre el editor.</span><span class="sxs-lookup"><span data-stu-id="055f0-107">Save the file as **DSR.txt** in the \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder, and then close the editor.</span></span>  
  
 <span data-ttu-id="055f0-108">Continúe con [paso 1: crear e implementar encabezado común y esquemas de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="055f0-108">Proceed to [Step 1: Create and Deploy Common Header and Acknowledgment Schemas](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md).</span></span>