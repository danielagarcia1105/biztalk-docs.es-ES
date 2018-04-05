---
title: 'Paso 6: Crear un puerto de envío para entregar los mensajes de consulta | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c373940d8ab1e847b66527d83ef24e952d84d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a>Paso 6: Crear un puerto de envío para entregar los mensajes de consulta
En este paso, creará el puerto de envío para entregar las consultas entrantes (consulta ^ Q01 mensajes) para el sistema de información de Hospital (HIS).  
  
### <a name="to-create-the-hissend-send-port"></a>Para crear el puerto de envío HIS_Send  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **HIS_Send**.|  
    |**Tipo de transporte**|Seleccione **MLLP**.|  
    |**Configurar**|Haga clic en el **configurar** situado a la derecha de **tipo**.|  
  
3.  En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre de conexión**|Tipo de **HIS_SendMLLP**.|  
    |**Host**|Tipo de **localhost**.|  
    |**Puerto**|Tipo de **24000**.|  
  
4.  En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  
  
5.  En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Para **propiedad**, seleccione **BTS. MessageType**.|  
    |**Operador**|Seleccione  **==**  en la lista desplegable.|  
    |**Valor**|Tipo de **http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**.|  
    |**Agrupar por**|Seleccione **AND** en la lista desplegable.|  
    |**Propiedad**|Para **propiedad** en la segunda línea, seleccione **BTAHL7Schemas.MSH5_1**.|  
    |**Operador**|Seleccione  **==**  en la lista desplegable.|  
    |**Valor**|Tipo de **HIS**.|  
  
    > [!NOTE]
    >  El primer filtro especifica que el puerto de envío selecciona sólo mensajes sean conformes a la consulta ^ esquema Q01 que creó en el paso 3A. El segundo filtro especifica el destino en el que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.  
  
6.  Haga clic en **Aceptar**.  
  
7.  En la consola de administración, seleccione **puertos de envío**, haga clic en **HIS_Send**y, a continuación, haga clic en **iniciar**.  
  
 Continúe con [paso 7: crear un puerto de envío para entregar los mensajes de respuesta](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).