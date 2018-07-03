---
title: Cómo finalizar instancias de orquestación suspendidas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37de5e1153e9d361b76900ca206351e8b9549dc3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991973"
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>Cómo finalizar instancias de orquestación suspendidas
Puede finalizar cualquier puerto o instancia de orquestación suspendida desde el panel Resultados de la consulta o el panel de previsualización de la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Cada instancia de una entrega ordenada de un puerto de envío puede tener varios mensajes asociados con él. Para evitar pérdida de datos o finalización accidental, compruebe que ha revisado todas las asociaciones de este tipo antes de finalizar la instancia.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo Operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>Para finalizar instancias de orquestación suspendidas  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.  
  
3. En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4. En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio suspendidas** desde el cuadro de lista desplegable.  
  
5. Realice una de las siguientes operaciones:  
  
   - Para finalizar una única instancia, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione el **denombredeservicio</em>*  filtro y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
   - Para finalizar las instancias de forma masiva, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione **agrupar resultados por</em>*  y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
6. Haga clic en **Ejecutar consulta**.  
  
7. En la lista de resultados de consulta, haga clic en la instancia de orquestación o un grupo de instancias que desea finalizar y, a continuación, haga clic en **finalizar instancia** o **finalizar instancias**.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de errores de mensaje, orquestación y puerto](../core/investigating-orchestration-port-and-message-failures.md)