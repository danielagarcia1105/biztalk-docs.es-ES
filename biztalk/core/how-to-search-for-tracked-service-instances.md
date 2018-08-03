---
title: Búsqueda de instancias de servicio controladas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3770e871e7be022ff7f4597b8d3eb4d8f307cc37
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966517"
---
# <a name="how-to-search-for-tracked-service-instances"></a>Búsqueda de instancias de servicio supervisadas
Puede usar el **consulta** pestaña en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración para buscar todas las instancias de servicio controladas. Para localizar instancias de servicio, puede buscar el nombre y la versión del ensamblado, el tiempo de inicio y fin de vigencia, el nombre o identificador de instancia de la clase de servicio, el nombre de host, el código de error y el estado de la instancia de servicio.  

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado la sesión como miembro del grupo Operadores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

### <a name="to-search-for-tracked-service-instances"></a>Procedimiento para buscar instancias de servicio controladas  

1. Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  

2. En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  

3. En el panel de detalles, haga clic en el **nueva consulta** ficha.  

4. En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio controladas** desde el cuadro de lista desplegable.  

5. En el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\***), seleccione una o varias de las siguientes acciones:  


   |          Elemento           |                     Descripción                      |
   |-------------------------|------------------------------------------------------|
   |    **Nombre del ensamblado**    |    Nombre del ensamblado para la instancia de servicio.    |
   |  **Versión del ensamblado**   |           Versión de la instancia de servicio.           |
   |      **Hora de finalización**       |          Fin del tiempo de la instancia de servicio.           |
   |     **Código de error**      | Cualquier código de error asociado a la instancia de servicio. |
   |      **Host Name**      |        Nombre de host de la instancia de servicio.        |
   |   **N.º máximo de coincidencias**   |          Número de coincidencias que se van a mostrar.           |
   |    **Clase de servicio**    |          Clase de la instancia de servicio.          |
   | **Id. de instancia de servicio** |               Identificador de la instancia de servicio.               |
   |    **Nombre de servicio**     |          El nombre de la instancia de servicio.           |
   |     **Start Time**      |       Tiempo de inicio de la instancia de servicio.        |
   |        **State**        |          Estado de la instancia de servicio.          |


6. Completar la **valor** columna según corresponda para la selección que haya realizado en el **nombre de campo** columna.  

7. Seguir agregando líneas adicionales a la consulta según corresponda, completando la **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  

## <a name="see-also"></a>Vea también  
 [Uso de la pestaña Consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)