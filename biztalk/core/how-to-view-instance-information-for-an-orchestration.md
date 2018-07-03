---
title: Cómo ver información de instancia de una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 761f29d6f341410fec544fb0d6fdc032f671775c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983997"
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a>Cómo ver información de instancia para una orquestación
En este tema se describe cómo ver información de instancia para una orquestación mediante la consola de administración de BizTalk Server. Una instancia de servicio es una instancia de una orquestación que BizTalk Server está procesando o ha serializado en el cuadro de mensajes para su seguimiento o procesamiento ulterior.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server. Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-view-instance-information-for-an-orchestration"></a>Para ver información de instancia para una orquestación  
  
1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que desea ver información de instancia.  
  
3. Haga clic en **orquestaciones**, seleccione la orquestación que desea ver información de instancia, haga clic en **vista**y, a continuación, seleccione **información de la instancia**.  
  
    En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias de la orquestación.  
  
    Para refinar la consulta y ver información de instancia diferente para la orquestación, haga clic en el cuadro en **valor** para el campo Buscar y seleccionar el tipo de instancia para ver y, a continuación, haga clic en **Ejecutar consulta**. Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.  
  
## <a name="see-also"></a>Vea también  
 [Administración de orquestaciones](../core/managing-orchestrations.md)   
 [Cómo buscar instancias de servicio de ejecución](../core/how-to-search-for-running-service-instances.md)   
 [Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md)   
 [Cómo buscar mensajes](../core/how-to-search-for-messages.md)   
 [Cómo buscar suscripciones](../core/how-to-search-for-subscriptions.md)