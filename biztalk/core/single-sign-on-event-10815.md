---
title: 'De sesión único: Evento 10815 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf4ebb92-f0fa-499c-9bda-0cde726ec98e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eed7b5a2ff7efe8944cd1c2e48117b3e43f84718
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024418"
---
# <a name="single-sign-on-event-10815"></a>De sesión único: Evento 10815
## <a name="details"></a>Detalles  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  Nombre del producto   |                 Inicio de sesión único (SSO) empresarial                  |
| Versión del producto | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    Identificador del evento     |                           10815                            |
|  Origen del evento   |                           ENTSSO                           |
|    Componente    |                            N/D                             |
|  Nombre simbólico  |                   ENTSSO_E_WRONG_SECRET                    |
|  Texto del mensaje   |                  Secreto principal incorrecto.                  |
  
## <a name="explanation"></a>Explicación  
 Durante el intento de restaurar el secreto principal, es posible que haya especificado el archivo incorrecto.  
  
## <a name="user-action"></a>Acción del usuario  
 Vuelva a comprobar el archivo y asegúrese de que sea el adecuado.