---
title: 'Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo | Documentos de Microsoft'
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
ms.openlocfilehash: 62581310d4260ecb5b1162df1f52b0170d791d57
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005510"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a>Paso 6: Crear un puerto de envío para entregar el ADT ^ A03 mensaje en el sistema de recepción mediante el adaptador de archivo
En este paso, creará el puerto de envío para la farmacia sistema (RX) mediante el adaptador de archivo.  
  
### <a name="to-create-the-tutorialsendmsgrx-send-port"></a>Para crear el puerto de envío Tutorial_sendMsg_RX  
  
1.  En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
2.  En el **propiedades de puerto de envío** diálogo cuadro, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **Tutorial_sendMsg_RX**.|  
    |**Tipo de transporte**|Seleccione **archivo** en la lista desplegable.|  
    |**Configurar**|Haga clic en **configurar** para abrir el **propiedades de transporte de archivo** cuadro de diálogo.|  
  
3.  En el cuadro de diálogo Propiedades de transporte de archivo, realice las siguientes acciones y, a continuación, haga clic en **Aceptar**.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de destino**|Vaya a  **\<**  *unidad***:\>\Program BizTalk \<versión\> acelerador HL7\SDK\End-to-end Tutorial\Tutorial_sendMsg_RX**.|  
    |**Nombre de archivo**|Tipo de **%MessageID%.txt** (reemplazar la extensión .xml con la extensión .txt).|  
  
4.  En el **propiedades de puerto de envío** cuadro de diálogo para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**.  
  
5.  En el panel izquierdo, seleccione **filtros**, y, a continuación, realice las siguientes acciones. Haga clic en **Aceptar** para continuar.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Propiedad** (primera línea)|Seleccione **BTS. MessageType** en la lista desplegable.|  
    |**Operador**|Seleccione **! =** en la lista desplegable.|  
    |**Valor**|Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.|  
    |**Agrupar por**|Seleccione **o** en la lista desplegable.|  
    |**Propiedad** (segunda línea)|Haga clic en el campo **propiedad**y, a continuación, seleccione **BTS. MessageType** en la lista desplegable.|  
    |**Operador**|Seleccione **! =** en la lista desplegable.|  
    |**Valor**|Tipo de **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**|  
    |**Agrupar por**|Seleccione **AND** en la lista desplegable.|  
    |**Propiedad** (tercera línea)|Seleccione **BTAHL7Schemas.MSH3_1**.|  
    |**Operador**|Seleccione  **==**  en la lista desplegable.|  
    |**Valor**|Tipo de **Tutorial_ADTSystem**.|  
  
    > [!NOTE]
    >  El primer filtro significa que el sistema de información de salud (HIS) se suscribe a un mensaje, no una confirmación. El segundo filtro significa que su se suscribe a mensajes cuyo origen es la admisión de descarga y el sistema de transferencia (ADT).  
  
    > [!NOTE]
    >  BTAHL7 coloca el mensaje en la ubicación de destino de archivo \< *unidad*\>: programa FilesMicrosoft BizTalk <version> Acelerador para TutorialTutorial_sendMsg_RX HL7SDKEnd-to-End.  
  
6.  Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar.**  
  
7.  En la consola de administración, haga clic en **puertos de envío**, haga clic en **Tutorial_sendMsg_RX**y, a continuación, haga clic en **iniciar**.  
  
 Continúe con [paso 7: crear un puerto de envío para entregar el ADT ^ A03 mensaje para su uso del adaptador MLLP](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md).