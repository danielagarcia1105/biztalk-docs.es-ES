---
title: 'Paso 10: Comprobar el escenario Interrogative | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, verifying solution
ms.assetid: 1f28800b-4a1d-4f29-8123-5cdea4b4a365
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b932ab2f179faab1381609c007dcdd148f200f7e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25961250"
---
# <a name="step-10-verify-the-interrogative-scenario"></a><span data-ttu-id="eeea1-102">Paso 10: Comprobar el escenario Interrogative</span><span class="sxs-lookup"><span data-stu-id="eeea1-102">Step 10: Verify the Interrogative Scenario</span></span>
<span data-ttu-id="eeea1-103">En este paso, comprobará el escenario de extremo a extremo para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="eeea1-103">In this step, you verify the end-to-end scenario for this tutorial.</span></span>  
  
### <a name="to-send-the-query-message"></a><span data-ttu-id="eeea1-104">Para enviar el mensaje de consulta</span><span class="sxs-lookup"><span data-stu-id="eeea1-104">To send the query message</span></span>  
  
1.  <span data-ttu-id="eeea1-105">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="eeea1-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="eeea1-106">En el símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**.</span><span class="sxs-lookup"><span data-stu-id="eeea1-106">In the command prompt, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**.</span></span>  
  
3.  <span data-ttu-id="eeea1-107">En el símbolo del sistema, escriba **MllpReceive /P 24000**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="eeea1-107">In the command prompt, type **MllpReceive /P 24000**, and then press **Enter**.</span></span> <span data-ttu-id="eeea1-108">Esto ejecuta la aplicación de agente de escucha MLLP escuchar al puerto 24000 y muestra cualquier mensaje recibido en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="eeea1-108">This runs the MLLP listener application listening to port 24000 and displays any messages received to the screen.</span></span> <span data-ttu-id="eeea1-109">Esta aplicación simula el sistema de información de salud.</span><span class="sxs-lookup"><span data-stu-id="eeea1-109">This application is simulating the Hospital Information System.</span></span>  
  
4.  <span data-ttu-id="eeea1-110">Abra un símbolo del sistema adicional.</span><span class="sxs-lookup"><span data-stu-id="eeea1-110">Open an additional command prompt.</span></span>  
  
5.  <span data-ttu-id="eeea1-111">En la segunda ventana de símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**.</span><span class="sxs-lookup"><span data-stu-id="eeea1-111">In the second Command Prompt window, move to **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities**.</span></span>  
  
6.  <span data-ttu-id="eeea1-112">En la segunda ventana del símbolo del sistema, escriba **MllpSend/SB 11 /EB 28 /CR 13/TWOWAY /P 22000 /F "\<*unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**y, a continuación, presione **ENTRAR.**</span><span class="sxs-lookup"><span data-stu-id="eeea1-112">In the second command prompt, type **MllpSend /SB 11 /EB 28 /CR 13 /TWOWAY /P 22000 /F "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**, and then press **Enter.**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eeea1-113">Este comando envía el mensaje de consulta que creó al principio de este tutorial para el puerto MLLP 22000 y espera una respuesta (confirmación).</span><span class="sxs-lookup"><span data-stu-id="eeea1-113">This command sends the query message you created at the beginning of this tutorial to MLLP port 22000 and waits for a response (acknowledgment).</span></span> <span data-ttu-id="eeea1-114">El ADT puerto recoge este mensaje de recepción y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="eeea1-114">The ADT receive port picks up this message and processes it.</span></span>  
  
7.  <span data-ttu-id="eeea1-115">Compruebe que dispone de los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="eeea1-115">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="eeea1-116">La aplicación de agente de escucha MLLP debe mostrar un mensaje con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="eeea1-116">The MLLP listener application should display a message with the following values:</span></span>  
  
        ```  
        MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        ```  
  
    -   <span data-ttu-id="eeea1-117">Además, la utilidad MllpSend crea un archivo de confirmación en el \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\ Carpeta de Tutorial interrogative denominada QRY^Q01.txt.RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="eeea1-117">In addition, the MllpSend utility creates an acknowledgment file in the \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial folder named QRY^Q01.txt.RESPONSE.</span></span> <span data-ttu-id="eeea1-118">Este archivo contiene la siguiente información como la confirmación:</span><span class="sxs-lookup"><span data-stu-id="eeea1-118">This file contains the following information as the acknowledgment:</span></span>  
  
        ```  
        MSH|^~\&|HIS||ADT||20040331154031.2222-0800||ACK^Q01^ACK|10000GSM|P|2.4  
        MSA|CA|MSG00001  
        ****END ACK****  
        ```  
  
### <a name="to-send-the-response-message"></a><span data-ttu-id="eeea1-119">Para enviar el mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="eeea1-119">To send the response message</span></span>  
  
1.  <span data-ttu-id="eeea1-120">En la línea de comandos que se ejecuta la aplicación MllpReceive, presione **Ctrl-C** para cancelar la operación anterior.</span><span class="sxs-lookup"><span data-stu-id="eeea1-120">In the command prompt running the MllpReceive application, press **Ctrl-C** to cancel the previous operation.</span></span>  
  
2.  <span data-ttu-id="eeea1-121">En el símbolo del sistema, escriba **MllpReceive /P 25000**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="eeea1-121">At the command prompt, type **MllpReceive /P 25000**, and then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eeea1-122">Paso 2 ejecuta la aplicación de agente de escucha MLLP escuchar al puerto 25000 y muestra todos los mensajes recibidos a la pantalla.</span><span class="sxs-lookup"><span data-stu-id="eeea1-122">Step 2 runs the MLLP listener application listening to port 25000 and displays any messages received to the screen.</span></span> <span data-ttu-id="eeea1-123">Esta aplicación simula el sistema ADT.</span><span class="sxs-lookup"><span data-stu-id="eeea1-123">This application is simulating the ADT system.</span></span>  
  
3.  <span data-ttu-id="eeea1-124">En la segunda ventana del símbolo del sistema, escriba **MllpSend/SB 11 /EB 28 /CR 13 /P 23000 /F "\<*unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Tutorial\DSR.txt"**, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="eeea1-124">In the second command prompt, type **MllpSend /SB 11 /EB 28 /CR 13 /P 23000 /F "\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial\DSR.txt"**, then press **Enter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eeea1-125">Paso 3 envía el mensaje de respuesta que creó al principio de este tutorial para el puerto MLLP 23000.</span><span class="sxs-lookup"><span data-stu-id="eeea1-125">Step 3 sends the response message you created at the beginning of this tutorial to MLLP port 23000.</span></span> <span data-ttu-id="eeea1-126">El HIS puerto recoge este mensaje de recepción y lo procesa.</span><span class="sxs-lookup"><span data-stu-id="eeea1-126">The HIS receive port picks up this message and processes it.</span></span>  
  
4.  <span data-ttu-id="eeea1-127">Compruebe que dispone de los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="eeea1-127">Verify that you have the following results:</span></span>  
  
    -   <span data-ttu-id="eeea1-128">La aplicación de agente de escucha MLLP debe mostrar un mensaje con los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="eeea1-128">The MLLP listener application should display a message with the following values:</span></span>  
  
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
  
    > [!NOTE]
    >  <span data-ttu-id="eeea1-129">Si los mensajes anteriores no aparezcan correctamente, utilice la herramienta de mantenimiento y seguimiento de actividad (HAT) para solucionar el error.</span><span class="sxs-lookup"><span data-stu-id="eeea1-129">If the messages above do not appear correctly, use the Health and Activity Tracking (HAT) tool to troubleshoot the error.</span></span>  
  
 <span data-ttu-id="eeea1-130">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="eeea1-130">Congratulations!</span></span> <span data-ttu-id="eeea1-131">Ha completado correctamente el Tutorial Interrogative BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="eeea1-131">You have successfully completed the BTAHL7 Interrogative Tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeea1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="eeea1-132">See Also</span></span>  
 <span data-ttu-id="eeea1-133">[Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="eeea1-133">[Batching Tutorial](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md) </span></span>  
 <span data-ttu-id="eeea1-134">[Tutorial de extremo a extremo](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md) </span><span class="sxs-lookup"><span data-stu-id="eeea1-134">[End-to-End Tutorial](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md) </span></span>  
 [<span data-ttu-id="eeea1-135">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="eeea1-135">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)