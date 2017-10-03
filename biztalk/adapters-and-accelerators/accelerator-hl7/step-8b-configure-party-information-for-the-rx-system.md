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
ms.openlocfilehash: 29ab7194e0e1b81a773c61123de9171f1c65eb0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a>Paso 8: configurar la información de entidad para el sistema RX
En este paso, configurará la información de entidad para el sistema de recepción.  
  
### <a name="to-configure-the-rx-system-party-information"></a>Para configurar la información de entidad del sistema RX  
  
1.  En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_RXSystem**.  
  
3.  En el árbol de consola, haga clic en **puertos de envío**.  
  
4.  En el panel de puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendMsg_RX**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.  
  
6.  En el Explorador de configuración BTAHL7, seleccione la **MSH mapa** ficha y, a continuación, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**MSH3**|Tipo de **BTAHL7** en el cuadro de texto a la izquierda.|  
    |**MSH5**|Tipo de **Tutorial_RXSystem** en el cuadro de texto a la izquierda.|  
  
7.  Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
 Continúe con [paso 8C: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).