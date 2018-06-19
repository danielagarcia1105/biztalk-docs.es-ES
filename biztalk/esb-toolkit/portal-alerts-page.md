---
title: Página de alertas del portal | Documentos de Microsoft
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
ms.openlocfilehash: ba854c269db4a1d7eabb021a974fa9614abb7690
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294884"
---
# <a name="portal-alerts-page"></a>Página de alertas del portal
La figura 1 muestra la página de alertas, que contiene dos secciones:  
  
-   La sección principal muestra un vínculo para crear una nueva alerta y una lista de las alertas existentes. Cada alerta incluye un vínculo correspondiente que le permite suscribirse a la alerta. También puede hacer clic en los iconos en la columna de acción para ver los detalles de la alerta, cree una nueva suscripción para la alerta y eliminar la alerta.  
  
-   El **Mis suscripciones** sección muestra una lista de las suscripciones que ha definido en el portal. Puede editar y cancelar la suscripción las suscripciones existentes mediante los vínculos de esta lista.  
  
 ![Página de alertas del portal](../esb-toolkit/media/ch8-portalalertspage.gif "Ch8-PortalAlertsPage")  
  
 **Figura 1**  
  
 **La página de alertas de Portal de administración de ESB**  
  
 El servicio de alertas de ESB genera alertas en función de criterios que especifique que coinciden con los valores de las excepciones cuando llegan en el Portal de administración de ESB. Puede coincidir con y comparar un intervalo de campos de una excepción para controlar con precisión las alertas que coincidirá con cada posible tipo de excepción. El portal también permite crear suscripciones que se asignan a los distintos tipos de alertas que defina. Estas suscripciones pueden notificar a los usuarios cuando se produzca la alerta correspondiente.  
  
 En la lista siguiente se explica cómo puede usar las características de la página de alertas de Portal de administración de ESB:  
  
-   Para crear una nueva alerta, haga clic en el **crear alerta** vínculo en la parte superior de la página para abrir la página Agregar alerta.  
  
-   Para ver o modificar una alerta existente, haga clic en el icono de lupa en la columna de acción de la alerta en la sección principal de la página. Se abrirá la [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md).  
  
-   Para suscribirse a una alerta existente, haga clic en el icono de suscripción de nuevo la columna acción situada junto a la alerta para abrir el [Agregar suscripción de alerta y editar páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).  
  
-   Si abre esta página como un administrador mediante las opciones en el **administración** menú de la pestaña (en lugar de desde el **alertas** ficha), puede hacer clic en el icono de marca entre la columna acción situada junto a cualquiera de las alertas de la lista para eliminar las suscripciones de alerta y cualquier vinculadas.  
  
-   Para editar una suscripción existente, haga clic en el **editar** vínculo situado junto a esa suscripción en la lista en la **Mis suscripciones** sección de la página para abrir el [Agregar suscripción de alertas y editar Páginas de suscripción](../esb-toolkit/add-alert-subscription-and-edit-subscription-pages.md).  
  
-   Para quitar una suscripción existente, haga clic en el **Unsubscribe** vínculo situado junto a esa suscripción en la lista en la **Mis suscripciones** sección de la página.  
  
-   Para exportar toda la lista de alertas a Microsoft Excel, haga clic en **exportar a Excel**.