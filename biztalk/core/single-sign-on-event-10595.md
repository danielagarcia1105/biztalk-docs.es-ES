---
title: 'De sesión único: Evento 10595 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1517478c-7217-4e34-a5cb-ff7deea367ed
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0cbc952197971f4e0db0586bc4f1d2d6c37aba44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995229"
---
# <a name="single-sign-on-event-10595"></a>De sesión único: Evento 10595
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                             Inicio de sesión único (SSO) empresarial                                                                                              |
| Versión del producto |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                             |
|    Identificador del evento     |                                                                                                       10595                                                                                                        |
|  Origen del evento   |                                                                                                       ENTSSO                                                                                                       |
|    Componente    |                                                                                                        N/D                                                                                                         |
|  Nombre simbólico  |                                                                                           SSO_WARN_APP_INCOMPLETE_FIELDS                                                                                           |
|  Texto del mensaje   | No se puede habilitar la aplicación porque los campos están incompletos para esta aplicación.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Número de campos definidos: %2 %r<br /><br /> Número de campos creados: %3 |
  
## <a name="explanation"></a>Explicación  
 Al crear una aplicación en el nivel de API, se especificó el número de campos (por ejemplo, Id. de usuario y contraseña) que definiría la aplicación. También se debe crear cada campo definido. Este mensaje de advertencia enumera el nombre, el número de campos definidos y el número de campos creados de la aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Determine los campos que se definieron pero no se crearon y, a continuación, vuelva atrás y créelos.