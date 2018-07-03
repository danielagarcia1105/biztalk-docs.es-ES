---
title: 'Paso 5: Crear un puerto de envío para entregar mensajes | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f56ad7a7-5c77-4191-a001-691e5e0652a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec45b98cf1ef5152f52e6d11c9d3f6d150c6b55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001685"
---
# <a name="step-5-create-a-send-port-to-deliver-messages"></a>Paso 5: Crear un puerto de envío para entregar mensajes
En este paso, crear y configurar un puerto para enviar los mensajes individuales contenidos en el lote recibido. Más adelante en el tutorial, se habilitará la fragmentación de la entidad de origen (Tutorial_BatchSource) en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración. Como resultado, el motor de integración de BizTalk fragmentará el lote en mensajes individuales y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] enviará los mensajes a través del puerto de envío que se crea en este paso.  

 Cree este puerto como estática, por lo que solo será asociado con un adaptador MLLP, y sólo enviará a un destino concreto (la aplicación de línea de negocio de destino). En este tutorial, que el destino es MESA_IS, que contiene el MSH5 de los mensajes individuales. Cree el puerto con los filtros que restringen el puerto para enviar mensajes, no las confirmaciones, filtrando los mensajes que cumplen el esquema ACK_024_GLO_DEF o cualquier confirmación (ACK) estático.  

 Configurar este puerto de envío para recibir confirmaciones desde el destino, asociando el puerto de envío con un puerto de recepción denominado **TwoWayAckReceivePort**. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación crea este puerto, y que la acompaña de ubicación de recepción **TwoWayAckReceiveLocation**. Configurar el puerto de envío para trabajar con este puerto estableciendo **de petición respuesta habilitar** a **Sí** y estableciendo el **URI de la ubicación de recepción envíe** a  **127.0.0.1:65535** (es decir, la configuración necesaria para aceptar mensajes de confirmación). Para obtener más información, consulte [configuración de seguridad de un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md).  

### <a name="to-create-a-send-port-to-deliver-messages"></a>Para crear un puerto de envío para entregar mensajes  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  


   |      Use      |                              Para                               |
   |--------------------|-----------------------------------------------------------------------|
   |      **Nombre**      |                      Tipo **Tutorial_2wayMsg**.                       |
   | **Tipo de transporte** |               Seleccione **MLLP** en la lista desplegable.                |
   |   **Configurar**    | Haga clic en **configurar** para abrir el cuadro de diálogo Propiedades de transporte de MLLP. |


3. En el cuadro de diálogo Propiedades de transporte de MLLP, realice lo siguiente:  


   |                 Use                  |                                                   Para                                                   |
   |-------------------------------------------|----------------------------------------------------------------------------------------------------------------|
   |            **Nombre de conexión**            |                                               Tipo **2wayMsg**.                                                |
   |                 **Host**                  |                                              Tipo **localhost**.                                               |
   |                 **Puerto**                  |                                                Tipo **41000**.                                                 |
   |       **Solicitud respuesta habilitado**        | Haga clic en el campo a la derecha del **de petición respuesta habilitado**y, a continuación, seleccione **Sí** en la lista desplegable. |
   | **Envíe la ubicación (URI) para la confirmación de recepción** |                                            Tipo**127.0.0.1:65535**                                             |


4. Haga clic en **Aceptar**.  

5. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

6. En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:  


   |          Use          |                                                     Para                                                      |
   |----------------------------|---------------------------------------------------------------------------------------------------------------------|
   | **Propiedad** (primero en línea)  |          Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.           |
   |        **Operador**        |                                       Seleccione **! =** en la lista desplegable.                                        |
   |         **Value**          |                          Tipo **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.                          |
   |        **Agrupar por**        |                                       Seleccione **AND** en la lista desplegable.                                       |
   | **Propiedad** (segunda línea) |          Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.           |
   |        **Operador**        |                                       Seleccione **! =** en la lista desplegable.                                        |
   |         **Value**          |                          Tipo  **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**                          |
   |        **Agrupar por**        |                                       Seleccione **y** en la lista desplegable.                                       |
   | **Propiedad** (tercera línea)  | Haga clic en el campo en la segunda línea bajo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable. |
   |        **Operador**        |                                       Seleccione **! =** en la lista desplegable.                                        |
   |         **Value**          |                                                 Tipo **StaticAck**.                                                 |


7. Haga clic en **Entrar**. En el panel en la parte inferior del cuadro de diálogo, compruebe que escribió correctamente la expresión de filtro y, a continuación, haga clic en **Aceptar**.  

8. En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_2wayMsg**y, a continuación, haga clic en **iniciar**.  

   Continúe con [paso 6: crear un puerto de envío para entregar confirmaciones](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md).