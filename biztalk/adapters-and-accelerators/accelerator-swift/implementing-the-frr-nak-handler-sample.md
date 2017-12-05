---
title: Implementar el ejemplo del controlador NAK FRR | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a91c0303c9abdf6b1d8c434869445f3c84348935
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="implementing-the-frr-nak-handler-sample"></a>Implementar el ejemplo del controlador FRR NAK
Para implementar el controlador personalizado de ejemplo FRR NAK, agregar el proyecto de ejemplo a la solución, compilar e implementar el proyecto, enlazar e iniciar la orquestación y, a continuación, detenga y reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-implement-the-frr-nak-custom-handler"></a>Para implementar el controlador de FRR NAK personalizado  
  
1.  En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], abra la solución. En el Explorador de soluciones, haga clic en la solución, seleccione **agregar**y, a continuación, haga clic en **proyecto existente**.  
  
2.  En el **Agregar proyecto existente** cuadro de diálogo, desplácese a  *\<unidad\>*: \Program Acelerador de BizTalk para SWIFT\SDK\Samples\FrrHandler. Seleccione **RepairSWIFTRejectedMessage.btproj**y, a continuación, haga clic en **abiertos**.  
  
3.  Generar una clave y asigne la clave al proyecto.  
  
4.  Compile e implemente el proyecto RepairSWIFTRejectedMessage.btproj.  
  
5.  En el Explorador de BizTalk, expanda **bases de datos de configuración de BizTalk**,  **\<* nombre del servidor*\>, BizTalkMgmtDb.dbo** y **Orquestaciones**, haga clic en **RepairSWIFTRejectedMessage.Orchestration_1**y, a continuación, haga clic en **enlazar**.  
  
6.  En el **propiedades de enlace de puerto** cuadro de diálogo, seleccione el host, como BizTalkServerApplication y, a continuación, haga clic en **Aceptar**.  
  
7.  En el Explorador de BizTalk, haga clic en **RepairSWIFTRejectedMessage.Orchestration_1**y, a continuación, haga clic en **iniciar**.  
  
8.  En el **inicio rápido** cuadro de diálogo, haga clic en **Aceptar**.  
  
9. Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**. Escriba **services.msc**y, a continuación, haga clic en **Aceptar**. Haga clic en **BizTalk Service**y, a continuación, haga clic en **reiniciar**.