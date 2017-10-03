---
title: "Cómo configurar canalizaciones de recepción para TIBCO Rendezvous | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, setting
- setting receive pipelines
- pipelines, setting
ms.assetid: d40e0225-0313-4e9b-8d92-464870aabf71
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dd29852ab41af0d5b1f4ed0d184c158a23b5ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-receive-pipelines-for-tibco-rendezvous"></a>Establecimiento de canalizaciones de recepción para TIBCO Rendezvous
El adaptador de Microsoft BizTalk para TIBCO Rendezvous requiere que se establezcan el controlador y la canalización de recepción.  
  
### <a name="to-set-the-pipeline"></a>Procedimiento para establecer la canalización  
  
1.  Establecer el **controlador de recepción** a **BizTalkServerIsolatedHost** en la lista.  
  
2.  Establecer el **canalización de recepción** a **XMLReceive** o cualquier canalización equivalente.  
  
3.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Controladores de recepción de creación TIBCO Rendezvous](../core/creating-tibco-rendezvous-receive-handlers.md)