---
title: 'De sesión único: Evento 11047 | Microsoft Docs'
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
ms.openlocfilehash: 8f1ee4f5eaea1dac2cb2033d4585e2f89807588e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991869"
---
# <a name="single-sign-on-event-11047"></a>De sesión único: Evento 11047
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                Inicio de sesión único (SSO) empresarial                                                                |
| Versión del producto |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    Identificador del evento     |                                                                          11047                                                                          |
|  Origen del evento   |                                                                         ENTSSO                                                                          |
|    Componente    |                                                                           N/D                                                                           |
|  Nombre simbólico  |                                                                 SSO_ERROR_SSOSQL_FAILED                                                                 |
|  Texto del mensaje   | No se pudo crear SSOSQL. Para corregir el problema, reinstale SSO o intente "regasm SSOSQL.dll' desde un prompt.%r Visual<br /><br /> Código de error: %1 |
  
## <a name="explanation"></a>Explicación  
 Es probable que el problema se deba a un error de instalación.  
  
## <a name="user-action"></a>Acción del usuario  
 Para solucionar el problema, reinstale SSO o intente "regasm SSOSQL.dll" desde el símbolo del sistema de Visual Studio.%r