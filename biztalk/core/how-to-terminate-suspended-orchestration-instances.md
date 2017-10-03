---
title: "Cómo finalizar instancias de orquestación suspendidas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc0160be5aeeef43b9595953893b4ea1af82c62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>Cómo finalizar instancias de orquestación suspendidas
Puede finalizar cualquier puerto o instancia de orquestación suspendida desde el panel Resultados de la consulta o el panel de previsualización de la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Cada instancia de un puerto de envío de entrega ordenada puede tener varios mensajes asociados a él. Para evitar pérdida de datos o finalización accidental, compruebe que ha revisado todas las asociaciones de este tipo antes de finalizar la instancia.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>Para finalizar instancias de orquestación suspendidas  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio suspendidas** en el cuadro de lista desplegable.  
  
5.  Realice una de las siguientes operaciones:  
  
    -   Para finalizar una única instancia, en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione la **nombre del servicio** filtro y, a continuación, en la **valor** columna, especifique el nombre del servicio.  
  
    -   Para finalizar instancias de forma masiva en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione **agrupar resultados por** y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
6.  Haga clic en **Ejecutar consulta**.  
  
7.  En la lista de resultados de la consulta, haga clic en la instancia de orquestación o un grupo de instancias que desea finalizar y, a continuación, haga clic en **finalizar instancia** o **finalizar instancias**.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md)