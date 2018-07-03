---
title: 'Paso 6: Crear el puerto de envío para el lote de confirmación | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a0f1ee-e060-4fb9-923e-ebe8168777d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f38b8c7f8e2f486e4de6feca12bf69551221428
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005005"
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a>Paso 6: Crear el puerto de envío para el lote de confirmación
En este paso, creará un puerto de envío para entregar el lote de confirmación que cree para la entidad de origen. Se trata de un puerto unidireccional estático con un tipo de adaptador de archivo. Designa una carpeta de archivos para el origen (\Tutorial_BatchACKDrop), donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se quitará el archivo por lotes de confirmación. Definir un filtro para el puerto que indica qué tipo de lotes de confirmación que enviará los puertos. El filtro especifica el origen de Tutorial_BatchSource y el tipo de mensaje de OutboundBatch.  

### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a>Para crear el puerto de envío para el lote de confirmación  

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  

2. En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  


   |   Use    |                              Para                               |
   |---------------|-----------------------------------------------------------------------|
   |   **Nombre**    |                    Tipo **Tutorial_BatchSource**.                     |
   |   **Tipo**    |               Seleccione **archivo** en la lista desplegable.                |
   | **Configurar** | Haga clic en **configurar** para abrir el cuadro de diálogo Propiedades de transporte de archivo. |


3. En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente:  


   |        Use        |                                                                                                                                                                              Para                                                                                                                                                                               |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Carpeta de destino** | Vaya a  **\< *unidad*:\>\Program Files\Microsoft BizTalk \<versión\> Acelerador para HL7\SDK\End-to-End Tutorial\Tutorial_BatchACKDrop**. Se trata de la ruta de acceso a la ubicación en el sistema de archivos o recurso compartido público al que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] escribirá el archivo que contiene el lote de confirmación. |
   |     **Nombre de archivo**      |                                                                                                                                            Tipo **%MessageID%.txt** (reemplace la extensión .xml con la extensión .txt).                                                                                                                                             |
   |     **Modo de copia**      |                                                                                                                                                                        Seleccione **crear nuevos**.                                                                                                                                                                         |


4. Haga clic en **Aceptar**.  

5. En el cuadro de diálogo Propiedades de puerto de envío para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  

6. En el árbol de consola, haga clic en **filtros**, y, a continuación, haga lo siguiente:  


   |   Use   |                                                              Para                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | **Propiedad** | Haga clic en el campo **propiedad**y, a continuación, seleccione **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** en la lista desplegable. |
   | **Operador** |                                                    Deje **==** como el operador.                                                     |
   |  **Value**   |                                                    Tipo **Tutorial_BatchSource**.                                                    |
   | **Agrupar por** |                                               Seleccione **y** en la lista desplegable.                                                |
   | **Propiedad** |                                             Seleccione **BTAHL7Schemas.BTAHL7MessageType**.                                              |
   | **Operador** |                                                    Deje **==** como el operador.                                                     |
   |  **Value**   |                                                       Tipo **OutboundBatch**.                                                        |


7. Presione **ENTRAR**. En el panel en la parte inferior del cuadro de diálogo, compruebe que escribió correctamente la expresión de filtro y, a continuación, haga clic en **Aceptar**.  

8. En la consola de administración de BizTalk, seleccione **puertos de envío**, haga clic en **Tutorial_BatchSource**y, a continuación, haga clic en **iniciar**.  

### <a name="to-associate-the-send-port-with-the-source-party"></a>Para asociar el puerto de envío a la entidad de origen  

1. En la consola de administración de BizTalk, haga clic en **partes**. Haga clic en **Tutorial_BatchSource**y, a continuación, haga clic en **propiedades**.  

2. En el cuadro de diálogo Propiedades de entidades, haga clic en **puertos de envío** en el árbol de consola. Para **puertos de envío**, seleccione **Tutorial_BatchSource** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.  

   Continúe con [paso 7: iniciar la orquestación y reiniciar el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md).