---
title: 'Parte 1: Escenario de fragmentados por lotes entrantes | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8891bd09c803c77e1878b304f5db5b71a26ab9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a>Parte 1: Escenario de fragmentados por lotes entrantes
En esta parte del tutorial, recibir un lote con codificación HL7, fragmentar en mensajes individuales y enviar los mensajes individuales a un destino. En la siguiente ilustración muestra el flujo de este proceso.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 Este escenario incluye el siguiente flujo de trabajo:  
  
1.  El flujo de trabajo comienza a contar cuando una aplicación de línea de negocio envía un lote de mensajes a la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] motor de integración mediante el protocolo de capa de protocolo inferior mínimo (MLLP). El lote contiene dos versiones de un ADT ^ A03 mensaje. La aplicación de origen pertenece a la entidad Tutorial_BatchSource.  
  
2.  El motor de la interfaz recibe el lote en un MLLP puerto de recepción y valida el lote de mensajes. (El nivel de validación depende de configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7).  
  
3.  En función de una configuración en el Explorador de configuración de BTAHL7 que permite la fragmentación de lote, el motor de interfaz analiza el lote en dos ADT individuales ^ A03 mensajes. Valida los mensajes individuales, nuevo en función de la configuración seleccionada para la entidad de origen en el Explorador de configuración de BTAHL7.  
  
4.  El motor de interfaz genera una confirmación para cada mensaje, en función de la configuración de la definición de confirmación en el Explorador de configuración de BTAHL7. En este tutorial, seleccionará el modo de confirmación Original, por lo que el motor de interfaz genera una confirmación de aplicación acepte única para cada mensaje después de validar el encabezado del mensaje y el cuerpo. El motor compila la confirmación basándose en el esquema ACK_024_GLO_DEF, introduce "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.  
  
5.  El motor de interfaz coloca contenedores MLLP alrededor de cada confirmación, y las rutas de las confirmaciones al origen de terceros a través de un adaptador de envío MLLP configurado para procesar confirmaciones.  
  
6.  El motor de interfaz incluye contenedores MLLP alrededor de cada mensaje y rutas configurado para procesar mensajes de confirmación no de puerto de envío de cada mensaje de forma individual para un MLLP.  
  
7.  BTAHL7 envía cada mensaje a través de otro puerto de envío MLLP en el destino especificado en el campo MSH5.  
  
8.  La entidad de destino que se envía a BTAHL7 una confirmación para cada mensaje que recibió de aceptación de aplicación.  
  
9. El motor de la interfaz recibe cada confirmación.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Agregar encabezado y esquemas de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [Paso 2: Agregar los esquemas comunes para v2.3.1](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [Paso 3: Agregar un esquema de desencadenador de eventos (mensaje)](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [Paso 4: Crear un puerto de recepción para aceptar el mensaje de lote](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [Paso 5: Crear un puerto de envío para la entrega de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [Paso 6: Crear un puerto de envío para entregar confirmaciones](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [Paso 7: Crear y configurar una entidad de origen](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [Paso 8: Reinicie el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [Paso 9: Compruebe el escenario fragmentados por lotes entrantes](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)