---
title: 'Paso 8A: configurar la información de entidad para el sistema ADT | Microsoft Docs'
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
ms.openlocfilehash: 6c1a608571c9cc3f939f9387c2e3a113273af554
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969765"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a>Paso 8A: configurar la información de entidad para el sistema ADT
En este paso, configure la información de entidad para el sistema de ADT.  
  
### <a name="to-configure-the-adt-system-party-information"></a>Para configurar la información de entidad del sistema de ADT  
  
1. En la consola de administración de BizTalk Server, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  
  
2. En el cuadro de diálogo Propiedades de entidad en el **nombre** , escriba **Tutorial_ADTSystem**. (El valor que escriba en este cuadro es de la instancia de mensaje original de HL7, ADT^A03.txt MSH3).  
  
3. En el árbol de consola, haga clic en **puertos de envío**.  
  
4. En el panel puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendAck_ADT**y, a continuación, haga clic en **Aceptar**.  
  
5. Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
6. En el Explorador de configuración de BTAHL7, seleccione el **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.  
  
7. Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
   Continúe con [paso 8B: configurar la información de entidad para el sistema de RX](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).