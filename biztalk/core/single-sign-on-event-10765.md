---
title: 'De sesión único: Evento 10765 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd49ead3fc30d3b98ea804a98a5882696ea749d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975109"
---
# <a name="single-sign-on-event-10765"></a>De sesión único: Evento 10765
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10765                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |                  ENTSSO_E_NO_CREDENTIALS                   |
|  Texto del mensaje   |       No se establecieron credenciales para la asignación.        |
  
## <a name="explanation"></a>Explicación  
 Se solicitó GetCredentials en una asignación, pero la asignación especificada no tiene credenciales.  
  
## <a name="user-action"></a>Acción del usuario  
 Use la línea de comandos o el complemento MMC para establecer las credenciales de la asignación.