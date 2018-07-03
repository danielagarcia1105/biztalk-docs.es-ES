---
title: 'Parte 1: Escenario de lote de entrada fragmentado | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5cf6f38daca7b1773798e4bc8ed2e40ad143bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970509"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a>Parte 1: Escenario de lote de entrada fragmentado
En esta parte del tutorial, recibir un lote con codificación HL7, fragmento de en mensajes individuales y enviar los mensajes individuales a un destino. En la siguiente ilustración muestra el flujo de este proceso.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 Este escenario incluye el flujo de trabajo siguiente:  
  
1. El flujo de trabajo se inicia cuando una aplicación de línea de negocio envía un lote de mensajes de Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] motor de integración mediante el protocolo del protocolo de nivel inferior mínimo (MLLP). El lote contiene dos versiones de un ADT ^ A03 mensaje. La aplicación de origen pertenece a la entidad Tutorial_BatchSource.  
  
2. El motor de la interfaz se recibe el lote en un MLLP puerto de recepción y valida el lote de mensajes. (El nivel de validación depende de configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7).  
  
3. Basándose en una configuración en el Explorador de configuración de BTAHL7 que permite la fragmentación de lote, el motor de la interfaz analiza el lote en dos ADT individuales ^ A03 mensajes. Valida los mensajes individuales, nuevamente basados en la configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7.  
  
4. El motor de la interfaz genera una confirmación para cada mensaje, según la configuración de la definición de confirmación en el Explorador de configuración de BTAHL7. En este tutorial, seleccionará el modo de confirmación Original, por lo que el motor de la interfaz genera una confirmación de aplicación acepte única para cada mensaje después de validar el encabezado del mensaje y el cuerpo. El motor de la confirmación en función del esquema ACK_024_GLO_DEF basa, escribirá "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.  
  
5. El motor de la interfaz coloca contenedores MLLP en torno a cada confirmación, y las rutas de las confirmaciones en el origen de terceros a través de un adaptador de envío MLLP configuración para procesar confirmaciones.  
  
6. El motor de interfaz incluye contenedores MLLP en torno a cada mensaje y las rutas configurada para procesar los mensajes de confirmación de que no sean de puerto de envío de cada mensaje de forma individual para un MLLP.  
  
7. BTAHL7 envía cada mensaje a través de otro puerto de envío MLLP al destino especificado en el campo MSH5.  
  
8. La entidad de destino que se envía a BTAHL7 una confirmación para cada mensaje que recibió de aceptación de aplicación.  
  
9. El motor de la interfaz se recibe cada confirmación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Agregar esquemas de encabezado y confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [Paso 2: Agregar los esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [Paso 3: Agregar un esquema de desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [Paso 4: Crear el puerto de recepción para aceptar el mensaje de lote](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [Paso 5: Crear un puerto de envío para entregar mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [Paso 6: Crear un puerto de envío para entregar confirmaciones](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [Paso 7: Crear y configurar una entidad de origen](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [Paso 8: Reiniciar BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [Parte 9: Comprobar el escenario de lote de entrada fragmentado](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)