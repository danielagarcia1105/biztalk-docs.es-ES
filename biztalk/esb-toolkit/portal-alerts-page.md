---
title: Página de alertas del portal | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 131b4750-ce3d-445f-be0e-6bf499734c69
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 252da9de050c228a7b2d8a4f549d2d084e2a2f81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978709"
---
# <a name="portal-alerts-page"></a>Página de alertas del portal
Figura 1 muestra la página de alertas, que contiene dos secciones:  

- La sección principal muestra un vínculo para crear una nueva alerta y una lista de las alertas existentes. Cada alerta tiene un vínculo correspondiente que le permite suscribirse a la alerta. También puede hacer clic en los iconos en la columna de acción para ver los detalles de la alerta, cree una nueva suscripción para la alerta y eliminar la alerta.  

- El **Mis suscripciones** sección muestra una lista de suscripciones que se ha definido en el portal. Puede editar y cancelar la suscripción a las suscripciones existentes con los vínculos de esta lista.  

  ![Página de alertas del portal](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")  

  **Figura 1**  

  **La página de alertas de Portal de administración de ESB**  

  El servicio de alerta de ESB genera alertas basadas en criterios que especifique que coinciden con los valores de las excepciones cuando llegan en el Portal de administración de ESB. Puede coincidir con y comparar un intervalo de campos de una excepción para controlar con precisión las alertas que coincidirá con cada posible tipo de excepción. El portal también permite crear suscripciones que se asignan a los distintos tipos de alertas que defina. Estas suscripciones pueden notificar a los usuarios cuando se produzca la alerta correspondiente.  

  En la lista siguiente se explica cómo puede usar las características de la página de alertas de Portal de administración de ESB:  

- Para crear una nueva alerta, haga clic en el **crear alerta** vínculo en la parte superior de la página para abrir la página Agregar alerta.  

- Para ver o editar una alerta existente, haga clic en el icono de lupa en la columna de acción de la alerta en la sección de la página principal. Se abrirá el [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md).  

- Para suscribirse a una alerta existente, haga clic en el icono de suscripción de nuevo la columna de acción junto a la alerta para abrir el [Agregar suscripción de alerta y editar páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).  

- Si abre esta página como un administrador mediante las opciones en el **Admin** menú de la pestaña (en lugar de desde el **alertas** pestaña), puede hacer clic en el icono de marca de tachado en la columna acción situada junto a cualquiera de las alertas en la lista para eliminar las alertas y las suscripciones.  

- Para editar una suscripción existente, haga clic en el **editar** vínculo situado junto a esa suscripción en la lista en el **Mis suscripciones** sección de la página para abrir el [Agregar suscripción de alerta y editar Las páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).  

- Para quitar una suscripción existente, haga clic en el **Unsubscribe** vínculo situado junto a esa suscripción en la lista en el **Mis suscripciones** sección de la página.  

- Para exportar toda la lista de alertas en Microsoft Excel, haga clic en **exportar a Excel**.
