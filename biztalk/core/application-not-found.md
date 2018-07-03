---
title: No se encontró la aplicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37680b2-b38a-40f3-bb27-7b7281299ec3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98499420c773328d647a9c7fa1c80e3ab09ba1b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003461"
---
# <a name="application-not-found"></a>No se ha encontrado la aplicación
## <a name="details"></a>Detalles  

|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| Versión del producto |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    Identificador del evento     |                                                    0                                                    |
|  Origen del evento   |                                                    0                                                    |
|    Componente    |                                                    0                                                    |
|  Nombre simbólico  |                                                    0                                                    |
|  Texto del mensaje   | Aplicación "{0}" no se encuentra. Compruebe que la aplicación existe en la base de datos de configuración de BizTalk predeterminado |

## <a name="explanation"></a>Explicación  
 Este error indica que BizTalk usa una aplicación que no existe en las bases de datos de BizTalk.  

## <a name="user-action"></a>Acción del usuario  
 Use el procedimiento siguiente para configurar una aplicación válida.  

#### <a name="to-configure-a-valid-application"></a>Para configurar una aplicación válida  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Asegúrese de que la aplicación exista allí. Si no existe, seleccione una aplicación válida diferente.
