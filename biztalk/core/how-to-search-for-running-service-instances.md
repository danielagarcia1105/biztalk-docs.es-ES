---
title: Búsqueda de instancias de servicio en ejecución | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, viewing
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- service instances, running
ms.assetid: fc65bf33-c013-4e6a-b9fd-b4536811e7b4
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8873747b39d6fa178b813d361b72ccf24f44b54a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255204"
---
# <a name="how-to-search-for-running-service-instances"></a>Cómo buscar instancias de servicio en ejecución
Puede usar el **consulta** pestaña en la consola de administración de BizTalk Server para buscar una determinada deshidratada, activa, en el punto de interrupción, programada y volver a intentar la instancia de servicio.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.  
  
### <a name="to-search-for-running-service-instances"></a>Para buscar instancias de servicio en ejecución  
  
1.  Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio en ejecución** en el cuadro de lista desplegable.  
  
5.  En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:  
  
    |Elemento|Description|  
    |----------|-----------------|  
    |**Application Name**|Indica la aplicación de BizTalk Server.|  
    |**Hora de creación**|Busca instancias de servicio en ejecución creadas antes o después de la fecha especificada.|  
    |**Agrupar los resultados por**|Puede agrupar los resultados por aplicación, nombre de host, tipo de operación pendiente, clase de servicio, estado de instancia de servicio o nombre de servicio.|  
    |**Host Name**|Indica el nombre del host de BizTalk.|  
    |**Estado de la instancia**|Puede buscar por instancias activas, instancias deshidratadas, instancias preparadas para ejecutarse e instancias programadas.|  
    |**N.º máximo de coincidencias**|Número de coincidencias que se van a mostrar.|  
    |**Operaciones pendientes**|Puede buscar instancias de servicio en ejecución de finalización o suspensión pendiente.|  
    |**Clase de servicio**|Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.|  
    |**Nombre del servicio**|Permite agrupar o filtrar las instancias de servicio en ejecución por nombre de servicio.|  
    |**Id. de tipo de servicio**|Puede agrupar o filtrar mensajes por Id. de tipo de servicio.|  
  
6.  Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.  
  
7.  Seguir agregando líneas adicionales a la consulta según corresponda, siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la pestaña Consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)