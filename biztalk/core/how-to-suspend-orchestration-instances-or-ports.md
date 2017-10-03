---
title: "Cómo suspender puertos o instancias de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a>Cómo suspender puertos o instancias de orquestación
Puede suspender puertos o instancias de orquestación desde una lista de resultados de consulta de la consola de administración de BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a>Para suspender puertos o instancias de orquestación  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio en ejecución** en el cuadro de lista desplegable.  
  
5.  Realice una de las siguientes operaciones:  
  
    -   Para suspender una única instancia, en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione la **nombre del servicio** filtro y a continuación, en la **valor** columna, especifique el nombre del servicio.  
  
    -   Para suspender las instancias de forma masiva en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione **agrupar resultados por** y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
6.  Haga clic en **Ejecutar consulta**.  
  
7.  En la lista de resultados de la consulta, haga clic en la orquestación activa o el puerto que desea suspender y, a continuación, haga clic en **Suspender instancia** o **suspender instancias**.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de orquestación, puerto y errores de mensaje](../core/investigating-orchestration-port-and-message-failures.md)