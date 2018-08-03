---
title: Cómo buscar instancias de servicio suspendidas | Microsoft Docs
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
- service instances, suspended
- Query tab [Administration Console], searching
- instances, suspended
- instances, services
ms.assetid: f91b1151-d879-4aa7-afc8-4cf13d928158
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a2ed50337f45a158614755a10beb8f2be15f2c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971757"
---
# <a name="how-to-search-for-suspended-service-instances"></a>Cómo buscar instancias de servicio suspendidas
Puede usar el **consulta** ficha en la consola de administración de BizTalk Server para buscar instancias de servicio suspendidas. Puede buscar un determinado subconjunto de mensajes para localizar un mensaje concreto asociado a un host, tipo, nombre de servicio, etc.  

> [!NOTE]
>  Las instancias finalizadas con mensajes sin consumir se muestran como un código de error (“Finalizada con mensajes sin consumir”) para las instancias de servicio suspendidas correspondientes. Estas instancias son no reanudables.  

> [!NOTE]
>  Al agrupar y filtrar por URI o por nombre de adaptador con error, los resultados solo mostrarán los puertos de envío y recepción. No se podrá agrupar ni filtrar por URI en el caso de las orquestaciones, ya que éstas no se incluyen en los resultados.  

## <a name="prerequisites"></a>Requisitos previos  
 Para realizar este procedimiento, debe haber iniciado sesión como miembro del grupo de operadores de BizTalk Server.  

### <a name="to-search-for-suspended-service-instances"></a>Para buscar instancias de servicio suspendidas  

1. Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  

2. En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.  

3. En el panel de detalles, haga clic en el **nueva consulta** ficha.  

4. En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio suspendidas** desde el cuadro de lista desplegable.  

5. En el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\***), seleccione una o varias de las siguientes acciones:  


   |         Elemento          |                                                                                                                                                                                                                   Descripción                                                                                                                                                                                                                   |
   |-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Application Name**  |                                                                                                                                                                                                   Nombre de aplicación de BizTalk Server.                                                                                                                                                                                                   |
   |   **Hora de creación**   |                                                                                                                                                                                  Encontrar instancias de servicio suspendidas, creadas antes o después de la fecha indicada.                                                                                                                                                                                   |
   |   **Adaptador con error**   | Puede agrupar o filtrar instancias de servicio suspendidas por tipo de adaptador. Por ejemplo: archivo, FTP, HTTP, MQSeries, MSMQ, POP3, SMTP, SOAP o Windows SharePoint Services. **Nota:** en los resultados de consulta, el campo de adaptador solo se rellena cuando el tiempo de ejecución de BizTalk Server se ejecuta en un error al usar el adaptador especificado. Si el tiempo de ejecución no encuentra un error en el adaptador, en los resultados de la consulta, el campo Adaptador con error estará vacío. |
   |    **Código de error**     |                                                                                                                                                 Permite agrupar o filtrar las instancias de servicio suspendidas por código de error para que se muestren todas las instancias de servicio que se hayan suspendido con dicho código de error.                                                                                                                                                  |
   | **Descripción del error** |                                                                                                                                                                            Puede agrupar o filtrar las instancias de servicio suspendidas con la descripción de error especificada.                                                                                                                                                                            |
   | **Agrupar resultados por**  |                                                                                                                                        Puede agrupar o filtrar los resultados por adaptador, aplicación, código de error, descripción del error, nombre del host, clase de servicio, estado de instancia de servicio, nombre de servicio o URI.                                                                                                                                         |
   |     **Host Name**     |                                                                                                                                                                                            Agrupar o filtrar las instancias de servicio suspendidas por nombre de host.                                                                                                                                                                                            |
   |  **Estado de la instancia**  |                                                                                                                                                                         Puede buscar las instancias suspendidas en función de si pueden o no reanudarse.                                                                                                                                                                         |
   |  **N.º máximo de coincidencias**  |                                                                                                                                                                                                        Número de coincidencias que se van a mostrar.                                                                                                                                                                                                        |
   |   **Clase de servicio**   |                                                                                                                                                       Puede buscar adaptadores aislados, mensajería, mensajería y adaptadores aislados, MSMQT, orquestación o informes de error de enrutamiento.                                                                                                                                                       |
   |   **Nombre de servicio**    |                                                                                                                                                                                      Puede agrupar o filtrar las instancias de servicio suspendidas por nombre de servicio.                                                                                                                                                                                       |
   |  **Id. de tipo de servicio**  |                                                                                                                                                                                     Puede agrupar o filtrar las instancias de servicio suspendidas por Id. de tipo de servicio.                                                                                                                                                                                     |
   |  **Hora de suspensión**  |                                                                                                                                                                        Puede agrupar o filtrar las instancias de servicio suspendidas antes o después de la fecha especificada.                                                                                                                                                                        |
   |        **IDENTIFICADOR URI**        |                                              Puede agrupar o filtrar las instancias de servicio suspendidas por URI. **Nota:** en los resultados de consulta, el URI solo se rellena cuando el tiempo de ejecución de BizTalk Server se ejecuta en un error al enviar al URI especificado. Si el tiempo de ejecución no encuentra un error al enviar al URI, en los resultados de la consulta, el campo URI estará vacío o mostrará un mensaje que indica que el URI no está disponible.                                              |


6. Completar la **valor** columna según corresponda para la selección que haya realizado en el **nombre de campo** columna.  

7. Seguir agregando líneas adicionales a la consulta según corresponda, completando la **nombre de campo**, **operador**, y **valores** columnas y, a continuación, haga clic en **ejecutar Consulta**.  

## <a name="see-also"></a>Vea también  
 [Uso de la pestaña Consulta de la consola de administración](../core/using-the-administration-console-query-tab.md)