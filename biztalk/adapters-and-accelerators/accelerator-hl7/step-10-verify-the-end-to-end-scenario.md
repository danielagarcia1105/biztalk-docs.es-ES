---
title: 'Paso 10: Comprobar el escenario de extremo a otro | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43d95e54bbcf0c7c716630305b85ba8b9bed1a52
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990349"
---
# <a name="step-10-verify-the-end-to-end-scenario"></a>Paso 10: Comprobar el escenario de extremo a otro
En este paso, comprobará el escenario de extremo a otro para este tutorial.  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a>Para comprobar el escenario del tutorial-to-end  
  
1. Haga clic en **iniciar**, apunte a **programas**, apunte a **Accesorios**y, a continuación, haga clic en **símbolo**.  
  
2. En la ventana de símbolo del sistema, desplácese a  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**y, a continuación, presione **ENTRAR**.  
  
   > [!NOTE]
   >  Si no encuentra una carpeta de utilidades de MLLP bajo la carpeta del SDK, no pueden instalarse las herramientas de prueba MLLP. Abra el Panel de Control y, a continuación, abra **agregar o quitar programas**. Seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, seleccione **cambio**. En el Asistente para instalación de BTAHL7, seleccione **modificar**. Expanda el **adaptador** carpeta para ver si el **herramienta de prueba de MLLP** se ha instalado. Si no es así, instálelo.  
  
3. En la ventana de símbolo del sistema, escriba **mllpreceive /p 14000**y, a continuación, presione **ENTRAR**. Esto ejecuta la aplicación de agente de escucha MLLP escuchar el puerto 14000 y especificar los caracteres de CR, SB y EB predeterminado del mensaje MLLP y muestra todos los mensajes recibidos en la pantalla.  
  
4. Inicie un símbolo del sistema adicional haciendo **iniciar**, apunte a **programas**, apunte a **Accesorios**y, a continuación, haga clic en **símbolo**.  
  
5. En la segunda ventana de símbolo del sistema, desplácese a  **\< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para utilidades HL7\SDK\MLLP**y, a continuación, presione **ENTRAR**.  
  
   > [!NOTE]
   >  El paso siguiente, envía el mensaje.  
  
6. En la ventana de símbolo del sistema, escriba **mllpsend/SB 11 /EB 28 /CR 13 /f "\<*unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\ To-End Tutorial\ADT ^ A03.txt "**, donde \< *unidad* \> es la letra de unidad de instalación. Presione **ENTRAR**.  
  
7. Compruebe que dispone de los siguientes resultados:  
  
   -   La aplicación de agente de escucha MLLP debe mostrar un mensaje. La primera línea del mensaje debe tener los siguientes valores:  
  
       ```  
       MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
       ```  
  
   -   Aparece un mensaje en \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para Tutorial\Tutorial_sendMsg_RX HL7\SDK\End-to-End. Este mensaje debe ser el mismo que el mensaje que se muestra en la aplicación de agente de escucha MLLP. Compruebe que la primera línea del mensaje tiene los mismos valores de mensaje como se indica a continuación. Tenga en cuenta que los valores de MSH3 un nd MSH5 en el código siguiente coincide con los valores especificados para el Tutorial_RXSystem:  
  
       ```  
       MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
       ```  
  
   -   Aparecen dos mensajes en \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para Tutorial\Tutorial_sendAck_ADT HL7\SDK\End-to-End. Uno de estos mensajes es una confirmación de la aplicación; el otro es una confirmación de confirmación. La confirmación de la aplicación debe tener el siguiente contenido:  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
       MSA|AA|000001  
       ```  
  
   -   La confirmación de la confirmación debe tener el siguiente contenido:  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
       MSA|CA|000001  
       ```  
  
   > [!NOTE]
   >  Si los mensajes no aparecen correctamente, utilice la herramienta de mantenimiento y seguimiento de actividad (HAT) para solucionar el error.  
  
   ¡Enhorabuena! Ha completado correctamente el Tutorial de BTAHL7-to-End.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial integral](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)