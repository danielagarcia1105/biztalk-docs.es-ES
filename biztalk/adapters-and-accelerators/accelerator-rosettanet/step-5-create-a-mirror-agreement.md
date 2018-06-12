---
title: 'Paso 5: Crear un acuerdo reflejado | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65fbb1c93b0401e8c6460c9df1f2313931c34950
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855599"
---
# <a name="step-5-create-a-mirror-agreement"></a>Paso 5: Crear un acuerdo de reflejo
En este paso, utilizará la utilidad de bucle invertido para crear un acuerdo de reflejado simular al socio comercial en el mismo equipo en el que ha configurado la organización principal. La utilidad de bucle invertido es una herramienta de línea de comandos.  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a>Para crear un acuerdo de reflejado mediante la utilidad de bucle invertido  
  
1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
2.  En el símbolo del sistema, vaya a \< *unidad*\>: \Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK. Escriba el siguiente comando y, a continuación, presione **ENTRAR**:  
  
    ```  
    Loopback /enable HOME  
    ```  
  
3.  Cuando haya finalizado el comando ejecutado en el paso 2, escriba el siguiente comando en el símbolo del sistema y, a continuación, presione **ENTRAR**:  
  
    ```  
    Loopback /mirror "Trade Agreement"   
    ```  
  
 La utilidad de bucle invertido crea automáticamente un acuerdo comercial de reflejo de la organización del asociado y de puertos de envío para la organización principal (iniciador). El socio comercial utiliza los dos nuevos puertos de envío para comunicarse con la organización principal.  
  
> [!NOTE]
>  Volver a debe reflejar el acuerdo comercial cada vez que actualice el acuerdo comercial original.  
  
## <a name="see-also"></a>Vea también  
 [Paso 6: Iniciar las orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)
