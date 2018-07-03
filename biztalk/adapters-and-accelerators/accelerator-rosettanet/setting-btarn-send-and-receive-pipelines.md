---
title: Configuración de envío BTARN y canalizaciones de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, modifying
- modifying, send pipelines
- receive pipelines, modifying
- modifying, receive pipelines
ms.assetid: 00960de0-3763-40aa-9e4b-1fedc7f1eea6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fa753193ada7cd90fb2f65d88e2ac9928cf1748
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001477"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a>Configuración de envío BTARN y canalizaciones de recepción
De forma predeterminada, Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza la norma [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización (Microsoft.Solutions.BTARN.Pipelines.Send) y el estándar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] (Microsoft.Solutions.BTARN.Pipelines.Receive) de la canalización de recepción al crear asociado puertos de envío. Sin embargo, puede cambiar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración que se usará una canalización de BizTalk existente o una canalización personalizada que haya creado. Todo uso de acuerdos entre socios comerciales y todos los socios y organizaciones principales, el mismo envío canalización y la misma canalización de recepción.  
  
 Al crear un socio, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] crea dos puertos de envío para ese socio usar uno asincrónico y sincrónico: \< *nombre del asociado de*\>. Puerto de envío asincrónico y \< *nombre del asociado de*\>. Puerto de envío de sincronización. Estos predeterminado de puertos de envío al estándar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización el valor predeterminado es el estándar de recepción de canalización y el puerto de envío de sincronización [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización de recepción.  
  
> [!NOTE]
>  Cambiar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] de canalización en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console podría restablecer las propiedades que puede cambiar directamente en el Explorador de BizTalk.  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a>Para cambiar el envío o la canalización de recepción que usa BTARN  
  
1. Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.  
  
2. En la consola de administración de BTARN, haga clic en el [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] nodo y, a continuación, haga clic en **propiedades**.  
  
3. En el cuadro de diálogo Propiedades globales, seleccione una canalización diferente en la lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
4. En el **instancias de Host** nodo bajo el [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración** nodo, detenga y reinicie el host.  
  
   > [!NOTE]
   >  Los cambios realizados en las canalizaciones solo tendrá efecto si reinicia el servidor BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Habilitar el seguimiento de BAM](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)