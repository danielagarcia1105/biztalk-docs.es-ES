---
title: Distributed problemas del sistema | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 287b0adb-d5f9-4e47-80f8-0ba5d90c7864
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24abe471a66e8bc0724ad731388c5a0e7c07b573
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297756"
---
# <a name="distributed-system-problems"></a>Problemas de sistemas distribuidos
En un sistema de destino distribuida, los trabajos de restauración no son conscientes de los errores o problemas en los demás equipos. Por ejemplo, suponga que el equipo A restaurar la base de datos de administración de BizTalk y la base de datos de seguimiento de BizTalk y el equipo B está restaurando la base de datos de BizTalk MessageBox. Ambos equipos restauración correctamente los conjuntos de copia de seguridad 1 y 25. Conjunto de 26, sin embargo, tiene un archivo de copia de seguridad de registro dañado de la base de datos de BizTalk MessageBox. El equipo A sus bases de datos restaura correctamente pero se produce un error en el equipo B restaurar el archivo dañado.  
  
 En este caso, forzar una copia de seguridad completa en el sistema de origen. Siguiendo con el ejemplo anterior, se supone que se ha diagnosticado el problema y se creó una copia de seguridad completa para el conjunto de 35. El equipo A, a continuación, restauraciones conjuntos 26 a 34, porque no es consciente del problema en el equipo B. equipo B se producirá un error hasta que ve 35 de conjunto de copia de seguridad completa y copia de seguridad de registros subsiguientes conjunto 36 (Recuerde que debe siempre ser una copia de seguridad de registros completa subsiguientes para un conjunto sea restauración d). Cuando llegan los conjuntos de 35 y 36 en el equipo B, reparará utilizando 35. Una vez completada la reparación, equipo A y B se sincronizarán.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)