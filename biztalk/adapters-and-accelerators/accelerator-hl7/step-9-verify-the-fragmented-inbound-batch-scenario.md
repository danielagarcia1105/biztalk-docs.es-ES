---
title: 'Paso 9: Comprobar el escenario de lote de entrada fragmentado | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ba61866-2e1b-49e2-be57-ef281407d0a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dce0f283695af423b96c07103a1c2f5837cf4b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970679"
---
# <a name="step-9-verify-the-fragmented-inbound-batch-scenario"></a>Paso 9: Comprobar el escenario de lote de entrada fragmentado
En este paso, compruebe el escenario de lote de entrada fragmentado.  
  
 Comprobar el escenario implica el uso de las siguientes herramientas:  
  
- **Herramienta MllpSend**, que usa la línea de comandos para enviar un mensaje por lotes para el puerto de recepción.  
  
- **Herramienta MllpReceive**, que se utiliza desde la línea de comandos para comprobar la recepción de los mensajes individuales (como contenido en el lote) desde el puerto de envío. Esta instancia de la herramienta MllpReceive funciona como una aplicación de línea de negocio simulada. En la recepción de los mensajes, también genera una confirmación a la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor de integración.  
  
- Una segunda instancia de la herramienta MllpReceive, que se utiliza para comprobar la recepción de confirmaciones desde el puerto de envío.  
  
### <a name="to-test-the-fragmented-inbound-batch-scenario"></a>Para probar el escenario de lote de entrada fragmentado  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Accesorios**y, a continuación, haga clic en **símbolo**.  
  
2. En el símbolo del sistema, vaya a  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**.  
  
3. En el símbolo del sistema, escriba **mllpreceive /p 41000/SB 11 /eb 28 /cr 13 /hl7ack "\<*unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\Samples\Sample aplicación acepte ACK.txt**y, a continuación, presione **ENTRAR**. La ventana de símbolo del sistema entra en estado de espera hasta que realice el paso 5 y el sistema recibe la entrada.  
  
   > [!NOTE]
   >  El comando en el paso 3 ejecuta la aplicación de agente de escucha MLLP que escucha el puerto 41000. Este puerto está asociado con el puerto de envío que envía mensajes (como se crearon en [paso 5: crear un puerto de envío para entregar mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)). La herramienta MllpReceive actúa como la aplicación de línea de negocio que recibe los mensajes y envía la confirmación (ACK) al BTAHL7 (como contenido en el archivo de ejemplo ACK.txt de aceptación de aplicación de ejemplo). La herramienta muestra los mensajes devueltos a él en la ventana de símbolo del sistema. El comando en el paso 3 especifica los caracteres de CR, SB y EB predeterminado del mensaje MLLP.  
  
4. Repita los pasos 1 y 2 para abrir otra ventana del símbolo del sistema y vaya al directorio utilidades de MLLP. En el símbolo del sistema, escriba **mllpreceive /p 41002**y, a continuación, presione **ENTRAR**. La ventana de símbolo del sistema entra en estado de espera hasta que realice el paso 5 y el sistema recibe la salida.  
  
   > [!NOTE]
   >  El comando en el paso 4 ejecuta la aplicación de agente de escucha MLLP escuchar el puerto 41002. Este puerto está asociado con el puerto de envío que ofrece las confirmaciones en el origen del mensaje por lotes (como se crearon en [paso 6: crear un puerto de envío para entregar confirmaciones](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)). La herramienta MllpReceive actúa como la aplicación de línea de negocio que envió el lote original. La herramienta muestra confirmaciones devueltas a él en la ventana de símbolo del sistema. El comando en el paso 4 especifica los caracteres de CR, SB y EB predeterminado del mensaje MLLP.  
  
5. Repita los pasos 1 y 2 para abrir otra ventana del símbolo del sistema y vaya al directorio utilidades de MLLP. En el símbolo del sistema, escriba **mllpsend /twoway/SB 11 /eb 28 /cr 13 /f "\<*unidad*\>: \Batching Tutorial\Instances\FragmentedInboundBatch.txt" /p 21000**, donde \< *unidad* \> es la letra de unidad de instalación y, a continuación, presione **ENTRAR**.  
  
   > [!NOTE]
   >  El comando en el paso 5 simula el envío del mensaje al puerto de recepción por lotes original. La consola debería mostrar "los mensajes enviados: 1", que indica que la herramienta MllpSend envió el mensaje de lote único. Si no se muestra "mensaje enviado: 1", compruebe el Visor de eventos. Compruebe el texto del comando especificado en el paso 5, a continuación, solucionar problemas de la configuración de envío y puertos de recepción y el estado de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] y BTAHL7.  
  
### <a name="to-verify-the-results-of-the-fragmented-inbound-batch-tutorial"></a>Para comprobar los resultados del Tutorial de lote de entrada fragmentado  
  
1.  Compruebe que, tras una breve demora, la herramienta MllpReceive escucha los mensajes en el puerto 41000 muestra el contenido de los mensajes individuales fragmentado del lote y envía a la entidad Tutorial_BatchSource. El contenido de los dos mensajes debe ser como sigue:  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
2.  Compruebe que, tras una breve demora, la herramienta MllpReceive escucha las confirmaciones en el puerto 41002 muestra el contenido de dos confirmaciones que se devuelve desde el motor de integración de BTAHL7 al origen del lote. El contenido de las dos confirmaciones debería ser como sigue:  
  
    |MSH.9|MSH.3|MSH.5|MSA.2|MSA.1|  
    |-----------|-----------|-----------|-----------|-----------|  
    |CONFIRMACIÓN ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|000001|AA|  
    |CONFIRMACIÓN ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|000002|AA|  
  
## <a name="see-also"></a>Vea también  
 [Parte 2: Proceso por lotes en / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [Parte 3: Escenario de creación de lote](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)