---
title: 'Parte 2: En lotes escenario | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593f1e57b12eb30f47db65bfacd34a988f701f07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975421"
---
# <a name="part-2-batch-inbatch-out-scenario"></a>Parte 2: Proceso por lotes en / escenario de lote
En esta parte del tutorial, se recibe un archivo de lotes codificados en HL7, pasarlo a través de [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin fragmentación y envíe el archivo por lotes intacto al destino. En la siguiente ilustración muestra el flujo de este proceso y la subsección siguiente describe el flujo de trabajo.  
  
> [!NOTE]
>  Antes de iniciar esta parte del tutorial, desactive las herramientas de MllpReceive y MllpSend que usó en la parte 1, al cerrar los símbolos.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 **Cómo fluyen los mensajes del lote en / escenario de lote**  
  
 Este escenario incluye el flujo de trabajo siguiente:  
  
1. El flujo de trabajo se inicia cuando una aplicación de línea de negocio envía un lote de mensajes para el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) mediante el protocolo de archivo de motor de integración. El lote contiene dos versiones de un ADT ^ A03 mensaje. La aplicación de origen pertenece a la entidad Tutorial_BatchSource.  
  
2. El motor de integración recibe el lote en un archivo de puerto de recepción y valida el lote de mensajes. (El nivel de validación depende de la configuración seleccionada para la entidad de origen en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.)  
  
3. En función de una configuración en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración que deshabilita la fragmentación de lote para la entidad, el motor de la interfaz no se analiza el lote en mensajes individuales, pero deja el lote como un lote. Valida los mensajes individuales, nuevamente basados en la configuración seleccionada para la entidad de origen en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración.  
  
4. El motor de la interfaz genera una confirmación para el mensaje por lotes, según la configuración de la definición de confirmación en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Editor de configuración para la entidad. En este caso, selecciona el modo de confirmación Original, por lo que el motor de la interfaz genera una confirmación de aceptación de la aplicación solo para el lote de mensajes después de validar el encabezado del mensaje y el cuerpo. El motor de la confirmación en función del esquema ACK_024_GLO_DEF basa, escribirá "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.  
  
5. Adaptador configurado para procesar las confirmaciones de envío de las rutas de motor de la interfaz del lote de confirmación al origen de terceros a través de un archivo. En este caso, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enruta el lote a la carpeta \Tutorial_BatchACKDrop.  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía que el lote de mensajes al destino especificado para la entidad de destino, en este caso el \Tutorial_BTAHL7Drop carpeta.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Configurar la información de entidad para el lote de entrada o salida](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [Paso 2: Modificar o crear los puertos de envío y recepción](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [Paso 3: Probar el escenario de lote de entrada o salida](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)