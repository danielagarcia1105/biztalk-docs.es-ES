---
title: Cómo reanudar instancias de orquestación suspendidas | Documentos de Microsoft
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6696547ce3e918dc8d84b7cfcb4f24e31c8b70a0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-resume-suspended-orchestration-instances"></a>Cómo reanudar instancias de orquestación suspendidas
Si ha suspendido instancias de orquestación enumeradas como "suspendidas reanudables", puede intentar reanudarlas desde el panel de previsualización o de resultados de consulta. La reanudación de la instancia de orquestación sólo se realizará correctamente si el problema subyacente que ocasionó su suspensión se ha resuelto.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-resume-suspended-orchestration-instances"></a>Para reanudar instancias de orquestación suspendidas  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio suspendidas** en el cuadro de lista desplegable.  
  
5.  Realice una de las siguientes operaciones:  
  
    -   Para reanudar una única instancia, en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione la **nombre del servicio** filtro y a continuación, en la **valor** columna, especifique el nombre del servicio.  
  
    -   Para reanudar las instancias de forma masiva en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione **agrupar resultados por** y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
6.  Haga clic en **Ejecutar consulta**.  
  
7.  En la lista de resultados de la consulta, haga clic en la instancia de orquestación que desea reanudar y, a continuación, haga clic en **reanudar instancia** o **Reanudar instancias**. Esto permite seleccionar las instancias que desea reanudar.  
  
     [Estados de la instancia de servicio](../core/service-instance-states.md) proporciona más información sobre el en estado suspendido.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de errores de mensaje, orquestación y puerto](../core/investigating-orchestration-port-and-message-failures.md)
