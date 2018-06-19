---
title: Establecer los tiempos de espera para una orquestación de proceso público y un adaptador de HTTP | Documentos de Microsoft
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
ms.openlocfilehash: 339f4eb5fa11b23602d05f8cd75c30ca3aa16279
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963298"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a>Establecer los tiempos de espera para una orquestación de proceso público y un adaptador de HTTP
Cuando se utiliza una orquestación de proceso público con un adaptador de HTTP en un escenario sincrónico, debe establecer los tiempos de espera para cada uno de ellos correctamente. El valor de tiempo de espera para la orquestación (tiempo para realizar) debe ser menor que el tiempo de espera para el adaptador HTTP (tiempo de espera de solicitud). Esto es porque si la configuración del adaptador de HTTP es menor, pudo instalar el adaptador de tiempo de espera antes de la orquestación. Esto proporciona al control de adaptador del proceso. La orquestación debe tener el control del proceso; por lo tanto, su valor de tiempo de espera debe ser menor.  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a>Para establecer la configuración de tiempo de espera del adaptador de HTTP  
  
1.  En el Explorador de BizTalk, expanda **puertos de envío**y, a continuación, haga doble clic en el puerto de envío HTTP con la orquestación de proceso público.  
  
2.  En la ventana Propiedades de puerto de envío, haga clic en el botón de puntos suspensivos (**...** ) para **dirección (URI)**.  
  
3.  En la ventana de propiedades de transporte HTTP, en el panel General, en la **solicitar tiempo de espera (seg.)** , escriba un valor adecuado para el tiempo de espera. Este valor debe ser mayor que el **tiempo para realizar** establecer para el proceso de interfaz de socio (PIP) pertinentes.  
  
4.  Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a>Para establecer la configuración de tiempo de espera para la orquestación de proceso público  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en  **Acelerador de BizTalk para RosettaNet Management Console**.  
  
2.  Expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en **configuración del proceso**.  
  
3.  Haga clic en el PIP que desea establecer el tiempo de espera de y, a continuación, haga clic en **propiedades**.  
  
4.  En el cuadro de diálogo de theProperties, en la **actividad** ficha la **tiempo para realizar** , escriba un valor adecuado que es menor que el tiempo de espera del adaptador HTTP establecer y, a continuación, haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)