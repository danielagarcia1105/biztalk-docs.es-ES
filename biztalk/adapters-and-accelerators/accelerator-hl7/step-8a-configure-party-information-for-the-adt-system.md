---
title: 'Paso 8: configurar la información de entidad para el sistema ADT | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42b92e3b55cd4de181103e28526abf3ecde29412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962050"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a>Paso 8: configurar la información de entidad para el sistema ADT
En este paso, configurará la información de entidad para el sistema ADT.  
  
### <a name="to-configure-the-adt-system-party-information"></a>Para configurar la información de entidad del sistema ADT  
  
1.  En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_ADTSystem**. (El valor que escriba en este cuadro es de la instancia de mensaje HL7 original, ADT^A03.txt MSH3).  
  
3.  En el árbol de consola, haga clic en **puertos de envío**.  
  
4.  En el panel de puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendAck_ADT**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
6.  En el Explorador de configuración BTAHL7, seleccione la **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.  
  
7.  Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
 Continúe con [paso 8B: configurar la información de entidad para el sistema RX](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).