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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b932ab2f179faab1381609c007dcdd148f200f7e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="step-10-verify-the-interrogative-scenario"></a>Paso 10: Comprobar el escenario Interrogative
En este paso, comprobará el escenario de extremo a extremo para este tutorial.  
  
### <a name="to-send-the-query-message"></a>Para enviar el mensaje de consulta  
  
1.  Abra un símbolo del sistema.  
  
2.  En el símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**.  
  
3.  En el símbolo del sistema, escriba **MllpReceive /P 24000**y, a continuación, presione **ENTRAR**. Esto ejecuta la aplicación de agente de escucha MLLP escuchar al puerto 24000 y muestra cualquier mensaje recibido en la pantalla. Esta aplicación simula el sistema de información de salud.  
  
4.  Abra un símbolo del sistema adicional.  
  
5.  En la segunda ventana de símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**.  
  
6.  En la segunda ventana del símbolo del sistema, escriba **MllpSend/SB 11 /EB 28 /CR 13/TWOWAY /P 22000 /F "\<*unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Tutorial\QRY^Q01.txt**y, a continuación, presione **ENTRAR.**  
  
    > [!NOTE]
    >  Este comando envía el mensaje de consulta que creó al principio de este tutorial para el puerto MLLP 22000 y espera una respuesta (confirmación). El ADT puerto recoge este mensaje de recepción y lo procesa.  
  
7.  Compruebe que dispone de los siguientes resultados:  
  
    -   La aplicación de agente de escucha MLLP debe mostrar un mensaje con los siguientes valores:  
  
        ```  
        MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        ```  
  
    -   Además, la utilidad MllpSend crea un archivo de confirmación en el \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\ Carpeta de Tutorial interrogative denominada QRY^Q01.txt.RESPONSE. Este archivo contiene la siguiente información como la confirmación:  
  
        ```  
        MSH|^~\&|HIS||ADT||20040331154031.2222-0800||ACK^Q01^ACK|10000GSM|P|2.4  
        MSA|CA|MSG00001  
        ****END ACK****  
        ```  
  
### <a name="to-send-the-response-message"></a>Para enviar el mensaje de respuesta  
  
1.  En la línea de comandos que se ejecuta la aplicación MllpReceive, presione **Ctrl-C** para cancelar la operación anterior.  
  
2.  En el símbolo del sistema, escriba **MllpReceive /P 25000**y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  Paso 2 ejecuta la aplicación de agente de escucha MLLP escuchar al puerto 25000 y muestra todos los mensajes recibidos a la pantalla. Esta aplicación simula el sistema ADT.  
  
3.  En la segunda ventana del símbolo del sistema, escriba **MllpSend/SB 11 /EB 28 /CR 13 /P 23000 /F "\<*unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\SDK\Interrogative Tutorial\DSR.txt"**, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  Paso 3 envía el mensaje de respuesta que creó al principio de este tutorial para el puerto MLLP 23000. El HIS puerto recoge este mensaje de recepción y lo procesa.  
  
4.  Compruebe que dispone de los siguientes resultados:  
  
    -   La aplicación de agente de escucha MLLP debe mostrar un mensaje con los siguientes valores:  
  
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
    >  Si los mensajes anteriores no aparezcan correctamente, utilice la herramienta de mantenimiento y seguimiento de actividad (HAT) para solucionar el error.  
  
 ¡Enhorabuena! Ha completado correctamente el Tutorial Interrogative BTAHL7.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de procesamiento por lotes](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [Tutorial de extremo a extremo](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)   
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)