---
title: Página principal del portal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60072c30-d57b-4bd8-a7ee-b4d0fa50de58
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cec16922e7d7f5075942577750867c4739602e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011029"
---
# <a name="portal-home-page"></a>Página principal del portal
Figura 1 muestra la página principal, que contiene cuatro secciones:  

- El **gráficos** sección contiene un desglose de errores por aplicación, por tipo y un análisis con el tiempo, que indica el estado general de toda la empresa desde una perspectiva de la aplicación.  

- El **registro** sección contiene una lista de las solicitudes recientes para publicación de extremo de servicio que se envían al servicio de Universal Description, Discovery and Integration (UDDI).  

- El **historial de la alerta** sección muestra una lista de alertas recibidas por el servicio de alertas.  

- El **errores** sección muestra una lista resumida de los errores más reciente generado por el mecanismo de excepción enrutamiento de orquestación de error de ESB y el mecanismo de enrutamiento de mensajes de error de BizTalk. La lista muestra los errores, agrupados por la aplicación y muestra la gravedad, el nombre de servicio, tipo de error y la fecha y hora para cada error en la lista.  

  ![Página principal del portal](../esb-toolkit/media/portalhomepage.gif "PortalHomePage")  

  **Figura 1**  

  **La página principal del Portal de administración de ESB**  

  En la lista siguiente se explica cómo puede usar las características de la página principal del Portal de administración de ESB.  

- Al cargar la página principal en primer lugar, puede que no vea todas las aplicaciones en el primer gráfico. Para seleccionar las aplicaciones para la que desea ver la información, haga clic en el **seleccionar aplicaciones** vincular por encima del primer gráfico y, a continuación, active o desactive las casillas de verificación en la lista de aplicaciones de BizTalk instaladas que aparece. También puede usar los vínculos que aparecen seleccionar todas o ninguna de las aplicaciones. Haga clic en **guardar** para mostrar la información de las aplicaciones seleccionadas, o haga clic en **cancelar** para abandonar los cambios. Puede cambiar la lista predeterminada de las aplicaciones en la [mi página de configuración del Portal](../esb-toolkit/portal-my-settings-page.md).  

- Para cambiar el período para el que el portal muestra información, cambiar la configuración en la lista desplegable situada encima del primer gráfico. Puede elegir mostrar la información de la anterior **hora, día, semana,** o **mes**. Puede cambiar el período predeterminado en el [mi página de configuración del Portal](../esb-toolkit/portal-my-settings-page.md).  

- Para activar o desactivar la publicación automática de las entradas UDDI, haga clic en el **cambio** vínculo en la parte superior de la **registro** sección de la página. Se abrirá el [página de configuración del registro](../esb-toolkit/registry-settings-page.md), donde debe especificar lo siguiente:  

  -   Detalles del servidor UDDI usará el portal, incluido el URI del servidor, si está habilitada la publicación automática y si está habilitado el acceso anónimo  

  -   Si están habilitadas las notificaciones de correo electrónico de las publicaciones de UDDI y la configuración que se usará para el servidor de correo electrónico, direcciones de correo electrónico, asunto del mensaje y cuerpo del mensaje.  

  -   Su nombre y correo electrónico dirección de contacto para las entradas publicadas.  

- Para ver una lista de solicitudes de registro UDDI pendientes, haga clic en el vínculo situado en la parte superior de la **registro** sección de la página que muestra el número de solicitudes pendientes. Se abrirá el [administrar página de solicitudes pendientes](../esb-toolkit/manage-pending-requests-page.md), que contiene lo siguiente:  

  -   **Una lista de solicitudes de registro pendientes**. Para cada uno, puede hacer clic en los iconos a la derecha de esa solicitud para ver los detalles, apruebe la solicitud o rechazar la solicitud. Al ver la solicitud, puede ver los detalles del registro, los detalles del servicio del registro (que se puede modificar) y detalles de contacto.  

  -   **Un vínculo para mostrar un historial de solicitudes como una lista**. Esta lista muestra un intervalo de valores de cada solicitud de registro.  

- Para cambiar el criterio de ordenación de los errores enumerados en la **errores** sección de la página, haga clic en el **fecha** o **gravedad** botón de opción situado encima de la lista de errores.  

- El portal muestra los errores de la **errores** sección de la página agrupados por la aplicación de BizTalk. Para ver los errores para sólo una aplicación específica, haga clic en el vínculo que es el nombre de la aplicación por encima del grupo de errores pertinente.  

- Para ver los detalles de un error específico, haga clic en la fila que contiene ese error en la **errores** sección de la página. Se abrirá el [Portal Visor de mensajes de error](../esb-toolkit/portal-fault-message-viewer.md) para el error seleccionado.
