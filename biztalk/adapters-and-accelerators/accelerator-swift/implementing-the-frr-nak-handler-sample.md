---
title: Implementar el ejemplo del controlador NAK de FRR | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42885d6c487c6f088bfab113891ec5425d3fc82e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990285"
---
# <a name="implementing-the-frr-nak-handler-sample"></a>Implementar el ejemplo del controlador NAK de FRR
Para implementar el controlador personalizado de ejemplo NAK de FRR, agregue el proyecto de ejemplo a la solución, compilar e implementar el proyecto, enlazar e iniciar la orquestación y, a continuación, detener y reiniciar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  

### <a name="to-implement-the-frr-nak-custom-handler"></a>Para implementar el controlador personalizado de NAK de FRR  

1. En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], abra la solución. En el Explorador de soluciones, haga clic en la solución, seleccione **agregar**y, a continuación, haga clic en **proyecto existente**.  

2. En el **Agregar proyecto existente** cuadro de diálogo, desplácese a  *\<unidad\>*: Acelerador de BizTalk para SWIFT\SDK\Samples\FrrHandler \Program Files\Microsoft. Seleccione **RepairSWIFTRejectedMessage.btproj**y, a continuación, haga clic en **abierto**.  

3. Generar una clave y asignar la clave al proyecto.  

4. Compile e implemente el proyecto RepairSWIFTRejectedMessage.btproj.  

5. En el Explorador de BizTalk, expanda **bases de datos de configuración de BizTalk**,  **\< *nombre del servidor*\>, BizTalkMgmtDb.dbo**, y  **Orquestaciones**, haga clic en **RepairSWIFTRejectedMessage.Orchestration_1**y, a continuación, haga clic en **enlazar**.  

6. En el **propiedades de enlace de puerto** cuadro de diálogo, seleccione el host, como BizTalkServerApplication y, a continuación, haga clic en **Aceptar**.  

7. En el Explorador de BizTalk, haga clic en **RepairSWIFTRejectedMessage.Orchestration_1**y, a continuación, haga clic en **iniciar**.  

8. En el **inicio rápido** cuadro de diálogo, haga clic en **Aceptar**.  

9. Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**. Escriba **services.msc**y, a continuación, haga clic en **Aceptar**. Haga clic en **BizTalk Service**y, a continuación, haga clic en **reiniciar**.
