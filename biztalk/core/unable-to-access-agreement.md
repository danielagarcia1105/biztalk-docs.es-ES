---
title: No se puede obtener acceso al acuerdo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72890ee9-54c9-48ed-8c6e-8b329d79c68b
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9c8d8126a7b38d95adfce1e813dd2a86ccde24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024538"
---
# <a name="unable-to-access-agreement"></a>No se puede obtener acceso al acuerdo
## <a name="details"></a>Detalles  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                              UnableToLocateAS2PartyError                               |
|  Texto del mensaje   |            No se puede obtener acceso al acuerdo. AS2From: {0} AS2To: {1}. Error: {2}             |

## <a name="explanation"></a>Explicación  
 Este error indica que BizTalk Server no pudo encontrar una entidad para el calificador y valor dados.  

## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, cree un alias de entidad para el calificador dado:  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y haga clic en **partes**.  

3. Haga clic con el botón secundario en la entidad correcta.  

4. Haga clic en **Propiedades**.  

5. En el [*nombre de la entidad*] **las propiedades de entidad** diálogo cuadro, escriba **valor From de EDIINT-AS2** en el **nombre** columna.  

6. Escriba el nombre de entidad en el **valor** columna.  

7. Haga clic en **Aceptar**.
