---
title: Archivos de copia de seguridad dañados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5947b527dea1206255daf52f128569fd7a4f659c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987917"
---
# <a name="corrupt-backup-files"></a>Archivos de copia de seguridad dañados
Una copia de seguridad puede quedar dañado, dañado o faltan. Si esto ocurre, no puede restaurarse al menos un archivo. Busca el siguiente conjunto de copia de seguridad completa válido en el trabajo de restauración en el sistema que ha había sufrido el error. En la mayoría de los casos será necesario forzar una copia de seguridad completa del sistema de origen. Si no existe tal conjunto, se produce un error en el trabajo de restauración y cada ejecución posterior también genera un error hasta que llegue un conjunto de copia de seguridad completa válido. Si existe un conjunto, sirve para reparar el entorno.  
  
> [!NOTE]
>  Debido a la manera en que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] escribe los datos de copia de seguridad en un archivo, es posible que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] informará correctamente incluso si la copia de seguridad dado error durante la escritura de los datos real. Este escenario se produce principalmente cuando el disco que se escriben en no es local para el equipo y un error de red o se produce la interrupción. Como medida de precaución general, si se produce un error de red mientras se ejecuta el trabajo de copia de seguridad, fuerce una copia de seguridad completa después de resolver el problema de conectividad de red.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)