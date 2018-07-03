---
title: 'Paso 5: Crear el puerto de envío para el lote de mensajes | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24a71d788d0b12a3ffaef8f14ccd145ef61d673e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002845"
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a>Paso 5: Crear el puerto de envío para el lote de mensajes
En este paso, creará un puerto de envío para entregar el lote de mensajes que cree para la entidad de destino. Se trata de un puerto unidireccional estático con un tipo de adaptador de archivo. Designa una carpeta de archivos para el destino (\Tutorial_BatchMsgDrop) donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se quitará el archivo por lotes de mensajes. Definir un filtro para el puerto que indica qué tipo de lotes de mensajes que enviará los puertos. El filtro especifica el destino de Tutorial_BatchDest y el tipo de mensaje de OutboundBatch.  

> [!NOTE]
>  Cuando se ejecuta esta parte del tutorial, puede simplificar los resultados al detener el puerto de envío utilizado en la parte 2 del tutorial: el **Tutorial_BTAHL7Drop** puerto de envío.  

### <a name="to-create-the-send-port-for-the-message-batch"></a>Para crear el puerto de envío para el lote de mensajes  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  


   |   Use    |                              Para                               |
   |---------------|-----------------------------------------------------------------------|
   |   **Nombre**    |                     Tipo **Tutorial_BatchDest**.                      |
   |   **Tipo**    |               Seleccione **archivo** en la lista desplegable.                |
   | **Configurar** | Haga clic en **configurar** para abrir el cuadro de diálogo Propiedades de transporte de archivo. |


3. En el **propiedades de transporte FILE** diálogo cuadro, realice lo siguiente:  


   |        Use        |                                                                                                                                                                           Para                                                                                                                                                                            |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Carpeta de destino** | Vaya a  **\< *unidad*:\>\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\End-to-End Tutorial\Tutorial_BatchMsgDrop**. Se trata de la ruta de acceso a la ubicación en el sistema de archivos o recurso compartido público al que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] escribirá el archivo que contiene el lote de mensajes. |
   |     **Nombre de archivo**      |                                                                                                                                         Tipo **%MessageID%.txt** (reemplace la extensión .xml con la extensión .txt).                                                                                                                                          |
   |     **Modo de copia**      |                                                                                                                                                                     Seleccione **crear nuevos**.                                                                                                                                                                      |


4. Haga clic en **Aceptar**.  

5. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

6. En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:  


   |   Use   |                                                              Para                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | **Propiedad** | Haga clic en el campo **propiedad**y, a continuación, seleccione **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** en la lista desplegable. |
   | **Operador** |                                                    Deje **==** como el operador.                                                     |
   |  **Value**   |                                                     Tipo **Tutorial_BatchDest**.                                                     |
   | **Agrupar por** |                                               Seleccione **y** en la lista desplegable.                                                |
   | **Propiedad** |                                             Seleccione **BTAHL7Schemas.BTAHL7MessageType**.                                              |
   | **Operador** |                                                    Deje **==** como el operador.                                                     |
   |  **Value**   |                                                       Tipo **OutboundBatch**.                                                        |


7. Presione **ENTRAR**. En el panel en la parte inferior del cuadro de diálogo, compruebe que escribió correctamente la expresión de filtro y, a continuación, haga clic en **Aceptar**.  

8. En la consola de administración de BizTalk, seleccione **puertos de envío**, haga clic en **Tutorial_BatchDest**y, a continuación, haga clic en **iniciar**.  

### <a name="to-associate-the-send-port-with-the-destination-party"></a>Para asociar el puerto de envío a la entidad de destino  

1. En la consola de administración de BizTalk Server, expanda **partes**, haga clic en **Tutorial_BatchDest**y, a continuación, haga clic en **propiedades**.  

2. En el cuadro de diálogo Propiedades de entidades, haga clic en **puertos de envío** en el árbol de consola.  Seleccione **Tutorial_BatchDest** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si se produce una infracción de simultaneidad mientras el **Tutorial_DestBatch** se actualizaba la entidad, haga clic en **Aceptar** y cerrar el cuadro de diálogo. En la consola de administración, haga clic en **grupo de BizTalk**, haga clic en **actualizar**y, a continuación, repita los pasos 1 y 2.  

   Continúe con [paso 6: crear el puerto de envío para el lote de confirmación](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md).