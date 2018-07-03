---
title: 'Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje al sistema RX mediante el adaptador de archivo | Microsoft Docs'
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
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95a9200d4c03f11f2feca89042bfb57ba36de345
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004381"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a>Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje al sistema RX mediante el adaptador de archivo
En este paso, creará el puerto de envío para la farmacia del sistema (RX) mediante el adaptador de archivo.  

### <a name="to-create-the-tutorialsendmsgrx-send-port"></a>Para crear el puerto de envío Tutorial_sendMsg_RX  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

2. En el **propiedades de puerto de envío** diálogo cuadro, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.  


   |      Use      |                                Para                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **Nombre**      |                       Tipo **Tutorial_sendMsg_RX**.                       |
   | **Tipo de transporte** |                 Seleccione **archivo** en la lista desplegable.                  |
   |   **Configurar**    | Haga clic en **configurar** para abrir el **propiedades de transporte File** cuadro de diálogo. |


3. En el cuadro de diálogo Propiedades de transporte de archivo, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.  


   |        Use        |                                                                     Para                                                                     |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Carpeta de destino** | Vaya a **\<** <em>unidad</em>**:\>\Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_sendMsg_RX**. |
   |     **Nombre de archivo**      |                                   Tipo **%MessageID%.txt** (reemplace la extensión .xml con la extensión .txt).                                   |


4. En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

5. En el panel izquierdo, seleccione **filtros**, y, a continuación, realice las acciones siguientes. Haga clic en **Aceptar** para continuar.  


   |          Use          |                                            Para                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | **Propiedad** (primero en línea)  |                       Seleccione **BTS. MessageType** en la lista desplegable.                        |
   |        **Operador**        |                              Seleccione **! =** en la lista desplegable.                              |
   |         **Value**          |                Tipo **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.                 |
   |        **Agrupar por**        |                              Seleccione **o** en la lista desplegable.                              |
   | **Propiedad** (segunda línea) | Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable. |
   |        **Operador**        |                              Seleccione **! =** en la lista desplegable.                              |
   |         **Value**          |                Tipo  **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**                 |
   |        **Agrupar por**        |                             Seleccione **AND** en la lista desplegable.                              |
   | **Propiedad** (tercera línea)  |                                 Seleccione **BTAHL7Schemas.MSH3_1**.                                 |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                                   Tipo **Tutorial_ADTSystem**.                                   |

   > [!NOTE]
   >  El primer filtro significa que el sistema de información de Hospital (HIS) se está suscribiendo a un mensaje, no una confirmación. El segundo filtro significa que su está suscribiendo a los mensajes cuyo origen es la admisión de descarga y el sistema de transferencia (ADT).  

   > [!NOTE]
   >  BTAHL7 coloca el mensaje en la ubicación de destino de archivo \< *unidad*\>: programa FilesMicrosoft BizTalk <version> Acelerador para TutorialTutorial_sendMsg_RX HL7SDKEnd-to-End.  

6. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  

7. En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendMsg_RX**y, a continuación, haga clic en **iniciar**.  

   Continúe con [paso 7: crear un puerto de envío para entregar el ADT ^ mensaje A03 a HIS mediante el adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).