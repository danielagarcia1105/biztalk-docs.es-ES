---
title: Deficiencias en el proceso de restauración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 616c4f36-8ed6-4b99-b97a-5635627dfc17
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b7d3ccadd950f5a955430b982c1a6f79a262864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298100"
---
# <a name="gaps-in-the-restore-process"></a>Deficiencias en el proceso de restauración
Al revisar los registros en la tabla Master.dbo.bts_LogShippingHistory, quizá observe huecos en los conjuntos restaurados. Esto puede ocurrir por varios motivos. Sin embargo, se puede restaurar la estabilidad del sistema de destino aunque hayan desaparecido elementos. Un espacio debe ir seguido de una restauración de una copia de seguridad completa para reparar el entorno de destino. Si no está seguido de un espacio restauración de conjunto de copia de seguridad completa, el entorno de destino no es estable y no se puede restaurar en un estado coherente.  
  
> [!NOTE]  
>  Las copias de seguridad completas tan sólo se restauran para crear inicialmente la base de datos y para reparar problemas en la cadena de copias de seguridad del historial de registros. Siempre que un problema no se produce con una restauración, no se restauran conjuntos de copia de seguridad completa, ya no participan en la cadena de copia de seguridad de registros.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)