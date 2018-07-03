---
title: 'De sesión único: Evento 10615 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b99f901ba60749386d055ce771beed225e4a18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008469"
---
# <a name="single-sign-on-event-10615"></a>De sesión único: Evento 10615
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                                                                                                Inicio de sesión único (SSO) empresarial                                                                                                                |
| Versión del producto |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    Identificador del evento     |                                                                                                                          10615                                                                                                                          |
|  Origen del evento   |                                                                                                                         ENTSSO                                                                                                                          |
|    Componente    |                                                                                                                           N/D                                                                                                                           |
|  Nombre simbólico  |                                                                                                            SSO_WARN_NO_UPDATE_TICKET_TIMEOUT                                                                                                            |
|  Texto del mensaje   | El usuario del cliente debe ser miembro de la cuenta de administradores de SSO para cambiar el tiempo de espera de vale de una aplicación.%r<br /><br /> Usuario cliente: %1 %r<br /><br /> Administradores de SSO: %2 %r<br /><br /> Nombre de la aplicación: %3 %r<br /><br /> Código de error: %4 |
  
## <a name="explanation"></a>Explicación  
 El usuario del cliente debe ser miembro de la cuenta de administradores de SSO para cambiar el tiempo de espera de vale de una aplicación.  
  
## <a name="user-action"></a>Acción del usuario  
 Solicite ayuda al administrador del sistema para encontrar a un miembro de la cuenta de administradores de SSO que realice este cambio.