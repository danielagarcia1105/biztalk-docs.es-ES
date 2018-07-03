---
title: Cómo reanudar instancias de orquestación suspendidas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, resuming [HAT]
- HAT, resuming orchestrations
- HAT, resuming pipelines
- orchestrations, resuming
- resuming, pipelines
- resuming, orchestrations
- HAT, debug mode
ms.assetid: da133183-68d9-48d1-9601-8f6d4d5b8898
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f3243173f454d560515d1c3cbb9bef749fc17d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991173"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a>Cómo reanudar instancias de orquestación suspendidas
Si ha suspendido instancias de orquestación enumeradas como "suspendidas reanudables", puede intentar reanudarlas desde el panel de previsualización o de resultados de consulta. La reanudación de la instancia de orquestación sólo se realizará correctamente si el problema subyacente que ocasionó su suspensión se ha resuelto.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo Operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-resume-suspended-orchestration-instances"></a>Para reanudar instancias de orquestación suspendidas  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  
  
3. En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4. En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio suspendidas** desde el cuadro de lista desplegable.  
  
5. Realice una de las siguientes operaciones:  
  
   - Para reanudar una única instancia, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione el **denombredeservicio</em>*  filtro y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
   - Para reanudar las instancias de forma masiva, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione **agrupar resultados por</em>*  y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
6. Haga clic en **Ejecutar consulta**.  
  
7. En la lista de resultados de consulta, haga clic en la instancia de orquestación que desea reanudar y, a continuación, haga clic en **reanudar instancia** o **Reanudar instancias**. Esto permite seleccionar las instancias que desea reanudar.  
  
    [Estados de instancia de servicio](../core/service-instance-states.md) proporciona más información sobre el en estado suspendido.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de errores de mensaje, orquestación y puerto](../core/investigating-orchestration-port-and-message-failures.md)
