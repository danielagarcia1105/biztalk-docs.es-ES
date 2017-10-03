---
title: "Paso 2: Modificar o crear el envío y puertos de recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61f201f8b20d5824b1b037cc61edaa1d64729135
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a>Paso 2: Modificar o crear el envío y puertos de recepción
Necesitará envío de archivos y los puertos de recepción para el lote en / lote tutorial. Si hace clic en el **iniciar Tutorial** botón al final de la instalación de la edición Enterprise de [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] crea estos puertos: un puerto de envío denominado Tutorial_BTAHL7Drop y un puerto de recepción denominado Tutorial_BTAHL7PickUp. Si dispone de estos puertos, deberá modificar el puerto de envío Tutorial_BTAHL7Drop.  
  
 Si [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el programa de instalación no crear el envío y puertos de recepción para usted, vea el procedimiento "Para crear el BIBOTutorialPickup puerto de recepción" en este tema y, a continuación, consulte el procedimiento "Para crear el BIBOTutorialDrop puerto de envío" también en este tema.  
  
### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a>Para modificar el puerto de envío Tutorial_BTAHL7Drop  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda  **Aplicación de BizTalk 1**.  
  
3.  Haga clic en **puertos de envío**, haga clic en **Tutorial_BTAHL7Drop**y, a continuación, haga clic en **propiedades**.  
  
4.  En el árbol de consola, haga clic en **filtros**.  
  
5.  En el **filtros** panel, en la segunda fila, seleccione **BTAHL7Schemas.MessageClass** para **propiedades**, seleccione  **==**  para **Operador**y el tipo de **MessageClass2X** para **valor**. Haga clic en **Entrar**.  
  
6.  Establecer **Agrupar por** en el **BTS. ReceivePortName** línea a **o**y, a continuación, haga clic en **Aceptar**.  
  
7.  En el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ventana de administración, expanda **configuración de plataforma**y expanda **instancias de Host**. Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.  
  
    > [!NOTE]
    >  Solo use los procedimientos siguientes si ha instalado la edición Standard de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], o si no hizo clic en el **iniciar Tutorial** botón al configurar [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].  
  
### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a>Para crear el Tutorial_BTAHL7Pickup puerto de recepción y ubicación  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda  **Aplicación de BizTalk 1**.  
  
3.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en **puerto de recepción unidireccional**.  
  
4.  En el cuadro de diálogo Propiedades de puerto de recepción, en el **nombre** , escriba **Tutorial_BTAHL7PickUp**.  
  
5.  Haga clic en **aplicar** para enlazar el puerto y, a continuación, haga clic en **Aceptar**.  
  
6.  Haga clic en **ubicaciones de recepción**, seleccione **New**y, a continuación, haga clic en **ubicación de recepción unidireccional**.  
  
7.  En el, seleccione un cuadro de diálogo de puerto de recepción, haga clic en **Tutorial_BTAHL7PickUp**y, a continuación, haga clic en **Aceptar**.  
  
8.  En el cuadro de diálogo Propiedades de la ubicación de recepción, en el **nombre** , escriba **Tutorial_FileReceiveLoc**.  
  
9. En el **transporte** sección, para la **tipo** cuadro de texto, haga clic en la lista desplegable y, a continuación, seleccione **archivo**.  
  
10. Haga clic en el **configurar** situado a la derecha de la lista desplegable de tipo.  
  
11. En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Vaya a  **\<**  *unidad***>: \Program BizTalk \<versión > Accelerator for Tutorial\Tutorial_BTAHL7PickUp HL7\SDK\End-to-End** . **Nota:** trata la ruta de acceso a la ubicación en el sistema de archivos o un recurso compartido público desde donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] recogerá el archivo.|  
    |**Máscara de archivo**|Tipo de  **\*.txt**.|  
  
12. Haga clic en **Aceptar**.  
  
13. En el cuadro de diálogo Propiedades de la ubicación de recepción, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Controlador de recepción**|Mantener **BizTalkServerApplication** como seleccionado.|  
    |**La canalización de recepción**|Seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**.|  
  
14. Haga clic en **Aceptar**.  
  
15. En el Explorador de BizTalk, haga clic en **Tutorial_FileReceiveLoc**y, a continuación, haga clic en **habilitar**.  
  
### <a name="to-create-the-tutorialbtahl7drop-send-port"></a>Para crear el puerto de envío Tutorial_BTAHL7Drop  
  
1.  En el [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] consola de administración, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el cuadro de diálogo Propiedades de puerto de envío, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Tutorial_BTAHL7Drop**.|  
    |**Tipo**|Seleccione **archivo** en la lista desplegable.|  
    |**Configurar**|Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.|  
  
3.  En el cuadro de diálogo Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de destino**|Vaya a  **\<**  *unidad***: > \Program BizTalk \<versión > Accelerator for Tutorial\Tutorial_BTAHL7Drop HL7\SDK\End-to-End** . **Nota:** se trata de la ruta de acceso a la ubicación en el sistema de archivos o un recurso compartido público al que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] escribirá el archivo.|  
    |**Nombre de archivo**|Tipo de **%MessageID%.txt** (tenga en cuenta que la extensión txt, xml no).|  
  
4.  Haga clic en **Aceptar**.  
  
5.  En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline** en la lista desplegable.  
  
6.  En el árbol de consola, haga clic en **filtros**, y, a continuación, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad**|Seleccione **BTS. ReceivePortName** en la lista desplegable.|  
    |**Operador**|Deje  **==**  como el operador.|  
    |**Valor**|Tipo de **Tutorial_BTAHL7PickUp**.|  
    |**Agrupar por**|Seleccione **o** en la lista desplegable.|  
    |**Propiedad**|Seleccione **BTAHL7Schemas.MessageClass**.|  
    |**Operador**|Deje  **==**  como el operador.|  
    |**Valor**|Tipo de **MessageClass2X**.|  
  
7.  Haga clic en **Entrar**. En el panel en la parte inferior del cuadro de diálogo, compruebe que la expresión de filtro es correcta.  
  
8.  Haga clic en **Aceptar**.  
  
9. En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_BTAHL7Drop**y, a continuación, haga clic en **iniciar**.  
  
10. Expanda **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**. Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **reiniciar**.  
  
 Continúe con [paso 3: probar el lote / lote escenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).