---
title: Configuración de envío BTARN y canalizaciones de recepción | Documentos de Microsoft
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
ms.openlocfilehash: a6f5e996b7046e94c90df0269381391a3aed3084
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964514"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a>Configuración de envío BTARN y canalizaciones de recepción
De forma predeterminada, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza la norma [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización (Microsoft.Solutions.BTARN.Pipelines.Send) y el estándar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] (Microsoft.Solutions.BTARN.Pipelines.Receive) de la canalización de recepción cuando se crea puertos de envío de socios comerciales. Sin embargo, puede cambiar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuración para que use una canalización de BizTalk existente o una canalización personalizada que haya creado. Acuerdos de socios comerciales y todos los socios y organizaciones internas, todo, use el mismo enviar canalización y la misma canalización de recepción.  
  
 Cuando se crea un asociado, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] crea dos puertos de envío para ese socio usar uno asincrónica y otra sincrónica: \< *nombre del asociado de*\>. Puerto de envío asincrónico y \< *nombre del asociado de*\>. Puerto de envío de sincronización. Estos predeterminado de puertos de envío con el estándar [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar canalización el valor predeterminado es el estándar de recepción de canalización y el puerto de envío de sincronización [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] canalización de recepción.  
  
> [!NOTE]
>  Cambiar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] de canalización en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración puede restablecer las propiedades que se cambió directamente en el Explorador de BizTalk.  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a>Para cambiar el envío o la canalización de recepción que usa BTARN  
  
1.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, haga clic en el [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] nodo y, a continuación, haga clic en **propiedades**.  
  
3.  En el cuadro de diálogo Propiedades globales, seleccione una canalización diferente en la lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
4.  En el **instancias de Host** nodo bajo el [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración** nodo, detenga y reinicie el host.  
  
    > [!NOTE]
    >  Los cambios realizados en las canalizaciones solo aplicarán si reinicia el servidor BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)   
 [Habilitar el seguimiento de BAM](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)