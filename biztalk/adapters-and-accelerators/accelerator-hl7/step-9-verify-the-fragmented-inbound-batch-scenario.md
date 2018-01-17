---
title: 'Paso 9: Compruebe el escenario fragmentados por lotes entrantes | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ba61866-2e1b-49e2-be57-ef281407d0a5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47d5ec8ffa7a7875af7073e60d6578149d532a7a
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-9-verify-the-fragmented-inbound-batch-scenario"></a>Paso 9: Compruebe el escenario fragmentados por lotes entrantes
En este paso, compruebe el escenario fragmentado por lotes de entrada.  
  
 Comprobando el escenario implica el uso de las siguientes herramientas:  
  
-   **Herramienta de MllpSend**, que se utiliza desde la línea de comandos para enviar un mensaje por lotes para el puerto de recepción.  
  
-   **Herramienta de MllpReceive**, que se utiliza desde la línea de comandos para comprobar la recepción de los mensajes individuales (como contenido en el lote) desde el puerto de envío. Esta instancia de la herramienta MllpReceive funciona como una aplicación de línea de negocio simulada. En la recepción de los mensajes, también genera una confirmación hacia el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de integración.  
  
-   Una segunda instancia de la herramienta MllpReceive, que se usa para comprobar la recepción de confirmaciones desde el puerto de envío.  
  
### <a name="to-test-the-fragmented-inbound-batch-scenario"></a>Para probar el escenario fragmentado por lotes de entrada  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **símbolo**.  
  
2.  En el símbolo del sistema, vaya a  **\< *unidad*\>: \Program BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**.  
  
3.  En el símbolo del sistema, escriba **mllpreceive /p 41000/SB 11 /eb 28 /cr 13 /hl7ack "\<*unidad*\>: \Program BizTalk \<versión\> Acelerador para HL7\Samples\Sample aplicación acepte ACK.txt**y, a continuación, presione **ENTRAR**. La ventana de símbolo del sistema entra en estado de espera hasta que realice el paso 5 y el sistema recibe la entrada.  
  
    > [!NOTE]
    >  El comando en el paso 3 ejecuta la aplicación de agente de escucha MLLP que escucha el puerto 41000. Este puerto está asociado con el puerto de envío que envía mensajes (como se crearon en [paso 5: crear un puerto de envío para entregar mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)). La herramienta MllpReceive actúa como la aplicación de línea de negocio que recibe los mensajes y envía la confirmación (ACK) al BTAHL7 (como contenido en el archivo de ejemplo ACK.txt de aceptación de aplicación de ejemplo). La herramienta muestra los mensajes devueltos a él en la ventana de símbolo del sistema. El comando en el paso 3 especifica los caracteres EB, SB y CR predeterminado del mensaje MLLP.  
  
4.  Repita los pasos 1 y 2 para abrir otra ventana del símbolo del sistema y desplácese al directorio de utilidades de MLLP. En el símbolo del sistema, escriba **mllpreceive /p 41002**y, a continuación, presione **ENTRAR**. La ventana de símbolo del sistema entra en estado de espera hasta que realice el paso 5 y el sistema recibe la salida.  
  
    > [!NOTE]
    >  El comando en el paso 4 ejecuta la aplicación de agente de escucha MLLP escuchar al puerto 41002. Este puerto está asociado con el puerto de envío que ofrece confirmaciones hacia el origen del mensaje de lote (como se crearon en [paso 6: crear un puerto de envío para entregar confirmaciones](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)). La herramienta MllpReceive actúa como la aplicación de línea de negocio que envió el lote original. La herramienta muestra confirmaciones devueltas a él en la ventana de símbolo del sistema. El comando en el paso 4 especifica los caracteres EB, SB y CR predeterminado del mensaje MLLP.  
  
5.  Repita los pasos 1 y 2 para abrir otra ventana del símbolo del sistema y desplácese al directorio de utilidades de MLLP. En el símbolo del sistema, escriba **mllpsend /twoway/SB 11 /eb 28 /cr 13 /f "\<*unidad*\>: \Batching Tutorial\Instances\FragmentedInboundBatch.txt" /p 21000**, donde \< *unidad* \> es la letra de unidad de instalación y, a continuación, presione **ENTRAR**.  
  
    > [!NOTE]
    >  El comando en el paso 5 simula el envío del mensaje original por lotes para el puerto de recepción. La consola debería mostrar "mensaje enviados: 1", que indica que la herramienta MllpSend envió el mensaje de lote único. Si no se muestra "mensaje enviados: 1", compruebe el Visor de eventos. Compruebe el texto del comando especificado en el paso 5, a continuación, solucionar problemas de la configuración de envío y puertos de recepción y el estado de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y BTAHL7.  
  
### <a name="to-verify-the-results-of-the-fragmented-inbound-batch-tutorial"></a>Para comprobar los resultados del Tutorial de lote de entrada fragmentado  
  
1.  Compruebe que, tras un breve retraso, la herramienta MllpReceive realizar escuchas de mensajes en el puerto 41000 muestra el contenido de los mensajes individuales fragmentado del lote y envía a la entidad Tutorial_BatchSource. El contenido de los dos mensajes debe ser como sigue:  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT^A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT^A03|000002|Tutorial_BatchSource|MESA_IS|  
  
2.  Compruebe que, tras un breve retraso, la herramienta MllpReceive realizando escuchas para las confirmaciones en el puerto 41002 muestra el contenido de las dos confirmaciones devueltos desde el motor de integración de BTAHL7 para el origen del lote. El contenido de las dos confirmaciones debe ser como sigue:  
  
    |MSH.9|MSH.3|MSH.5|MSA.2|MSA.1|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK^A03^ACK|MESA_IS|Tutorial_BatchSource|000001|AA|  
    |ACK^A03^ACK|MESA_IS|Tutorial_BatchSource|000002|AA|  
  
## <a name="see-also"></a>Vea también  
 [Parte 2: Lote / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)