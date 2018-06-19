---
title: 'Paso 3E: agregar un puerto de envío de archivo para el almacenamiento de FileAct y reenviar escenario para capturar los mensajes de Sw-ExchangeSnFResponse | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bad2ab-1ea4-4602-9dee-5b9af9be3b93
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44cf320f22f5acc2511d6327c36c54cda8f0dd1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223996"
---
# <a name="step-3e-add-a-file-send-port-for-the-fileact-store-and-forward-scenario-to-capture-sw-exchangesnfresponse-messages"></a>Paso 3E: agregar un puerto de envío de archivo para el escenario de hacia delante para capturar los mensajes de Sw-ExchangeSnFResponse y el almacenamiento de FileAct
Antes de comenzar este paso, debe completar [paso 3D: agregar un puerto de envío de FILEACT para el escenario de al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md).  
  
### <a name="to-add-a-file-send-port-to-capture-status-events"></a>Para agregar un puerto de envío de archivo para capturar los eventos de estado:  
  
1.  Iniciar **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda el grupo de BizTalk y, a continuación, expanda la aplicación de BizTalk para el que desea crear un puerto de envío.  
  
3.  Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
4.  En el **propiedades de puerto de envío** ventana, nombre el puerto de envío Tutorial_ GetStatusReports.  
  
5.  En el **propiedades de puerto de envío** ventana, desde el **tipo de transporte** lista desplegable, seleccione **archivo**y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte de archivo** cuadro de diálogo, en la **carpeta de destino** , escriba C:\SWIFTAdapterTutorial\Fileact\ StatusEvents y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **propiedades de puerto de envío** ventana, haga lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Controlador de envío**|En la lista desplegable, seleccione **BizTalkServerApplication**.|  
    |**Canalización de envío**|En la lista desplegable, seleccione **XMLTransmit**.|  
  
8.  En el **propiedades de puerto de envío** ventana, en la **filtros** ficha, realice lo siguiente:  
  
    |**Use esto**|**Para ello**|  
    |------------------|--------------------|  
    |**Propiedad**|Seleccione BTS. MessageType|  
    |**Operador**|Seleccione ==|  
    |**Valor**|Tipo Sw-HandleFileEventRequest|  
    |**Grupo**|O bien|  
    |**Propiedad**|Seleccione BTS. MessageType|  
    |**Operador**|Seleccione ==|  
    |**Valor**|Tipo Sw-ExchangeSnFResponse|