---
title: 'Paso 8C: configurar la información de entidad para el sistema de HI | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1d853e381da6cbfbbe96fa805ca6396a1b7aae
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961076"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a>Paso 8C: configurar la información de entidad para el sistema de alta
En este paso, configurará la información de entidad para el sistema de alta.  
  
### <a name="to-configure-the-hi-system-party-information"></a>Para configurar la información de entidad del sistema de alta  
  
1.  En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_HISystem**.  
  
3.  En el árbol de consola, haga clic en **puertos de envío**.  
  
4.  En el panel de puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_MllpSend**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
6.  En el Explorador de configuración de BTAHL7, seleccione la **MSH mapa** ficha y, a continuación, haga lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**MSH3**|Tipo de **BTAHL7**, **IE**, y **UUID** en el primer, segundo y tercer mensaje cuadros, respectivamente.|  
    |**MSH5**|Tipo de **HI**, **System**, y **GUID** en el primer, segundo y tercer mensaje cuadros, respectivamente.|  
    |**MSH9**|Tipo de **ADT** y **A04** en los cuadros de mensaje de primer y segundo, respectivamente.|  
    |**MSH12**|Tipo de **2.4**.|  
    |**MSH15**|Seleccione **SU** para enviar confirmaciones después de la transmisión correcta de un mensaje.|  
    |**MSH16**|Seleccione **NE** nunca enviar confirmaciones.|  
  
7.  Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
    > [!NOTE]
    >  No es necesario que cree información de entidad para el sistema de motor de interfaz de BTAHL7, porque la información de configuración no es necesaria para este escenario.  
  
 Continúe con [paso 9: reinicie el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).