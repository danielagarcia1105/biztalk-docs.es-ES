---
title: "Página principal del portal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60072c30-d57b-4bd8-a7ee-b4d0fa50de58
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c2c525fdc8e5786143e8b4f942f0f2379226d3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="portal-home-page"></a>Página principal del portal
La figura 1 muestra la página de inicio, que contiene cuatro secciones:  
  
-   El **gráficos** sección contiene un desglose de errores de aplicación, por tipo y un análisis con el tiempo, que indica el estado general de toda la empresa desde una perspectiva de la aplicación.  
  
-   El **registro** sección contiene una lista de solicitudes recientes para publicación de extremo de servicio que se envían al servicio de Universal Description, Discovery y Integration (UDDI).  
  
-   El **historial de la alerta** sección muestra una lista de alertas recibidas por el servicio de alertas.  
  
-   El **errores** sección muestra una lista abreviada de los errores más recientes generados por el mecanismo de excepción enrutamiento de orquestación de error de ESB y el mecanismo de enrutamiento de mensajes de error de BizTalk. La lista muestra los errores, agrupados por aplicación y muestra la gravedad, nombre del servicio, tipo de error y la fecha y hora para cada error en la lista.  
  
 ![Página principal del portal](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  
  
 **Figura 1**  
  
 **La página principal del Portal de administración de ESB**  
  
 En la lista siguiente se explica cómo puede usar las características de la página principal del Portal de administración de ESB.  
  
-   Al cargar la página de inicio por primera vez, no verá todas las aplicaciones en el primer gráfico. Para seleccionar las aplicaciones para el que desea ver la información, haga clic en el **seleccionar aplicaciones** vincular por encima del primer gráfico y, a continuación, active o desactive las casillas de verificación en la lista de aplicaciones instaladas de BizTalk que aparece. También puede usar los vínculos que aparecen seleccionar todas o ninguna de las aplicaciones. Haga clic en **guardar** para mostrar la información de las aplicaciones seleccionadas, o haga clic en **cancelar** abandonar los cambios. Puede cambiar la lista predeterminada de las aplicaciones en el [página de configuración de Portal de mi](../esb-toolkit/portal-my-settings-page.md).  
  
-   Para cambiar el período para el que el portal muestra información, cambiar la configuración en la lista desplegable situada encima del primer gráfico. Puede decidir mostrar la información de la anterior **hora, día, semana,** o **mes**. Puede cambiar el período predeterminado en el [página de configuración de Portal de mi](../esb-toolkit/portal-my-settings-page.md).  
  
-   Para activar o desactivar la publicación automática de las entradas UDDI, haga clic en el **cambio** vínculo en la parte superior de la **registro** sección de la página. Se abrirá la [página de configuración del registro](../esb-toolkit/registry-settings-page.md), donde se especifique lo siguiente:  
  
    -   Detalles del servidor UDDI utilizará el portal, incluido el identificador URI del servidor, si está habilitada la publicación automática y si está habilitado el acceso anónimo  
  
    -   Si no están habilitadas las notificaciones de correo electrónico de publicaciones de UDDI y la configuración que se usará para el servidor de correo electrónico, direcciones de correo electrónico, asunto del mensaje y el cuerpo del mensaje.  
  
    -   El nombre y correo electrónico dirección de contacto para las entradas publicadas.  
  
-   Para ver una lista de solicitudes de registro UDDI pendientes, haga clic en el vínculo situado en la parte superior de la **registro** sección de la página que muestra el número de solicitudes pendientes. Se abrirá la [administrar la página de solicitudes pendientes](../esb-toolkit/manage-pending-requests-page.md), que contiene lo siguiente:  
  
    -   **Una lista de solicitudes de registro pendientes**. Para cada una de ellas, puede hacer clic en los iconos situados a la derecha de la solicitud para ver los detalles, aprobar la solicitud o rechazar la solicitud. Cuando se ve la solicitud, ver los detalles del registro, los detalles del servicio del registro (que se puede modificar) y detalles de contacto.  
  
    -   **Un vínculo para mostrar un historial de solicitudes como una lista**. Esta lista muestra un intervalo de valores de cada solicitud de registro.  
  
-   Para cambiar el criterio de ordenación de los errores enumerados en la **errores** sección de la página, haga clic en el **fecha** o **gravedad** botón de opción situado encima de la lista de errores.  
  
-   El portal muestra los errores de la **errores** sección de la página agrupados por la aplicación de BizTalk. Para ver los errores para una aplicación específica, haga clic en el vínculo que es el nombre de la aplicación supere el grupo pertinente de errores.  
  
-   Para ver los detalles de un error específico, haga clic en cualquier parte en la fila que contiene ese error en el **errores** sección de la página. Se abrirá la [Visor de mensajes de error de Portal](../esb-toolkit/portal-fault-message-viewer.md) para el error seleccionado.