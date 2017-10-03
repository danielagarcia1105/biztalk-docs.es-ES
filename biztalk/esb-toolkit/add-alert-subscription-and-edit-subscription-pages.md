---
title: "Agregar suscripción de alertas y editar páginas de suscripción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49bed9959b51439f21d625795a69804fd41d77ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a>Agregar suscripción de alertas y editar páginas de suscripción
Las páginas de suscripción de alerta agregar y Editar suscripción son similares. Se diferencian en que la página Editar suscripción muestra el identificador de suscriptor (la cuenta de Microsoft Windows del usuario del portal actual) y tiene un conjunto diferente de botones. La figura 1 muestra las páginas de suscripción de alerta agregar y Editar suscripción.  
  
 ![Agregar suscripción de edición de alerta](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")  
  
 **Figura 1**  
  
 **Las páginas de ESB Management Portal Agregar suscripción de alertas y Editar suscripción**  
  
 Las páginas de suscripción de alerta agregar y Editar suscripción permiten especificar y modificar los siguientes elementos:  
  
-   Una dirección de correo electrónico personalizado que se utilizará para la suscripción (en lugar de la dirección de correo electrónico de tu cuenta de Microsoft Windows)  
  
-   El período de tiempo cuando aceptará las notificaciones de alerta  
  
-   Un período de "negro horizontal" para los eventos como vacaciones  
  
-   El intervalo sobre el que el portal no enviará alertas duplicadas  
  
 Puede hacer lo siguiente en las páginas de suscripción de alerta agregar y Editar suscripción:  
  
-   Active la casilla situada junto a la **correo electrónico personalizado** texto cuadro si desea usar una dirección de correo electrónico de la suscripción que es diferente a la dirección de correo electrónico de cuenta de Windows estándar y, a continuación, escriba la dirección de correo electrónico preferida en el cuadro de texto.  
  
-   Active la casilla situada en la parte superior de la **programación** sección si desea especificar un período cuando el portal debe enviar alertas a usted y, a continuación, especifique las horas de inicio y finalización para el período en el **Start Time** y **Hora de finalización** listas desplegables. Alertas que se producen fuera de este período se ponen en cola y se entregan durante el período especificado.  
  
-   Escriba la fecha de inicio y fecha de finalización de un **negro de espera** si hay un período cuando no se podrá recibir y actuar en alertas. Use el formato mm/dd/aaaa para las dos fechas.  
  
-   Seleccione un **intervalo** en **minutos** durante la que el portal de comparará las alertas emitidas y enviar sola cuando se producen varias instancias de la misma alerta. Esto evita que un error rápidamente que se está produciendo desde la creación de un gran número de mensajes de alerta idénticos.  
  
-   Haga clic en el **guardar** botón para crear o actualizar la suscripción.  
  
-   Haga clic en el **eliminar** botón (disponible únicamente en la página Editar suscripción) para eliminar la suscripción seleccionada.  
  
-   Haga clic en el **cancelar** botón para volver atrás y el [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md) sin la creación o modificación de la suscripción.