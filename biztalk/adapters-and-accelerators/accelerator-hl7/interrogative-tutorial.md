---
title: Tutorial de interrogación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92c832de8b6572e5ac70b79db1cbcc75d3812ea6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003205"
---
# <a name="interrogative-tutorial"></a>Tutorial de interrogación
Este tutorial contiene los pasos detallados que describen cómo utilizar Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] para facilitar procesos empresariales en un escenario de consulta/respuesta.  
  
> [!NOTE]
>  Para usar este tutorial, debe instalar las herramientas de prueba MLLP. Estas herramientas no se instalan una instalación típica de BTAHL7. Debe ejecutar una instalación personalizada y seleccione **herramienta de prueba de MLLP** desde la carpeta del adaptador y **las instancias de prueba** desde la carpeta de artefactos. Si se instalan las herramientas de prueba, el sistema contendrá la carpeta \< *unidad*:\>\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\MLLP utilidades. Consulte [instalar el Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).  
  
## <a name="interrogative-scenario"></a>Escenario de interrogación  
 Este tutorial usa la consulta/respuesta o un escenario de interrogación. En este escenario, el flujo de negocio es similar al que se muestra en la ilustración siguiente. La lista numerada de la figura siguiente describe el flujo de trabajo.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  El flujo de trabajo comienza cuando un sistema de admisión de descarga y transferir (ADT) envía una consulta al sistema de información de Hospital. El mensaje de HL7 usa el "**QRY ^ Q01**" esquema. En el tutorial, la utilidad MllpSend simula el ADT sistema que envía el mensaje de consulta al sistema de información de Hospital a través de la ADT puerto de recepción en el motor de integración de BTAHL7.  
  
2.  El motor de integración de BTAHL7 recibe el mensaje de consulta desde el sistema ADT y lo valida. A continuación, la canalización de BTAHL7 envía una confirmación al ADT.  
  
3.  El motor de la interfaz de BTAHL7 procesa el mensaje y, a continuación, el puerto de envío el mensaje de consulta en el destino de HIS de terceros a través de la HIS de rutas.  
  
4.  Después de recibir la confirmación de la consulta original, el sistema ADT espera una respuesta. Puerto de recepción de los envíos de sistema de información de Hospital un mensaje de respuesta hacia atrás por la HIS. Para este tutorial, la utilidad MllpSend simula el sistema de información de Hospital enviar el mensaje de respuesta.  
  
5.  El motor de la interfaz de BTAHL7 procesa el mensaje de respuesta y, a continuación, se enruta a la entidad de destino a través del puerto de envío ADT.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Preparación para usar el tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [Paso 1: Crear e implementar esquemas comunes de encabezado y confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [Paso 2: Crear los esquemas comunes para V2.4](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [Paso 3: Crear e implementar un proyecto de desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [Paso 4: Crear el puerto de recepción para aceptar mensajes de consulta de ADT](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [Paso 5: Crear el puerto de recepción para aceptar mensajes de consulta de HIS](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [Paso 6: Crear un puerto de envío para entregar los mensajes de consulta](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [Paso 8: Configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [Paso 9: Reiniciar BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [Paso 10: Comprobar el escenario de interrogación](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a>Paso siguiente  
 [Preparación para usar el tutorial](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a>Vea también  
[Introducción al Acelerador de BizTalk para HL7](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)