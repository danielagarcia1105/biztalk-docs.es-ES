---
title: Tipo de enlace no admitido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5556a7d7-f092-4f69-9561-88f51ac46cc9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98d156f22b5e903cd704dc109f98435203bd6ba8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286596"
---
# <a name="unsupported-binding-type"></a>Tipo de enlace no compatible.
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|Identificador del evento|0|  
|Origen del evento|0|  
|Componente|0|  
|Nombre simbólico|0|  
|Texto del mensaje|Tipo de enlace no compatible.|  
  
## <a name="explanation"></a>Explicación  
 Se eligió el enlace MsmqIntegration, pero no era compatible con el adaptador de WCF.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el adaptador de WCF-NetMsmq. Si fuera necesario intercambiar los mensajes MSMQ nativos, use el adaptador de BizTalk MSMQ.  
  
 Para obtener más información sobre la configuración de adaptadores, vea el recurso siguiente:  
  
-   [Configurar el adaptador de WCF-NetMsmq](../core/configuring-the-wcf-netmsmq-adapter.md)