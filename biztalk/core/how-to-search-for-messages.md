---
title: Búsqueda de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- messages, searching
- Query tab [Administration Console], searching
- Query tab [Administration Console], messages
ms.assetid: c751d23f-913a-4325-81da-a36d61c07e8b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5443cc021bd5f97621f44d295432c99834bdaed
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-messages"></a>Cómo buscar mensajes
Puede usar el **consulta** pestaña en la consola de administración de BizTalk Server para buscar una clase específica de mensajes.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.  
  
### <a name="to-search-for-messages"></a>Para buscar mensajes  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **mensajes** en el cuadro de lista desplegable.  
  
5.  En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:  
  
    |Elemento|Description|  
    |----------|-----------------|  
    |**Hora de creación**|Permite buscar mensajes creados antes o después de la fecha especificada.|  
    |**Adaptador con error**|Puede agrupar o filtrar mensajes por tipo de adaptador: archivo, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP o Windows SharePoint Services.|  
    |**Código de error**|Permite agrupar o filtrar mensajes por código de error.|  
    |**Descripción del error**|Permite agrupar o filtrar mensajes por descripción del error.|  
    |**Host Name**|Permite agrupar o filtrar mensajes por nombre de host.|  
    |**Estado de la instancia**|El estado de la instancia de servicio que hace referencia al mensaje. Puede buscar todos los tipos siguientes de instancias: todas las instancias en ejecución, todas las instancias suspendidas, instancias activas, instancias deshidratadas, instancias preparadas para ejecutarse, instancias programadas, suspendidos pero no reanudables instancias, o suspendidos y reanudables instancias.|  
    |**N.º máximo de coincidencias**|Número de coincidencias que se van a mostrar.|  
    |**Id. de mensaje**|Permite agrupar o filtrar mensajes por Id. de mensaje.|  
    |**Estado del mensaje**|Puede buscar mensajes con el siguiente estado: consumido, en proceso, suspendido, suspendido pero no reanudable, suspendido y reanudable, en cola, en cola pero en espera de procesarse, en cola pero programado para entregarse más tarde y en cola pero en espera de reintento.|  
    |**Tipo de mensaje**|Permite agrupar o filtrar mensajes por tipo de mensaje.|  
    |**Clase de servicio**|Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.|  
    |**Id. de instancia de servicio**|Puede agrupar o filtrar mensajes por Id. de instancia de servicio.|  
    |**Nombre del servicio**|Permite agrupar o filtrar mensajes por nombre de servicio.|  
    |**Id. de tipo de servicio**|Puede agrupar o filtrar mensajes por Id. de tipo de servicio.|  
    |**URI**|Permite agrupar o filtrar mensajes por URI.|  
  
6.  Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.  
  
7.  Seguir agregando líneas adicionales a la consulta según corresponda, siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la pestaña Consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)