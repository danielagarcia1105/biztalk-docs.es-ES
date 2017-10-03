---
title: 'Parte 2: En los lotes escenario | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56ffac38676fe6b163a39ff06be5fe0538800d2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="part-2-batch-inbatch-out-scenario"></a>Parte 2: Lote / escenario de lote
En esta parte del tutorial, se recibe un archivo por lotes con codificación HL7, acceso directo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] sin fragmentación y envíe el archivo por lotes intactos en el destino. En la siguiente ilustración muestra el flujo de este proceso, y en la subsección siguiente describe el flujo de trabajo.  
  
> [!NOTE]
>  Antes de iniciar esta parte del tutorial, desactive las herramientas MllpReceive y MllpSend que usa en la parte 1, cierre el símbolo del sistema.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 **Cómo fluyen los mensajes en el lote en / escenario de lote**  
  
 Este escenario incluye el siguiente flujo de trabajo:  
  
1.  El flujo de trabajo comienza a contar cuando una aplicación de línea de negocio envía un lote de mensajes a la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) mediante el protocolo de archivo de motor de integración. El lote contiene dos versiones de un ADT ^ A03 mensaje. La aplicación de origen pertenece a la entidad Tutorial_BatchSource.  
  
2.  El motor de integración recibe el lote en un archivo de puerto de recepción y valida el lote de mensajes. (El nivel de validación depende de la configuración seleccionada para la entidad de origen en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.)  
  
3.  En función de un valor en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración que deshabilita la fragmentación de lote para la entidad, el motor de interfaz no analiza el lote en mensajes individuales, pero deja el lote como un lote. Valida los mensajes individuales, nuevo en función de la configuración seleccionada para la entidad de origen en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.  
  
4.  El motor de interfaz genera una confirmación para el mensaje de lote, en función de la configuración de la definición de confirmación en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Editor de configuración para la entidad. En este caso, selecciona el modo de confirmación Original, por lo que el motor de interfaz genera una confirmación de aplicación acepte única para el lote de mensajes después de validar el encabezado del mensaje y el cuerpo. El motor compila la confirmación basándose en el esquema ACK_024_GLO_DEF, introduce "AA" en el campo MSA2 de la confirmación, entra en la entidad de destino en MSH3 y entra en la entidad de origen en MSH5.  
  
5.  Adaptador configurado para procesar confirmaciones de envío de las rutas de motor de la interfaz del lote de confirmación al origen de terceros a través de un archivo. En este caso, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enruta el lote a la carpeta \Tutorial_BatchACKDrop.  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]envía que el lote de mensajes en el destino especificado para la entidad de destino, en este caso, la carpeta \Tutorial_BTAHL7Drop.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Configurar la información de entidad para el lote en / lote Out](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [Paso 2: Modificar o crear el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [Paso 3: Probar el lote / escenario de lote](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)