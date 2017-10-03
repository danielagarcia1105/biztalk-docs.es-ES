---
title: 'Parte 3: Crear lote escenario | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0949d45fc70ead14338e30b554e0cb4b9694b5d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="part-3-create-batch-scenario"></a>Parte 3: Escenario de lote crear
En esta parte del escenario, recibe dos mensajes entrantes, combinarlos en un mensaje por lotes y enviar el lote a un destino. Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) devuelve un lote de confirmación que contiene las dos confirmaciones generadas para los mensajes desde el destino al origen. En la siguiente ilustración muestra el flujo del proceso de esta parte del tutorial.  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 **Cómo fluyen los mensajes en el escenario de crear lote**  
  
 Este escenario incluye el siguiente flujo de trabajo:  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]intercepta todos los mensajes sean conformes a la definición de lote en la base de datos de cuadro de mensajes. Escriba esta definición en el **definición por lotes** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración. En este tutorial, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] se capturar y procesar por lotes de todos los mensajes se envíen a Tutorial_BatchDest con un esquema de ADT ^ A03 y todas las confirmaciones para enviarse a Tutorial_BatchSource como resultado ADT ^ A03 mensajes.  
  
-   Cuando se produce la hora de envío por lotes programados, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía un mensaje de control de proceso por lotes que desencadena la transacción por lotes saliente. Defina la programación en el **programación por lotes** ficha de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración. También puede desencadenar el proceso haciendo clic en **enviar ahora** en la misma ficha.  
  
-   La orquestación del lote constituye el lote de mensajes fuera de los mensajes que haya quedado bloqueada en la base de datos de cuadro de mensajes. La orquestación también ajusta el lote en un encabezado de archivo y finalizador y un encabezado de lote y el finalizador. Esta orquestación es nativo [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] orquestación agregada por [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el programa de instalación para el conjunto de orquestaciones de BizTalk, por lo que aparece bajo el nodo orquestaciones en el Explorador de BizTalk o la consola de administración de BizTalk Server.  
  
-   Si las confirmaciones se definen para la entidad de origen (como aparecen en este caso para Tutorial_BatchSource), BizTalk procesa por lotes las confirmaciones y los devuelve en un lote (en la carpeta \Tutorial_BatchACKDrop). En este tutorial, las confirmaciones por lotes se envían tras un breve retraso.  
  
-   La orquestación enruta el mensaje al puerto de envío (Tutorial_BatchDest), que envía el mensaje por lotes en el destino (en este caso, la carpeta \Tutorial_BatchMsgDrop en el disco duro). En este tutorial, se envían los mensajes por lotes después de una hora.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Paso 1: Configurar y habilitar el BatchControlPort el puerto de recepción](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [Paso 2: Habilitar la orquestación del lote](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [Paso 3: Crear y configurar una entidad de destino](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [Paso 4: Configurar la entidad de origen para el escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [Paso 5: Crear el puerto de envío para el lote de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [Paso 6: Crear el puerto de envío para el lote de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [Paso 7: Iniciar la orquestación y reiniciar el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [Paso 8: Probar el escenario de lote crear](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)