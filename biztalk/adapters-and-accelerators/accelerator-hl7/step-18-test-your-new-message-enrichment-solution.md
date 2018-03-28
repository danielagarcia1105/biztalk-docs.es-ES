---
title: 'Paso 18: Probar la nueva solución de enriquecimiento de mensajes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, testing solution
ms.assetid: 233fbf79-0ab1-4064-b828-6bbbb56cbec2
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 035925684617e74608246aed99fa98e16d0668a4
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="step-18-test-your-new-message-enrichment-solution"></a>Paso 18: Probar la nueva solución de enriquecimiento de mensajes
En este paso, probará la solución mediante la aplicación WSClient para enviar un mensaje a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y ver si la aplicación MLLPReceive recibe un mensaje con formato HL7 según lo previsto.  
  
### <a name="to-test-your-solution"></a>Para probar la solución  
  
1.  Abra un símbolo del sistema.  
  
    > [!NOTE]
    >  Paso 2 requiere que se haya instalado la herramienta de prueba de MLLP mediante el procedimiento de instalación personalizada. Si las utilidades \MLLP directorio que contiene MllpReceive.exe y MllpSend.exe no existe en el equipo, instálelos mediante la realización de una instalación personalizada. Para obtener información, consulte [realizar una instalación personalizada](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692).  
  
2.  En el símbolo del sistema, escriba **cd \< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP** () donde \< *unidad* \> es la letra de unidad de instalación) y, a continuación, presione **ENTRAR**.  
  
3.  En el símbolo del sistema, escriba **mllpreceive /p 11000 /eb 11/SB 28 /cr 13**y, a continuación, presione **ENTRAR**. Esto ejecuta la aplicación de agente de escucha MLLP escuchando al puerto 11000 y especificar los caracteres EB, SB y CR predeterminado del mensaje MLLP y muestra cualquier mensaje recibido en la pantalla.  
  
4.  Abra una segunda línea de comandos.  
  
5.  En el símbolo del sistema, escriba **cd \< *unidad*\>: \Tutorial\WSClient\bin\Debug**y, a continuación, presione **ENTRAR**.  
  
6.  En el símbolo del sistema, escriba **smith henry de john wsclient 123456789**y, a continuación, presione **ENTRAR**. Esto envía un mensaje al servicio Web que contiene un mensaje de ejemplo con el nombre de un paciente de John Henry Smith y un número de seguridad social de ejemplo de 123456789.  
  
7.  Tras una breve pausa, la aplicación MLLPReceive muestra el mensaje entrante de MLLP. El mensaje debe ser similar al siguiente:  
  
    ```  
    MSH|^~\&|TestTrailing^Delimiters|srcFac^srcFacUid|dstApp^dstAppUid|dstFac^dstFacUid|200307092343|sec|ADT^A04|msgid2134|P|2.2PID|||123456789||smith^john  
    ```  
  
     Si no recibe una respuesta después de unos minutos, debe comprobar el registro de eventos de aplicación para los errores y empezar a solucionar problemas.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)