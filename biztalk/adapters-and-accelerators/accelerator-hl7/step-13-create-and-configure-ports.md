---
title: 'Paso 13: Crear y configurar puertos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 256b1618313605f0847d9328abfd003f41ac61cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-13-create-and-configure-ports"></a>Paso 13: Crear y configurar puertos
En este paso, usa al Asistente para configuración de puertos para crear y configurar puertos en el Diseñador de orquestaciones. Puertos especifican cómo la orquestación envía y recibe mensajes del servidor de procesos empresariales. Cada puerto tiene un tipo, una dirección y un enlace. Las propiedades de combinación determinan la dirección de comunicación, el patrón de comunicación, la ubicación a o desde el que [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] envía o recibe el mensaje y cómo tiene lugar la comunicación. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]usa el adaptador de protocolo de nivel inferior (MLLP) como mínimo como un puerto de envío. El adaptador MLLP utiliza la comunicación de sockets TCP para comunicarse con otras aplicaciones, como aplicaciones de laboratorio, aplicaciones seguros y las aplicaciones de línea de negocio heredadas. Representa el adaptador de envío de MLLP un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador:  
  
-   Personalizar. El adaptador sólo se distribuye con [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], en lugar de envío con [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].  
  
-   Protocolo/transporte. El adaptador no es un aplicación o adaptador de datos.  
  
-   Estático. La configuración del adaptador no implica una interfaz de usuario personalizada.  
  
-   Asincrónica. El adaptador no bloquea el subproceso de motor de mensajería, lo que permite un mayor rendimiento de todos los adaptadores que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hosts.  
  
-   Sin transacciones. El adaptador no es una recepción de transacción o enviar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adaptador.  
  
-   Regular. El adaptador no se ejecuta en un proceso de aplicación diferente.  
  
-   Unidireccionales y bidireccionales. El adaptador admite unidireccionales y de solicitud-respuesta o petición-respuesta modos de interacción.  
  
 El adaptador MLLP puede enviar mensajes individuales o mensajes en un lote. El principio de un mensaje MLLP se marca con un carácter de contenedor, 0x0b hexadecimal (también conocido como el bloque de inicio o SB carácter), y se marca el final del mensaje mediante la combinación de un carácter hexadecimal de 0x1c (también conocido como el carácter de bloque final o EB) inmediatamente seguido del carácter de 0x0d (retorno de carro). Contadores de rendimiento de BTAHL7 contar solo estos caracteres de contenedor para los mensajes enviados. Contadores de rendimiento de BTAHL7 no cuentan estos caracteres de contenedor al recibir mensajes.  
  
> [!NOTE]
>  El protocolo MLLP estándar no permite caracteres en 0 x 20 en la carga del mensaje puesto que interfiere con la capacidad para detectar los caracteres de SB y EB. Puede configurar los valores de carácter SB y EB, por lo que tenga cuidado con este problema al realizar cambios.  
  
 En este paso, configurará el adaptador MLLP y el adaptador SOAP.  
  
### <a name="to-create-and-configure-the-ports"></a>Para crear y configurar los puertos  
  
1.  En el Diseñador de orquestaciones, arrastre la **puerto** forma del cuadro de herramientas hasta la superficie de puerto en el lado izquierdo de la vista Diseño y coloque la forma para que alinea horizontalmente con el **DoorbellReceive** forma.  
  
2.  En el **Asistente para configuración de puertos**, haga clic en **siguiente**.  
  
3.  En el **propiedades de puerto** página, en la **nombre** , escriba **SOAPReceivePort**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **seleccionar un tipo de puerto** página, escriba la información siguiente y, a continuación, haga clic en **siguiente** para continuar.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de tipo de puerto**|Tipo de **SOAPReceivePortType**.|  
    |**Patrón de comunicación**|Seleccione **unidireccional**.|  
    |**Restricciones de acceso**|Seleccione **público: sin límite**.|  
  
5.  En el **enlace de puerto** página, haga clic en **siguiente** para aceptar los valores predeterminados.  
  
6.  En el **completar el Asistente para puertos** página, haga clic en **finalizar**.  
  
7.  Arrastre el **puerto** forma del cuadro de herramientas hasta la superficie de puerto en el lado derecho de la vista Diseño y coloque la forma para que alinea horizontalmente con el **DoorbellSend** forma.  
  
8.  Mediante el **Asistente para configuración de puertos** como hizo en los pasos del 2 al 7, cree un puerto de envío adicionales con los parámetros siguientes:  
  
    |Propiedad|Parámetro|  
    |--------------|---------------|  
    |**Nombre de propiedades de puerto**|MLLPSendPort|  
    |**Nombre de tipo de puerto**|MLLPSendPortType|  
    |**Patrón de comunicación**|Unidireccional|  
    |**Restricciones de acceso**|Público: sin límite|  
    |**Enlace de puerto**|Especificar más tarde|  
    |**Dirección de puerto de comunicación**|Siempre enviaré los mensajes en este puerto.|  
  
9. En el **Vista orquestación** ventana, con el **tipos**, **tipos de puertos**, y **SOAPReceivePortType** nodos expandidos, expanda  **Operation_1**y, a continuación, haga clic en **solicitar**.  
  
10. En el **propiedades** ventana, en la lista desplegable para **tipo de mensaje**, expanda **esquemas**y, a continuación, haga clic en **BTAHL7_Project.Doorbell** .  
  
11. En el **Vista orquestación** ventana, expanda **MLLPSendPortType**, expanda **Operation_1**y, a continuación, haga clic en **solicitar**.  
  
12. En el **propiedades** ventana, en la lista desplegable para **tipo de mensaje**, expanda **tipos de mensaje de varias partes**y, a continuación, haga clic en **BTAHL7_ Project.DoorbellFinalMessageType**.  
  
13. En el **nombre** , escriba **respuesta**, a continuación, presione **ENTRAR**.  
  
14. En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellReceive** forma acción.  
  
15. En el **propiedades** ventana, en la lista desplegable para **mensaje**, seleccione **DoorbellInputMessage**.  
  
16. En la superficie de la vista de diseño de orquestación, haga clic en el **DoorbellSend** forma.  
  
17. En el **propiedades** ventana, en la lista desplegable para **mensaje**, seleccione **DoorbellFinalMessage**.  
  
18. Haga clic en el indicador verde en el **SOAPReceivePort** y arrástrelo hasta el indicador verde el **DoorbellReceive** recibir de forma que se va a conectar el **SOAPReceivePort** a la  **DoorbellReceive** forma recepción.  
  
19. Haga clic en el indicador verde en el **DoorbellSend** forma y arrástrelo hasta el indicador verde el **MLLPSendPort** puerto para conectar el **DoorbellSend** forma de envío para el **MLLPSendPort** puerto.  
  
20. Haga clic en el **el Explorador de soluciones** ficha en la Vista orquestación.  
  
21. En el Explorador de soluciones, haga clic en **BTAHL7V22Common**y, a continuación, haga clic en **generar**. Asegúrese de que aparece un mensaje de confirmación en la ventana de salida.  
  
    > [!NOTE]
    >  Si no aparece ningún mensaje de correcto, solucionar problemas de la solución.  
  
22. Haga clic en **BTAHL7 proyecto**y haga clic en **implementar** para implementar el proyecto de BTAHL7.  
  
 Continúe con [paso 14: publicar la orquestación como servicio Web](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)