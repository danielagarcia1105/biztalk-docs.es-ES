---
title: "Archivos de copia de seguridad esté dañado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda5acae756fd2c4d0afc0263bc723af3ba77e15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="corrupt-backup-files"></a>Archivos de copia de seguridad dañados
Un archivo de copia de seguridad quede dañado, está dañado o falta. Si esto ocurre, no se puede restaurar al menos un archivo. El trabajo de restauración en el sistema que ha sufrido el error, busca el siguiente conjunto de copia de seguridad completa válido. En la mayoría de los casos será necesario forzar una copia de seguridad completa del sistema de origen. Si no existe ningún conjunto de este tipo, se produce un error en el trabajo de restauración y cada ejecución subsiguientes también genera un error hasta que se reciba un conjunto de copia de seguridad completa válido. Si existe un conjunto, se usa para reparar el entorno.  
  
> [!NOTE]  
>  Debido a la forma en que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] escribe datos de copia de seguridad en un archivo, es posible que [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] va a notificar la finalización correcta incluso si la copia de seguridad produce errores durante la escritura real de los datos. Este escenario se produce principalmente cuando el disco que se escriben en no es local para el equipo y un error de red o se produce la interrupción. Como medida de precaución general, si se produce un error de red mientras se ejecuta el trabajo de copia de seguridad, forzar una copia de seguridad completa después de que se resuelva el problema de conectividad de red.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de trasvase de registros](../technical-guides/troubleshooting-log-shipping.md)