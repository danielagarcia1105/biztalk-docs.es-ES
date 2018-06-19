---
title: Establecer el tiempo de espera de retraso FRR | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbf4c08984876627c0f11f935b0be3e32769b5f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214004"
---
# <a name="setting-the-frr-delay-time-out"></a>Establecer el tiempo de espera de retraso FRR
Debe configurar la orquestación FRR tiempo de espera después de algún tiempo, por lo que no esperará la respuesta FNN indefinidamente. Si la duración de tiempo de espera expira, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] publica los mensajes ha superado el tiempo de espera en un controlador de tiempo de espera personalizado.  
  
### <a name="to-set-the-frr-delay-time-out"></a>Para establecer el tiempo de espera de retraso FRR  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **regedit**y, a continuación, haga clic en **Aceptar**.  
  
2.  En el panel izquierdo del Editor del registro, pase a la aceleración de mi equipo/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk para SWIFT/FRR.  
  
    > [!IMPORTANT]
    >  El rol se agregará en la posición en el flujo de trabajo que se define en el nodo funciones. Para cambiar esa posición, debe realizar el paso 8 para cambiar el orden de los roles en el nodo funciones.  
  
3.  En el panel derecho del Editor del registro, haga doble clic en **DelayTimeout**.  
  
4.  En el **Editar valor DWORD** cuadro de diálogo, en la **datos del valor** , escriba la duración de tiempo de espera en formato hexadecimal.  
  
    > [!NOTE]
    >  El valor predeterminado para la **FRR DelayTimeout** propiedad es 600 segundos (258 Hexadecimal).  
  
5.  Haga clic en **Aceptar**.