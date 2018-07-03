---
title: No se puede encontrar ninguna coincidencia para la expresión de ruta de acceso del cuerpo de entrada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0382348-96c4-414c-9dda-a390d491dee8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69ae115eef4440490fd4fc5ed4f40c5600b6cdb2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016977"
---
# <a name="unable-to-find-match-for-inbound-body-path-expression"></a>No se puede encontrar ninguna coincidencia para la expresión de ruta del cuerpo de entrada
## <a name="details"></a>Detalles  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |       No se puede encontrar ninguna coincidencia para la expresión de ruta de acceso del cuerpo de entrada "{0}" en el mensaje       |

## <a name="explanation"></a>Explicación  
 La expresión de ruta del cuerpo del mensaje entrante no devolvió ninguna coincidencia.  

## <a name="user-action"></a>Acción del usuario  
 Asegúrese de que la expresión de ruta de cuerpo sea correcta y que el mensaje entrante tenga los datos correctos.  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.  

2. En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.  

3. Busque la aplicación y, a continuación, busque su transporte.  

4. Haga clic con el botón secundario en el nombre del transporte.  

5. Haga clic en **Propiedades**.  

6. En el puerto **tipo** lista, seleccione el puerto correcto.  

7. Haga clic en **configurar**.  

8. En WCF **[**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **mensajes** ficha.  

9. En el **cuerpo del mensaje entrante de BizTalk** sección, compruebe la información de **expresión de ruta de cuerpo**.
