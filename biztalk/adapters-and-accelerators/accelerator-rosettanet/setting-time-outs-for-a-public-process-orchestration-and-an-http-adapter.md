---
title: Configuración de los tiempos de espera de una orquestación de proceso público y un adaptador de HTTP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, HTTP adapters
- public processes, orchestrations
- orchestrations, time-outs
- public processes, time-outs
- orchestrations, public-process orchestrations
- HTTP adapters, public processes
- HTTP adapters, time-outs
ms.assetid: 82fd64ac-6191-410c-94b3-8a3d1ff2611f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e0977589e310746e2c75c1f89fdd2c41ecb86aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976717"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a>Configuración de los tiempos de espera de una orquestación de proceso público y un adaptador de HTTP
Cuando se utiliza una orquestación de proceso público con un adaptador de HTTP en un escenario sincrónico, debe establecer correctamente los tiempos de espera para cada uno. El valor de tiempo de espera para la orquestación (tiempo para realizar) debe ser menor que el tiempo de espera del adaptador de HTTP (tiempo de espera de solicitud). Esto es porque si la configuración del adaptador de HTTP es menor, el adaptador podría tiempo de espera antes de la orquestación. Esto proporciona el control de adaptador del proceso. La orquestación debe estar en el control del proceso; por lo tanto, su valor de tiempo de espera debe ser menor.  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a>Para establecer la configuración de tiempo de espera del adaptador de HTTP  
  
1.  En el Explorador de BizTalk, expanda **puertos de envío**y, a continuación, haga doble clic en el puerto de envío HTTP utilizado con la orquestación de proceso público.  
  
2.  En la ventana Propiedades de puerto de envío, haga clic en el botón de puntos suspensivos (**...** ) para **dirección (URI)**.  
  
3.  En la ventana Propiedades de transporte HTTP, en el panel General, en el **(s) de tiempo de espera de solicitud** , escriba un valor adecuado para el tiempo de espera. Este valor debe ser mayor que el **tiempo para realizar** establecer para el proceso de interfaz de socio (PIP) pertinentes.  
  
4.  Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a>Para establecer la configuración de tiempo de espera para la orquestación de proceso público  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en  **Acelerador de BizTalk para RosettaNet Management Console**.  
  
2. Expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en **configuración del proceso**.  
  
3. Haga clic en el PIP que desea establecer el tiempo de espera para y, a continuación, haga clic en **propiedades**.  
  
4. En el cuadro de diálogo theProperties, en el **actividad** ficha la **tiempo para realizar** , escriba un valor adecuado que es menor que el tiempo de espera del adaptador HTTP establecer y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)