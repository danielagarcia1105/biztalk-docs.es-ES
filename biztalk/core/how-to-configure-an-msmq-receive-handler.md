---
title: "Cómo configurar controlador de recepción de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive handlers, MSMQ adapters
- configuring [MSMQ adapters], receive handlers
- MSMQ adapters, receive handlers
ms.assetid: d6d82098-3a73-44e2-80d5-143f77e919cc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f34e1b3f399c93bd92aa9c4e07f6e0082d25204
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-msmq-receive-handler"></a>Cómo configurar un controlador de recepción de MSMQ
Utilice el procedimiento siguiente para cambiar el host al que está asociado el controlador de recepción de MSMQ.  
  
> [!NOTE]
>  Cada host solo se puede asociar a un controlador de recepción.  
  
### <a name="to-change-the-host-with-which-the-msmq-receive-handler-is-associated"></a>Para cambiar el host al que está asociado el controlador de recepción de MSMQ  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda  **Adaptadores**.  
  
2.  En la lista de adaptadores expandida, haga clic en **MSMQ**, en el panel derecho, haga el controlador de recepción que desea configurar y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de controlador de adaptador** cuadro de diálogo la **General** ficha la **nombre de Host** lista, seleccione el host al que se asociará el controlador de recepción.  
  
4.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Configurar el adaptador MSMQ](../core/configuring-the-msmq-adapter.md)