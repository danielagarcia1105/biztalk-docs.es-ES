---
title: 'Paso 8: configurar la información de entidad para el sistema de HI | Documentos de Microsoft'
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
ms.openlocfilehash: 460840cf3bbbd6556b1684b25851a16778be92b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206316"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a>Paso 8: configurar la información de entidad para el sistema de alta
En este paso, configurará la información de entidad para el sistema de alta.  
  
### <a name="to-configure-the-hi-system-party-information"></a>Para configurar la información de entidad del sistema de alta  
  
1.  En la consola de administración de BizTalk, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **HIS**. (El valor que escriba en este cuadro debe coincidir con la instancia original del mensaje HL7, QRY^Q01.txt MSH5.)  
  
3.  En el árbol de consola, haga clic en **puertos de envío**.  
  
4.  En el **puerto de envío** panel, para **nombre** en la primera fila, seleccione **HIS_Send**y, a continuación, haga clic en **Aceptar**.  
  
 Continúe con [paso 9: reinicie el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).