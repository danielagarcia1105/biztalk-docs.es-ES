---
title: 'Inicio de sesión único: Evento 10564 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523c97a-608e-4bf4-8747-cfa0cce10acf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7268b877a59fcd4e993a2c9009d48d73e5db9ac8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270300"
---
# <a name="single-sign-on-event-10564"></a>Inicio de sesión único: Evento 10564
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|10564|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT|  
|Texto del mensaje|Formato incorrecto de archivo de copia de seguridad.|  
  
## <a name="explanation"></a>Explicación  
 Formato incorrecto de archivo de copia de seguridad.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si tiene el archivo y la ubicación correctos. Además, debe confirmar que no existen otros archivos en esa carpeta con la extensión .BAK, dado que el sistema ENTSSO puede confundirlos con el archivo de copia de seguridad real.