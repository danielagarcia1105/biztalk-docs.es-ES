---
title: 'Paso 6: Crear un puerto de envío para entregar confirmaciones | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 739b3e60-db56-46e9-a6b1-0acbe0c08f55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e30db70d67cb70ba87cf661e46ca325de1f3cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003621"
---
# <a name="step-6-create-a-send-port-to-deliver-acknowledgments"></a>Paso 6: Crear un puerto de envío para entregar confirmaciones
En este paso, creará un puerto para enviar confirmaciones de vuelta al origen del lote.  

 Cree este puerto como estática, por lo que solo será asociado con un adaptador MLLP, y sólo enviará a un destino concreto (el origen del lote). En este tutorial, el origen se asocia la entidad Tutorial_BatchSource. Esta entidad de origen se encuentra en MSH3 de los mensajes individuales y FHS3 y BHS3 del lote original.  

 Cree el puerto con los filtros que restringen el puerto de envío de confirmaciones, no los mensajes de datos. Estos filtros especifican un tipo de mensaje de ACK_024_GLO_DEF y un destino de Tutorial_BatchSource.  

 Configurar este puerto de envío para confirmaciones de recepción desde el destino, asociando el puerto de envío con un puerto de recepción denominado **TwoWayAckReceivePort**. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] programa de instalación crea este puerto, y que la acompaña de ubicación de recepción **TwoWayAckReceiveLocation**. Configurar el puerto de envío para trabajar con este puerto estableciendo **de petición respuesta habilitar** a **No** y estableciendo el **URI de la ubicación de recepción envíe** a  **127.0.0.1:65535** (es decir, la configuración necesaria para aceptar mensajes de confirmación). Para obtener más información, consulte [configuración de seguridad de un puerto de envío para recibir confirmaciones](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md).  

### <a name="to-create-a-send-port-to-deliver-acknowledgments"></a>Para crear un puerto de envío para entregar confirmaciones  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  


   |      Use      |                                Para                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **Nombre**      |                        Tipo **Tutorial_2wayAck**.                         |
   | **Tipo de transporte** |                 Seleccione **MLLP** en la lista desplegable.                  |
   |   **Configurar**    | Haga clic en **configurar** para abrir el **propiedades de transporte de MLLP** cuadro de diálogo. |


3. En el cuadro de diálogo Propiedades de transporte de MLLP, realice lo siguiente:  


   |                 Use                  |        Para         |
   |-------------------------------------------|---------------------------|
   |            **Nombre de conexión**            |     Tipo **2wayAck**.     |
   |                 **Host**                  |    Tipo **localhost**.    |
   |                 **Puerto**                  |      Tipo **41002**.      |
   |       **Solicitud respuesta habilitado**        | Mantener el campo como **No**. |
   | **Envíe la ubicación (URI) para la confirmación de recepción** | Tipo **127.0.0.1:65535**  |


4. Haga clic en **Aceptar**.  

5. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

6. En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:  

   > [!NOTE]
   >  Asegúrese de especificar los siguientes datos exactamente como se muestra. Estos datos distingue mayúsculas de minúsculas.  

   |          Use          |                                            Para                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | **Propiedad** (primero en línea)  |   Haga clic en el campo **propiedad**, a continuación, seleccione **BTS. MessageType** en la lista desplegable.   |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                Tipo **<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**.                 |
   |        **Agrupar por**        |                              Seleccione **o** en la lista desplegable.                              |
   | **Propiedad** (segunda línea) | Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable. |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                Tipo  **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>.**                 |
   |        **Agrupar por**        |                             Seleccione **y** en la lista desplegable.                              |
   | **Propiedad** (tercera línea)  |   Haga clic en el campo en la segunda línea bajo **propiedad**, a continuación, seleccione **BTAHL7Schemas.MSH5_1**.   |
   |        **Operador**        |                              Seleccione **==** en la lista desplegable.                              |
   |         **Value**          |                                  Tipo **Tutorial_BatchSource**.                                  |

   > [!NOTE]
   >  El primer filtro significa que se suscribe al mensaje de confirmación. El segundo filtro significa que desea que la confirmación que tiene el destino del publicador, **Tutorial_BatchSource**.  

7. Haga clic en **Entrar**. En el panel en la parte inferior del cuadro de diálogo, compruebe que escribió correctamente la expresión de filtro y, a continuación, haga clic en **Aceptar**.  

8. En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_2wayAck**y, a continuación, seleccione **iniciar**.  

   > [!NOTE]
   >  Para el Tutorial_2wayAck puerto de envío para funcionar correctamente, debe habilitar la TwoWayAckReceivePort ubicación de recepción.  

9. Haga clic en **ubicaciones de recepción**. Compruebe que el estado de la TwoWayAckReceiveLocation está habilitado. Si no, haga clic en **TwoWayAckReceiveLocation**y, a continuación, haga clic en **habilitar**.  

   Continúe con [paso 7: crear y configurar una entidad de origen](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md).