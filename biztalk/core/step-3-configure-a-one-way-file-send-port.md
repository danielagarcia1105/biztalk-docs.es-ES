---
title: "Paso 3: Configurar un puerto de envío de archivos unidireccional | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceb055f0d4d41eb82eb79cb549b082212fd1bbd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-one-way-file-send-port"></a>Paso 3: Configurar un puerto de envío de archivos unidireccional
En este paso, configurará un puerto de envío de archivos unidireccional que consume el mensaje de respuesta recibido de la interfaz REST y lo copia en una ubicación de archivo.  
  
### <a name="to-configure-a-file-send-port"></a>Procedimiento para configurar un puerto de envío de FILE  
  
1.  Desde la consola de administración de BizTalk Server, en la **BizTalk Application 1** nodo, haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **estático Puerto de envío unidireccional**.  
  
2.  En la ficha General, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Tipo de **SendPortOutAzureMarketPlaceData**.|  
    |**Tipo**|Seleccione **archivo**.|  
    |**Controlador de envío**|Seleccionar **BizTalkServerApplication**.|  
    |**Canalización de envío**|Seleccione **PassThruTransmit**.|  
  
     Haga clic en **configurar**.  
  
3.  Desde Propiedades de transporte de archivo, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Carpeta de recepción**|Escriba una ubicación en la que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia el mensaje de respuesta.|  
    |**Nombre de archivo**|Conservar`%MessageID%.xml`|  
  
4.  En el **filtros** ficha, especifique el filtro para consumir todos los mensajes que se escriben en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensaje mediante el puerto de recepción que creó en [paso 2: configurar un puerto de envío de WCF-WebHttp de bidireccional](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).  
  
    |||  
    |-|-|  
    |**Propiedad**|Establecido en **BTS. SPName**|  
    |**Operador**|Establecido en**==**|  
    |**Valor**|Establecido en`SendPortRESTAzureMarketPlace`|  
  
5.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial 5: Invocar una interfaz REST con BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)