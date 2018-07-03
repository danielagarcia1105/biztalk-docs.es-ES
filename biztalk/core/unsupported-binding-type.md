---
title: Tipo de enlace no admitido | Microsoft Docs
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
ms.openlocfilehash: 4a1090157a3b39dea62a3c95cb787b91e0a33bfc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004341"
---
# <a name="unsupported-binding-type"></a>Tipo de enlace no compatible.
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                              Tipo de enlace no compatible.                              |
  
## <a name="explanation"></a>Explicación  
 Se eligió el enlace MsmqIntegration, pero no era compatible con el adaptador de WCF.  
  
## <a name="user-action"></a>Acción del usuario  
 Use el adaptador de WCF-NetMsmq. Si fuera necesario intercambiar los mensajes MSMQ nativos, use el adaptador de BizTalk MSMQ.  
  
 Para obtener más información sobre la configuración de adaptadores, vea el recurso siguiente:  
  
-   [Configuración del adaptador de WCF-NetMsmq](../core/configuring-the-wcf-netmsmq-adapter.md)