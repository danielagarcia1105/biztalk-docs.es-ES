---
title: 'De sesión único: Evento 10564 | Microsoft Docs'
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
ms.openlocfilehash: 8be4ea87757a1fa0cb5d8ebd2e344ce521dbf740
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997149"
---
# <a name="single-sign-on-event-10564"></a>De sesión único: Evento 10564
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10564                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |           SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT           |
|  Texto del mensaje   |     Formato incorrecto de archivo de copia de seguridad.      |
  
## <a name="explanation"></a>Explicación  
 Formato incorrecto de archivo de copia de seguridad.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe si tiene el archivo y la ubicación correctos. Además, debe confirmar que no existen otros archivos en esa carpeta con la extensión .BAK, dado que el sistema ENTSSO puede confundirlos con el archivo de copia de seguridad real.