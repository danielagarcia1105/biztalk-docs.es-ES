---
title: Cómo suspender puertos o instancias de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10f6923df37b5cce3a500ed6e02014f09d1c2c0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994933"
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a>Cómo suspender puertos o instancias de orquestación
Puede suspender puertos o instancias de orquestación desde una lista de resultados de consulta de la consola de administración de BizTalk Server.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe ser iniciado sesión como miembro del grupo Operadores de BizTalk Server para llevar a cabo este procedimiento.  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a>Para suspender puertos o instancias de orquestación  
  
1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  
  
3. En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4. En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio en ejecución** en el cuadro de lista desplegable.  
  
5. Realice una de las siguientes operaciones:  
  
   - Para suspender una única instancia, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione el **denombredeservicio</em>*  filtro y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
   - Para suspender las instancias de forma masiva, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione **agrupar resultados por</em>*  y, a continuación, en el **valor** columna, especifique el nombre del servicio.  
  
6. Haga clic en **Ejecutar consulta**.  
  
7. En la lista de resultados de consulta, haga clic en la orquestación activa o el puerto que desea suspender y, a continuación, haga clic en **Suspender instancia** o **suspender instancias**.  
  
## <a name="see-also"></a>Vea también  
 [Investigación de errores de mensaje, orquestación y puerto](../core/investigating-orchestration-port-and-message-failures.md)