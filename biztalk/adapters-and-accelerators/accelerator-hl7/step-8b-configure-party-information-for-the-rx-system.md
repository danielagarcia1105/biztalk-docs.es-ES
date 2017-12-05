---
title: "Paso 8: configurar la información de entidad para el sistema RX | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce204ed2e892a6206f6e2db28bbccd0201e2f0f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a>Paso 8: configurar la información de entidad para el sistema RX
En este paso, configurará la información de entidad para el sistema de recepción.  
  
### <a name="to-configure-the-rx-system-party-information"></a>Para configurar la información de entidad del sistema RX  
  
1.  En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_RXSystem**.  
  
3.  En el árbol de consola, haga clic en **puertos de envío**.  
  
4.  En el panel de puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendMsg_RX**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
6.  En el Explorador de configuración BTAHL7, seleccione la **MSH mapa** ficha y, a continuación, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**MSH3**|Tipo de **BTAHL7** en el cuadro de texto a la izquierda.|  
    |**MSH5**|Tipo de **Tutorial_RXSystem** en el cuadro de texto a la izquierda.|  
  
7.  Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
 Continúe con [paso 8C: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).