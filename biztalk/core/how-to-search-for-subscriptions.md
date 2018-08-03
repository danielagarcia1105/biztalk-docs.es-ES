---
title: Cómo buscar suscripciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query tab [Administration Console], subscriptions
- Query tab [Administration Console], searching
- subscriptions, viewing
- subscriptions, searching
ms.assetid: 95f8fd20-2750-412b-a67b-18976e7706e2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07230ace1e097d71e728110b8f2280e903ea67b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023250"
---
# <a name="how-to-search-for-subscriptions"></a>Cómo buscar suscripciones
Puede usar el **consulta** ficha en la consola de administración de BizTalk Server para buscar suscripciones. Esto resulta muy útil para revisar todas las suscripciones definidas en el sistema. Al solucionar problemas de enrutamiento, se pueden revisar suscripciones para ver si hay alguna con una configuración incorrecta (puesto que ésta sería la causa del problema de enrutamiento).  

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.  

### <a name="to-search-for-subscriptions"></a>Para buscar suscripciones  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)].  

2. En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.  

3. En el panel de detalles, haga clic en el **nueva consulta** ficha.  

4. En el **expresión de consulta** grupo, en el **valor** columna, seleccione **suscripciones** desde el cuadro de lista desplegable.  

5. En el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\***), seleccione una o varias de las siguientes acciones:  


   |          Elemento           |                                    Descripción                                    |
   |-------------------------|-----------------------------------------------------------------------------------|
   |   **N.º máximo de coincidencias**   |                         Número de coincidencias que se van a mostrar.                         |
   | **Id. de instancia de servicio** |               Puede filtrar las suscripciones por Id. de instancia de servicio.                |
   |    **Nombre de servicio**     |                   Puede filtrar las suscripciones por nombre de servicio.                   |
   |  **Tipo de suscripción**  | Puede filtrar las suscripciones por suscripción de activación o suscripción de instancia. |


6. Completar la **valor** columna según corresponda para la selección que haya realizado en el **nombre de campo** columna.  

7. Seguir agregando líneas adicionales a la consulta según corresponda, completando la **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  

## <a name="see-also"></a>Vea también  
 [Uso de la pestaña Consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)