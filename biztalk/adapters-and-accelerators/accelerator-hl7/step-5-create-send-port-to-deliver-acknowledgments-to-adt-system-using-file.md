---
title: 'Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT mediante el adaptador de archivo | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1421b39ed4bbd15fb82cb16ed55b23e5781eead6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002101"
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a>Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT mediante el adaptador de archivo
En este paso, creará el puerto de envío para generar confirmaciones mediante el adaptador de archivo.  

### <a name="to-create-the-tutorialsendackadt-send-port"></a>Para crear el puerto de envío Tutorial_sendAck_ADT  

1. Mediante [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, crear el \< *unidad*:\>\Program Files\Microsoft BizTalk \<versión\> Acelerador para Tutorial\Tutorial_ HL7\SDK\End-to-End carpeta sendAck_ADT.  

2. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

3. En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  


   |      Use      |                                Para                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **Nombre**      |                      Tipo **Tutorial_sendAck_ADT**.                       |
   | **Tipo de transporte** |                 Seleccione **archivo** en la lista desplegable.                  |
   |   **Configurar**    | Haga clic en **configurar** para abrir el **propiedades de transporte File** cuadro de diálogo. |


4. En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente y, a continuación, haga clic en **Aceptar**.  


   |        Use        |                                                                     Para                                                                      |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Carpeta de destino** | Vaya a **\<** <em>unidad</em>**:\>\Program Files\Microsoft BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_sendAck_ADT**. |
   |     **Nombre de archivo**      |                                   Tipo **%MessageID%.txt** (reemplace la extensión .xml con la extensión .txt).                                    |


5. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

6. En el panel izquierdo, haga clic en **filtros**, y, a continuación, haga lo siguiente:  

   > [!NOTE]
   >  El primer filtro significa que se suscribe para el mensaje de confirmación. El segundo filtro significa que se suscribe a la confirmación que se destina el publicador Tutorial_ADTSystem.  

    Haga clic en **Aceptar** cuando esté listo para continuar.  


   |          Use          |                                            Para                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   |        **Propiedad**        | Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable. |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                Tipo **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.                 |
   |        **Agrupar por**        |                              Seleccione **o** en la lista desplegable.                              |
   | **Propiedad (segunda línea)** | Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable. |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                Tipo  **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**                 |
   |        **Agrupar por**        |                             Seleccione **AND** en la lista desplegable.                              |
   |        **Propiedad**        |     En la primera propiedad, haga clic en el cuadro en blanco y, a continuación, seleccione **BTAHL7Schemas.MSH5_1**.     |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                                   Tipo **Tutorial_ADTSystem**.                                   |

   > [!NOTE]
   >  Para el puerto de envío Tutorial_sendAck_ADT BTAHL7 quita las confirmaciones en la ubicación de destino de archivo \< *unidad*\>: programa FilesMicrosoft BizTalk <version> acelerador HL7SDKEnd-to-end TutorialTutorial_sendAck_ADT.  

7. Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  

8. En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendAck_ADT**y, a continuación, haga clic en **iniciar**.  

   Continúe con [paso 6: crear un puerto de envío para entregar el ADT ^ A03 mensaje al sistema RX mediante el adaptador de archivo](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md).