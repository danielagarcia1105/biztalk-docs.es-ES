---
title: No se pudo obtener la base de datos o los nombres de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0590f43b-0aec-491f-bca5-c50ab12552a5
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e2d346c2771328ac67df3e2aa7454288779cb9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990269"
---
# <a name="could-not-get-the-database-or-the-server-names"></a>No se han podido obtener los nombres de base de datos o servidor.
## <a name="details"></a>Detalles  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                     No se han podido obtener los nombres de base de datos o servidor.                     |

## <a name="explanation"></a>Explicación  
 Este error indica que BizTalk no pudo leer el nombre de BizTalkMgmtDb ni el nombre del servidor desde el Registro. Una posible razón para este error es que el grupo de BizTalk no esté configurado.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, configure el Grupo de BizTalk:  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En la Raíz de la consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  

3. Haga clic en **grupo de BizTalk**.  

4. Haga clic en **Propiedades**.  

5. En el panel izquierdo, haga clic en **General**.  

6. Compruebe el **Server** nombre y **base de datos** nombre son correctos.
