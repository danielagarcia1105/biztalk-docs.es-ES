---
title: 'De sesión único: Evento 11061 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52fb18e2-4482-4cdb-b8ed-d579a95acd7c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1733e444ecdfdaf54b20beb2de6894ade3466f4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011333"
---
# <a name="single-sign-on-event-11061"></a>De sesión único: Evento 11061
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                     Inicio de sesión único (SSO) empresarial                                                                                                                     |
| Versión del producto |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    Identificador del evento     |                                                                                                                               11061                                                                                                                               |
|  Origen del evento   |                                                                                                                              ENTSSO                                                                                                                               |
|    Componente    |                                                                                                                                N/D                                                                                                                                |
|  Nombre simbólico  |                                                                                                                   SSO_WARN_BAD_PASSWORD_FILTER                                                                                                                    |
|  Texto del mensaje   | Cadena de filtro de contraseña no válida. No se usará filtro de contraseña.%r<br /><br /> Nombre de la aplicación: %1 %r<br /><br /> Cadena de filtro de contraseña: %2 %r<br /><br /> Número de Tokens procesados: %3 %r<br /><br /> Datos adicionales: %4 %r<br /><br /> Código de error: %5 |
  
## <a name="explanation"></a>Explicación  
 Se creó manualmente un filtro de contraseña no válido. En algún momento de este proceso se generó un error (consulte la cadena de filtro de contraseña en el texto de la advertencia para conocer la ubicación del error).  
  
## <a name="user-action"></a>Acción del usuario  
 Para crear el filtro de contraseña mediante el Asistente para crear un filtro de contraseña, consulte [cómo usar filtros de contraseña](../core/how-to-use-password-filters.md).