---
title: 'Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador de MLLP | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540a8745da811e7f14ab6ac5c1909bffe057c5f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006109"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a>Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador de MLLP
En este paso, creará el puerto de envío para enviar el mensaje a del sistema de información de Hospital (HIS) mediante el adaptador de MLLP.  

### <a name="to-create-the-tutorialmllpsend-send-port"></a>Para crear el puerto de envío Tutorial_MllpSend  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, realice las siguientes acciones:  


   |      Use      |                                Para                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **Nombre**      |                        Tipo **Tutorial_MllpSend**.                        |
   | **Tipo de transporte** |                 Seleccione **MLLP** en la lista desplegable.                  |
   |   **Configurar**    | Haga clic en **configurar** para abrir el **propiedades de transporte de MLLP** cuadro de diálogo. |


3. En el cuadro de diálogo Propiedades de transporte de MLLP, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.  


   |      Use       |     Para      |
   |---------------------|---------------------|
   | **Nombre de conexión** | Tipo **1WaySend**.  |
   |      **Host**       | Tipo **localhost**. |
   |      **Puerto**       |   Tipo **14000**.   |


4. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

5. En el panel izquierdo, seleccione **filtros**, y, a continuación, haga lo siguiente:  

   |Use|Para|  
   |--------------|----------------|  
   |**Propiedad**|Seleccione **BTS. ReceivePortName** en la lista desplegable.|  
   |**Operador**|Seleccione **==** en la lista desplegable.|  
   |**Value**|Tipo **Tutorial_1WayReceive**.|  

   > [!NOTE]
   >  El puerto realizará escuchas para el puerto especificado en 1WayReceive para todos los mensajes.  

6. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  

7. En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_MllpSend**y, a continuación, haga clic en **iniciar**.  

   Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).