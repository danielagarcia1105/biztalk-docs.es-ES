---
title: "Cómo suspender, reanudar y finalizar instancias de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], resuming
- orchestrations, terminating
- managing [orchestrations], suspending
- orchestrations, resuming
- orchestrations, suspending
- managing [orchestrations], terminating
ms.assetid: 7b373dad-57d5-4696-9b29-a6c351d44fa8
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9528ac0e810a3d4e203733ab1cc5b041d3d61d31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a>Cómo suspender, reanudar y finalizar instancias de orquestación
En este tema se describe cómo suspender, reanudar y finalizar una o varias instancias de servicio en ejecución de una orquestación mediante la consola de administración de BizTalk Server. Una instancia de servicio es una instancia de una orquestación que BizTalk Server es un procesamiento o que se ha serializado en el cuadro de mensajes de seguimiento o procesamiento ulterior.  
  
 Los efectos de estas tres operaciones se describen a continuación:  
  
-   **Suspender.** Esta opción detiene la instancia de servicio. Los mensajes en curso se ejecutan hasta que finalizan. Los mensajes se seguirán enrutando a las instancias de servicio, pero no se procesarán.  
  
-   **Reanudar.** Esta opción reanuda el procesamiento de las instancias suspendidas.  
  
> [!NOTE]
>  No puede reanudar una instancia desde un estado de punto de interrupción. La reanudación de una instancia de este tipo puede mostrar el estado de "Pendiente" pero, finalmente, se producirá un error en la instancia.  
  
-   **Finalizar.** Esta opción finaliza el procesamiento de todos los mensajes. La instancia de servicio se elimina de las bases de datos de BizTalk Server. También se eliminan los mensajes que esté procesando la instancia de servicio, excepto aquellos a los que haga referencia una instancia de servicio que no se esté finalizando.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar el procedimiento detallado en este tema, debe haber iniciado sesión como miembro del grupo de operadores o de administradores de BizTalk Server. Para obtener más información sobre permisos, consulte [permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a>Para ver iniciar, detener o finalizar instancias de orquestación  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  Seleccione el grupo de BizTalk para mostrar la página Concentrador de grupo.  
  
3.  En **trabajo en curso**, haga clic en **instancias en ejecución**.  
  
     En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias de la orquestación.  
  
4.  Para refinar la consulta y ver distintas instancias de la orquestación, haga clic en el cuadro en **valor** para el **buscar** , a continuación, seleccione el tipo de instancia desea ver y, a continuación, haga clic en **Ejecutar consulta** . Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.  
  
5.  Haga clic en la instancia que desee y haga clic en **Suspend**, **reanudar**, o **Terminate**. Esta funcionalidad permite seleccionar las instancias que desea reanudar.  
  
    > [!NOTE]
    >  Para realizar la operación en varias instancias, mantenga presionada la tecla CTRL y haga clic en las instancias que desee. A continuación, haga clic en una instancia y haga clic en **Suspend**, **reanudar**, o **Terminate**.  
  
     [Estados de la instancia de servicio](../core/service-instance-states.md) proporciona más información sobre el estado suspendido.  
  
## <a name="see-also"></a>Vea también  
 [Administrar orquestaciones](../core/managing-orchestrations.md)   
 [Búsqueda de instancias de servicio en ejecución](../core/how-to-search-for-running-service-instances.md)   
 [Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md)