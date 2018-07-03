---
title: Limitaciones del adaptador de BizTalk para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f289d1f70005e8b4caa0e7c739522cc5590bca58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973718"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a>Limitaciones del adaptador de BizTalk para mySAP Business Suite

## <a name="limitations-list"></a>Lista de limitaciones
Lo siguiente es limitaciones conocida de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:  
  
- El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el adaptador de Microsoft BizTalk para mySAP Business Suite, la versión anterior del adaptador. No admite esta versión del adaptador de envío y recepción de mensajes con los esquemas generados con la versión anterior del adaptador.  
  
- El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC con tipos de parámetros complejos, incluidos los tipos de tabla (jerárquica) ITAB II.  
  
- El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC de tipos personalizados de ABAP.  
  
- Debido a problemas con el control de tiempo de espera por la biblioteca de cliente subyacente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
- Si cambia la hora del sistema del equipo que ejecuta el host de BizTalk Server, el tiempo no se actualiza automáticamente en el host de BizTalk Server. Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que usan el puerto de recepción de BizTalk Server. Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción después de haber cambiado la hora del sistema del equipo ejecuta.  
  
## <a name="see-also"></a>Vea también  
 [Definición del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)