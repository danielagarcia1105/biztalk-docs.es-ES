---
title: Limitaciones del adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft
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
ms.openlocfilehash: 1d392178cd49918151f0ad86c73a5fcba712d6b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217084"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a>Limitaciones del adaptador de BizTalk para mySAP Business Suite

## <a name="limitations-list"></a>Lista de limitaciones
Los siguientes se conocen las limitaciones de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:  
  
-   El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el adaptador de Microsoft BizTalk para mySAP Business Suite, la versión anterior del adaptador. Esta versión del adaptador no admite enviar y recibir mensajes con esquemas generados utilizando la versión anterior del adaptador.  
  
-   El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC con tipos de parámetros complejos, incluidos los tipos de tabla (jerárquicos) ITAB II.  
  
-   El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC tener tipos ABAP personalizados.  
  
-   Debido a problemas con el control de tiempo de espera por la biblioteca de cliente subyacente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
-   Si cambia la hora del sistema del equipo que ejecuta el host de BizTalk Server, el tiempo no se actualiza automáticamente en el host de BizTalk Server. Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que utilizan el puerto de recepción de BizTalk Server. Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción, después de haber cambiado la hora del sistema del equipo ejecuta.  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)