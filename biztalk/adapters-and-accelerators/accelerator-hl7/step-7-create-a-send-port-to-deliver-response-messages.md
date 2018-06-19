---
title: 'Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1260772f3b3df5f0dea96b0aa66023e107b9aa6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207084"
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a>Paso 7: Crear un puerto de envío para entregar los mensajes de respuesta
En este paso, creará el puerto de envío para entregar las respuestas de consulta a la admisión, descarga y transferir (ADT) sistema.  
  
### <a name="to-create-the-adtsend-send-port"></a>Para crear el puerto de envío ADT_Send  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **ADT_Send**.|  
    |**Tipo de transporte**|Seleccione **MLLP**.|  
    |**Configurar**|Haga clic en el **configurar** situado a la derecha de **tipo**.|  
  
3.  En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de conexión**|Tipo de **ADT_SendMLLP**.|  
    |**Host**|Tipo de **localhost**.|  
    |**Puerto**|Tipo de **25000**.|  
  
4.  En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  
  
5.  En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. MessageType**.|  
    |**Operador**|Seleccione  **==**  en la lista desplegable.|  
    |**Valor**|Tipo de **http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF**.|  
    |**Agrupar por**|Seleccione **AND** en la lista desplegable.|  
    |**Propiedad**|En la primera propiedad, haga clic en el cuadro en blanco y, a continuación, seleccione **BTAHL7Schemas.MSH5_1**.|  
    |**Operador**|Seleccione  **==**  en la lista desplegable.|  
    |**Valor**|Tipo de **ADT**.|  
  
    > [!NOTE]
    >  El primer filtro especifica que el puerto de envío selecciona sólo mensajes sean conformes al DSR ^ esquema Q01 que creó en el paso 3A. El segundo filtro especifica el destino en el que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En la consola de administración, haga clic en **puertos de envío**, haga clic en **ADT_Send**y, a continuación, haga clic en **iniciar**.  
  
 Continúe con [paso 8: configurar la información de entidad](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).