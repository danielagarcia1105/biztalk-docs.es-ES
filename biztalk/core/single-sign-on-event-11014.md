---
title: 'De sesión único: Evento 11014 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e86642a7f62b53d45f20e140131d6a12d0771ec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001141"
---
# <a name="single-sign-on-event-11014"></a>De sesión único: Evento 11014
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                Inicio de sesión único (SSO) empresarial                                                                 |
| Versión del producto |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    Identificador del evento     |                                                                          11014                                                                           |
|  Origen del evento   |                                                                          ENTSSO                                                                          |
|    Componente    |                                                                           N/D                                                                            |
|  Nombre simbólico  |                                                                  SSO_ERROR_ACCESS_CHECK                                                                  |
|  Texto del mensaje   | Error al comprobar el acceso.%r<br /><br /> Usuario del cliente: %1\\%2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Datos adicionales: %4 %r<br /><br /> Código de error: %5 |
  
## <a name="explanation"></a>Explicación  
 Se produjo un error al comprobar el acceso para el cliente y la aplicación enumerados.  
  
## <a name="user-action"></a>Acción del usuario  
 La información adicional debe permitirle solucionar el problema. Para evitar este error en el futuro, también puede reducir el nivel de auditoría.