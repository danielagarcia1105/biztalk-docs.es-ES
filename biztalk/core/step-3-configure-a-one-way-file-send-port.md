---
title: 'Paso 3: Configurar un puerto de envío de archivos unidireccional | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67cc96dfccc7256681887290ef37261c4c7fecb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987925"
---
# <a name="step-3-configure-a-one-way-file-send-port"></a>Paso 3: Configurar un puerto de envío de archivos unidireccional
En este paso, configurará un puerto de envío de archivos unidireccional que consume el mensaje de respuesta recibido de la interfaz REST y lo copia en una ubicación de archivo.  

### <a name="to-configure-a-file-send-port"></a>Procedimiento para configurar un puerto de envío de FILE  

1. Desde la consola de administración de BizTalk Server, bajo el **BizTalk Application 1** nodo, haga clic en **puertos de envío**, apunte a **New**y, a continuación, haga clic en **estático Puerto de envío unidireccional**.  

2. En la ficha General, haga lo siguiente:  

   |Use|Para|  
   |--------------|----------------|  
   |**Nombre**|Tipo **SendPortOutAzureMarketPlaceData**.|  
   |**Tipo**|Seleccione **archivo**.|  
   |**Controlador de envío**|Seleccionar **BizTalkServerApplication**.|  
   |**Canalización de envío**|Seleccione **PassThruTransmit**.|  

    Haga clic en **configurar**.  

3. Desde Propiedades de transporte de archivo, haga lo siguiente:  


   |      Use      |                                                              Para                                                               |
   |--------------------|---------------------------------------------------------------------------------------------------------------------------------------|
   | **Carpeta de recepción** | Escriba una ubicación en la que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copia el mensaje de respuesta. |
   |   **Nombre de archivo**    |                                                       Conservar `%MessageID%.xml`                                                        |


4. En el **filtros** ficha, especifique el filtro para consumir todos los mensajes que se escriben en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] base de datos de cuadro de mensaje que creó en el puerto de recepción [paso 2: configurar un puerto de envío de WCF-WebHttp de bidireccional](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).  


   |              |                                       |
   |--------------|---------------------------------------|
   | **Propiedad** |         Establecido en **BTS. SPName**         |
   | **Operador** |             Establecido en **==**             |
   |  **Value**   | Establecido en `SendPortRESTAzureMarketPlace` |


5. Haga clic en **Aceptar**.  

## <a name="see-also"></a>Vea también  
 [Tutorial 5: Invocar una interfaz REST con BizTalk Server](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)