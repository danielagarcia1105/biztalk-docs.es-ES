---
title: 'De sesión único: Evento 10562 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 924d03c3-9cc3-438c-93d8-b4346cfe0c36
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a369f4bf1793660e1fada5252c30e825e39f3ada
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987995"
---
# <a name="single-sign-on-event-10562"></a>De sesión único: Evento 10562
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10562                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |                SSO_INFO_REENCRYPT_STARTING                 |
|  Texto del mensaje   |         El recifrado de la base de datos de SSO está en curso.         |
  
## <a name="explanation"></a>Explicación  
 Este mensaje es solo informativo. Se cambió el secreto y el sistema SSO está comenzando a cifrar nuevamente la base de datos con el secreto nuevo.  
  
## <a name="user-action"></a>Acción del usuario  
 No se requiere ninguna acción del usuario.