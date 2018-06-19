---
title: 'Inicio de sesión único: Evento 11047 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e16c2fa899642f20c67e171d0bd8f9536b6add2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278972"
---
# <a name="single-sign-on-event-11047"></a>Inicio de sesión único: Evento 11047
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|Inicio de sesión único (SSO) empresarial|  
|Versión del producto|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|Identificador del evento|11047|  
|Origen del evento|ENTSSO|  
|Componente|N/D|  
|Nombre simbólico|SSO_ERROR_SSOSQL_FAILED|  
|Texto del mensaje|No se pudo crear SSOSQL. Para corregir el problema, reinstale SSO o pruebe 'a utilizar regasm SSOSQL.dll' desde un Visual Studio comando prompt.%r<br /><br /> Código de error: %1|  
  
## <a name="explanation"></a>Explicación  
 Es probable que el problema se deba a un error de instalación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el problema, reinstale SSO o intente "regasm SSOSQL.dll" desde el símbolo del sistema de Visual Studio.%r