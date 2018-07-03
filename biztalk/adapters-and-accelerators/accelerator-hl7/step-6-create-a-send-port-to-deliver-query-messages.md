---
title: 'Paso 6: Crear un puerto de envío para entregar los mensajes de consulta | Microsoft Docs'
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
ms.openlocfilehash: 24e65ec7bc4e04850907609fc6d1d63e6f166593
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004053"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a>Paso 6: Crear un puerto de envío para entregar los mensajes de consulta
En este paso, creará el puerto de envío para entregar las consultas entrantes (QRY ^ Q01 mensajes) para el sistema de información de Hospital (HIS).  

### <a name="to-create-the-hissend-send-port"></a>Para crear el puerto de envío HIS_Send  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, seleccione **puerto de envío unidireccional estático**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  


   |      Use      |                        Para                        |
   |--------------------|----------------------------------------------------------|
   |      **Nombre**      |                    Tipo **HIS_Send**.                    |
   | **Tipo de transporte** |                     Seleccione **MLLP**.                     |
   |   **Configurar**    | Haga clic en el **configurar** situado a la derecha de **tipo**. |


3. En el cuadro de diálogo Propiedades de transporte de MLLP, escriba la información siguiente y, a continuación, haga clic en **Aceptar**.  


   |      Use       |       Para       |
   |---------------------|------------------------|
   | **Nombre de conexión** | Tipo **HIS_SendMLLP**. |
   |      **Host**       |  Tipo **localhost**.   |
   |      **Puerto**       |    Tipo **24000**.     |


4. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

5. En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:  


   |   Use   |                              Para                               |
   |--------------|-----------------------------------------------------------------------|
   | **Propiedad** |             Para **propiedad**, seleccione **BTS. MessageType**.             |
   | **Operador** |                Seleccione **==** en la lista desplegable.                 |
   |  **Value**   | Tipo **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**. |
   | **Agrupar por** |                Seleccione **AND** en la lista desplegable.                |
   | **Propiedad** | Para **propiedad** en la segunda línea, seleccione **BTAHL7Schemas.MSH5_1**. |
   | **Operador** |                Seleccione **==** en la lista desplegable.                 |
   |  **Value**   |                             Tipo **HIS**.                             |

   > [!NOTE]
   >  El primer filtro especifica que el puerto de envío solo selecciona los mensajes que cumplen el QRY ^ esquema Q01 que creó en el paso 3A. El segundo filtro especifica el destino al que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] motor interfaz envía estos mensajes.  

6. Haga clic en **Aceptar**.  

7. En la consola de administración, seleccione **puertos de envío**, haga clic en **HIS_Send**y, a continuación, haga clic en **iniciar**.  

   Continúe con [paso 7: crear un puerto de envío para entregar los mensajes de respuesta](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).