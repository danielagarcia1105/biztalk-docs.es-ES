---
title: 'De sesión único: Evento 10804 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d98bef-fdc3-4627-bb5b-663fa502b965
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a262448f4d07a01f726f111ca5ddd01901e9e7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017016"
---
# <a name="single-sign-on-event-10804"></a>De sesión único: Evento 10804
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10804                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |                ENTSSO_E_INCORRECT_COMPUTER                 |
|  Texto del mensaje   |     El adaptador no está configurado para este equipo.      |
  
## <a name="explanation"></a>Explicación  
 Cada adoptador se configura para ejecutarse en un equipo específico, que se identifica mediante su nombre largo. El nombre es incorrecto o se está intentando ejecutar el adaptador en otro equipo.  
  
## <a name="user-action"></a>Acción del usuario  
 Consulte la configuración del adaptador para determinar el nombre correcto del equipo correspondiente.