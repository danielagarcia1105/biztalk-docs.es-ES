---
title: 'Paso 1: Configurar un archivo de ubicación de recepción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df591263-964a-4ad8-bc3a-a553de8dae4f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78f8bccc187bf310b8426fc3d5fee36add44a9f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278260"
---
# <a name="step-1-configure-a-file-receive-location"></a>Paso 1: Configurar un archivo de ubicación de recepción
En este tema configurará una ubicación de recepción de FILE que consume el mensaje de solicitud ficticio que coloca en una carpeta de archivos para invocar el puerto de envío.  
  
> [!NOTE]
>  Los pasos de este tutorial se supone que usa la aplicación predeterminada (**BizTalk Application 1**) para crear la solución. También puede crear otra aplicación y realizar los mismos pasos en cualquier aplicación.  
  
### <a name="to-configure-a-file-receive-location"></a>Para configurar una ubicación de recepción de archivos  
  
1.  Desde la consola de administración de BizTalk Server, en la **BizTalk Application 1** nodo, haga clic en **puertos de recepción**, seleccione **New**y, a continuación, haga clic en  **Unidireccional puerto de recepción**.  
  
2.  En la ficha General, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **ReceivePortRestAzureMarketPlace**.|  
    |**Habilitar enrutamiento para mensajes con errores**|(clear)|  
  
3.  Haga clic en **ubicaciones de recepción**y, a continuación, haga clic en **nuevo**.  
  
4.  Desde Ubicación de recepción1 - Propiedades de ubicación de recepción, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **ReceiveLocationAzureMarketPlace**.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Controlador de recepción**|Seleccionar **BizTalkServerApplication**.|  
    |**La canalización de recepción**|Seleccione **PassThruReceive**.|  
  
5.  Haga clic en **configurar**.  
  
6.  Desde Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Escriba una ubicación en la que colocará el mensaje de solicitud ficticio.|  
    |**Nombre de archivo**|Conservar`*.xml`|  
  
7.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 5: Invocar una interfaz REST con BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)