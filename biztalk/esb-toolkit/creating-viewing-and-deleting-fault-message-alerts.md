---
title: Crear, ver y eliminar error mensaje alertas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59df2b40-b42c-4167-873c-0819839919da
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55894eca1baa8ca6616c67f623a87e8015a2f32f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974450"
---
# <a name="creating-viewing-and-deleting-fault-message-alerts"></a>Crear, ver y eliminar las alertas de mensaje de error
El Portal de administración de ESB pueden generar alertas cuando llegan los mensajes de error en el portal, basándose en una comparación de valores en el mensaje con los criterios especificados para la alerta. El portal también puede mantener una lista de notificaciones de alertas vinculado a una persona y los usuarios, y notificará a estos usuarios cuando proactivamente genera alertas.  
  
### <a name="to-create-and-configure-a-new-alert"></a>Para crear y configurar una nueva alerta  
  
1.  Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md) para ver una lista de las alertas existentes y las suscripciones actuales de estas alertas.  
  
2.  Haga clic en el **crear alertas** vínculo para abrir el [Agregar página alerta](../esb-toolkit/add-alert-page.md).  
  
3.  En el **escriba el nombre de alerta** cuadro de texto, escriba un nombre para la nueva alerta.  
  
4.  En el **condiciones** sección de la página Agregar alerta, seleccione un campo (como **aplicación**, **tipo de Error**, o **gravedad de error**) en el **Criterios** lista desplegable; seleccione un tipo de comparación (como +, =,! =, > =, < =, o **como**) en el **operador** lista desplegable y escriba o seleccione un valor de la tercero lista o cuadro de texto (denominado **valor**). Al seleccionar un **criterios** valor, la página cambia para mostrar un cuadro de texto o una lista desplegable para el valor coincidente. Todas las condiciones se combinan con el **AND** operador.  
  
5.  Haga clic en el **agregar** use el vínculo para agregar esta condición a la lista y, a continuación, repita el paso anterior para agregar más condiciones Si es necesario.  
  
6.  Haga clic en el **guardar** botón para crear una nueva alerta con el nombre especificado y condiciones.  
  
### <a name="to-view-details-of-an-existing-alert-or-delete-an-existing-alert"></a>Para ver los detalles de una alerta existente o eliminar una alerta existente  
  
1.  Abra la [página de alertas del Portal](../esb-toolkit/portal-alerts-page.md).  
  
2.  Para eliminar una alerta, haga clic en el **Eliminar alerta** icono en la columna de acción de una alerta existente.  
  
    > [!NOTE]
    >  Los usuarios no administrativos pueden eliminar sólo las alertas para que sean propietarios, y de que hay actualmente ningún suscriptor. Debe iniciar sesión en el portal como un administrador elimine otras alertas.  
  
3.  Para ver los detalles de una alerta, haga clic en el **vista** icono en la columna de acción de una alerta existente. Se abrirá la página de Visor de alertas.  
  
4.  Haga clic en **exportar a Excel** para descargar la lista completa de las alertas en un formato que se puede ver en Microsoft Excel.