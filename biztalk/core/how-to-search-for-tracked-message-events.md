---
title: "Búsqueda de eventos de mensajes controlados | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d4c573b864d16362c1b12b1e293e85f139cad4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-tracked-message-events"></a>Búsqueda de eventos de mensaje de seguimiento
Puede usar el **nueva consulta** pestaña en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para buscar eventos de mensajes controlados.  Desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se puede habilitar el seguimiento del cuerpo y las propiedades de mensajes. En el panel Resultados de la consulta se puede ver información acerca del evento de mensaje, incluida la información de esquema, el tipo de evento, el identificador de instancia de servicio y todas las propiedades promocionadas para el mensaje generado.  
  
> [!NOTE]
>  Para ver el cuerpo del mensaje, puede invocar la **detalles del mensaje** menú contextual y vaya a la pestaña "Partes del mensaje", o guardar el mensaje desde la lista de resultados ver invocando **guardar en archivo** desde el menú contextual.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado la sesión como miembro del grupo Operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-search-for-tracked-message-items"></a>Para buscar elementos de mensaje supervisados  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  
  
2.  En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  
  
3.  En el panel de detalles, haga clic en el **nueva consulta** ficha.  
  
4.  En el **expresión de consulta** grupo, en la **valor** columna, seleccione **realiza el seguimiento de eventos de mensaje** en el cuadro de lista desplegable.  
  
5.  En el **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione una o varias de las siguientes acciones:  
  
    |Elemento|Description|  
    |----------|-----------------|  
    |**Hora de creación**|Hora de creación del mensaje.|  
    |**Tipo de evento**|El tipo de evento que se supervisa.|  
    |**N.º máximo de coincidencias**|Número de coincidencias que se van a mostrar.|  
    |**Entidad**|La organización que envió el mensaje.|  
    |**Puerto**|El puerto usado para procesar el mensaje.|  
    |**Nombre del esquema**|Nombre del esquema que usa el mensaje.|  
    |**Id. de instancia de servicio**|El identificador de instancia de servicio que se usa para el mensaje.|  
    |**URI**|El URI que se usa para el mensaje.|  
    |**\<Seleccione un nombre de esquema para las propiedades controladas >**|Si selecciona un esquema, las propiedades promocionadas de ese esquema se podrán usar en la consulta.|  
  
6.  Completar la **valor** columna según la selección que haya realizado en la **nombre de campo** columna.  
  
7.  Seguir agregando líneas adicionales a la consulta según corresponda siguiendo el **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  
  
## <a name="see-also"></a>Vea también  
 [Uso de la pestaña de consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)