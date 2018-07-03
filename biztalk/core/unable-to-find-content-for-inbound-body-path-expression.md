---
title: No se encuentra el contenido de la expresión de ruta de acceso del cuerpo de entrada | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed294662-a94e-4fbb-b125-878a27107eab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9de18c9d3fa7ccf89a33eb6b09e6c11381a73a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972029"
---
# <a name="unable-to-find-content-for-inbound-body-path-expression"></a>No se encuentra el contenido para la expresión de ruta del cuerpo de entrada
## <a name="details"></a>Detalles  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |      No se encuentra el contenido de la expresión de ruta de acceso del cuerpo de entrada "{0}" en el mensaje      |

## <a name="explanation"></a>Explicación  
 El contenido extraído del mensaje de entrada mediante la ejecución de la expresión de ruta del cuerpo no contiene ningún dato.  

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
