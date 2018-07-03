---
title: 'Paso 8B: configurar la información de entidad para el sistema de RX | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ed8dfaeb333c1b35ea64a5d52a53ebce509729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008405"
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a>Paso 8B: configurar la información de entidad para el sistema de RX
En este paso, configure la información de entidad para el sistema de RX.  

### <a name="to-configure-the-rx-system-party-information"></a>Para configurar la información de entidad del sistema de RX  

1. En la consola de administración de BizTalk Server, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  

2. En el cuadro de diálogo Propiedades de entidad en el **nombre** , escriba **Tutorial_RXSystem**.  

3. En el árbol de consola, haga clic en **puertos de envío**.  

4. En el panel puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendMsg_RX**y, a continuación, haga clic en **Aceptar**.  

5. Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  

6. En el Explorador de configuración de BTAHL7, seleccione el **asignación de MSH** pestaña y, a continuación, haga lo siguiente:  


   | Use |                    Para                    |
   |----------|--------------------------------------------------|
   | **MSH3** |      Tipo **BTAHL7** en el cuadro de texto a la izquierda.       |
   | **MSH5** | Tipo **Tutorial_RXSystem** en el cuadro de texto a la izquierda. |


7. Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  

   Continúe con [paso 8c: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).