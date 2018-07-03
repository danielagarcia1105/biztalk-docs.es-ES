---
title: 'Paso 8B: configurar la información de entidad para el sistema de HI | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96338c05-1440-416e-a56a-6f5b19b55a60
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2cfc31d4bc42b599d7403006f8b44a8bfab447
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973749"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a>Paso 8B: configurar la información de entidad para el sistema de HI
En este paso, configure la información de entidad para el sistema de HI.  
  
### <a name="to-configure-the-hi-system-party-information"></a>Para configurar la información de entidad del sistema de HI  
  
1. En la consola de administración de BizTalk, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  
  
2. En el cuadro de diálogo Propiedades de entidad en el **nombre** , escriba **HIS**. (El valor que escriba en este cuadro debe coincidir con la instancia de mensaje original de HL7, QRY^Q01.txt MSH5.)  
  
3. En el árbol de consola, haga clic en **puertos de envío**.  
  
4. En el **puerto de envío** panel, para **nombre** en la primera fila, seleccione **HIS_Send**y, a continuación, haga clic en **Aceptar**.  
  
   Continúe con [paso 9: reiniciar BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).