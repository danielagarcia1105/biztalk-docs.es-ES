---
title: Habilitar o deshabilitar el seguimiento de BAM | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1132c41e9a017e42139d988d1588f79d7d3afaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-or-disabling-bam-tracking"></a>Habilitar o deshabilitar el seguimiento de BAM
Puede habilitar o deshabilitar el seguimiento en cualquier momento, incluso aunque el proceso de reparación de mensajes y nuevo transmisión tiene transacciones en proceso de BAM. Sin embargo, si deshabilita el seguimiento de BAM mientras las transacciones están en curso, los datos de BAM pueden estar incompletos en las transacciones. Si esto ocurre, la tabla de historial todavía contendrá datos precisos de todas las instancias.  
  
 Para obtener información acerca de cómo habilitar o deshabilitar el seguimiento como parte del proceso de configuración de componente de A4SWIFT de BAM, consulte [establecer las propiedades de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md).  
  
### <a name="to-enable-or-disable-bam-tracking"></a>Para habilitar o deshabilitar el seguimiento de BAM  
  
1.  En el cliente Web de perfil, haga clic en **Acelerador de BizTalk para SWIFT** en el árbol de consola y, a continuación, haga clic en **propiedades**.  
  
2.  En el cuadro de diálogo Propiedades globales, deshabilitar el seguimiento de BAM mediante anulando la selección de **Habilitar seguimiento de BAM**, o habilitar el seguimiento de BAM mediante selecciónelo.  
  
3.  Haga clic en **Aceptar**.  
  
4.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, **grupo de BizTalk**y, a continuación, **configuración de plataforma**. Haga clic en **instancias de Host**.  
  
5.  En el panel de detalles, haga clic en la instancia de host y, a continuación, haga clic en **reiniciar**.  
  
## <a name="see-also"></a>Vea también  
 [Establecer las propiedades de A4SWIFT](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)