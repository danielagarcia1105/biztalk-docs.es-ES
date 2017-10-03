---
title: "Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje a su usa el adaptador MLLP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc122ab37ee0d618c3bd75792a5b88571dd49162
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a>Paso 7: Crear un puerto de envío para entregar el ADT ^ A03 mensaje a su usa el adaptador MLLP
En este paso, creará el puerto de envío para enviar el mensaje para el sistema de información Hospital (HIS) que se usa el adaptador MLLP.  
  
### <a name="to-create-the-tutorialmllpsend-send-port"></a>Para crear el puerto de envío Tutorial_MllpSend  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, realice las siguientes acciones:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Tutorial_MllpSend**.|  
    |**Tipo de transporte**|Seleccione **MLLP** en la lista desplegable.|  
    |**Configurar**|Haga clic en **configurar** para abrir el **propiedades de transporte de MLLP** cuadro de diálogo.|  
  
3.  En el cuadro de diálogo Propiedades de transporte de MLLP, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de conexión**|Tipo de **1WaySend**.|  
    |**Host**|Tipo de **localhost**.|  
    |**Puerto**|Tipo de **14000**.|  
  
4.  En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  
  
5.  En el panel izquierdo, seleccione **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. ReceivePortName** en la lista desplegable.|  
    |**Operador**|Seleccione  **==**  en la lista desplegable.|  
    |**Valor**|Tipo de **Tutorial_1WayReceive**.|  
  
    > [!NOTE]
    >  El puerto realizará escuchas para el puerto especificado en 1WayReceive para los mensajes.  
  
6.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  
  
7.  En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_MllpSend**y, a continuación, haga clic en **iniciar**.  
  
 Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).