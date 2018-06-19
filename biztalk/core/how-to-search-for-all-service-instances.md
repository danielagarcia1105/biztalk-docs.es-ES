---
title: Búsqueda de todas las instancias de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service instances, Query tab [Administration Console]
- Query tab [Administration Console], service instances
- Query tab [Administration Console], searching
- service instances, searching
- instances, services
ms.assetid: 48cb885c-aaf1-44e8-9810-2e70cf63db81
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e96622fad23c28c0d4147f64a11cc540e88e7f97
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22255124"
---
# <a name="how-to-search-for-all-service-instances"></a>Cómo buscar todas las instancias de servicio
Puede usar el **consulta** pestaña en la consola de administración de BizTalk Server para buscar todas las instancias de servicio. No se podrá dar de baja un tipo de servicio específico cuando se trate de instancias en ejecución o suspendidas. Por ejemplo, antes de poder dar de baja un tipo de servicio específico, puede buscar todas las instancias de servicio para asegurarse de que no haya ninguna en ejecución o suspendida.  
  
> [!NOTE]
>  Al agrupar y filtrar por URI, los resultados sólo mostrarán los puertos de envío y de recepción. No se podrá agrupar ni filtrar por URI en el caso de las orquestaciones, ya que éstas no se incluyen en los resultados.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.  
  
### <a name="to-search-for-all-service-instances"></a>Para buscar todas las instancias de servicio  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **todas las instancias de servicio en curso** en el cuadro de lista desplegable.  
  
5.  En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Application Name**|Indica la aplicación de BizTalk Server.|  
    |**Hora de creación**|Busca todas las instancias de servicio creadas antes o después de la fecha especificada.|  
    |**Agrupar los resultados por**|Puede agrupar los resultados por aplicación, nombre de host, clase de servicio, estado de instancia de servicio o nombre de servicio.|  
    |**Host Name**|Indica el nombre del host de BizTalk.|  
    |**Estado de la instancia**|Puede buscar todas las instancias en ejecución, instancias suspendidas, instancias activas, instancias deshidratadas, instancias preparadas para ejecutarse, instancias programadas, instancias suspendidas no reanudables o instancias suspendidas reanudables.|  
    |**N.º máximo de coincidencias**|Número de coincidencias que se van a mostrar (requerido). Por lo general, se establece como 50 (valor predeterminado).<br /><br /> Al incluir Agrupar resultados por, se muestra el número de grupos, no el número total de registros.|  
    |**Clase de servicio**|Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.|  
    |**Id. de instancia de servicio**|Permite agrupar o filtrar las instancias de servicio por Id. de instancia de servicio.|  
    |**Nombre del servicio**|Permite agrupar o filtrar las instancias de servicio por nombre de servicio.|  
    |**Id. de tipo de servicio**|Permite agrupar o filtrar instancias de servicio por Id. de tipo de servicio.|  
  
6.  Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.  
  
7.  Seguir agregando líneas adicionales a la consulta según corresponda, siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la pestaña Consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)