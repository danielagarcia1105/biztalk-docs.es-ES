---
title: Agregar suscripción de alerta y editar las páginas de suscripción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad5e99f1-714e-458b-b5f0-85ac69be5335
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b843bde8905d8b6803dda56a6370f70c934a610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013453"
---
# <a name="add-alert-subscription-and-edit-subscription-pages"></a>Agregar suscripción de alerta y editar las páginas de suscripción
Las páginas Agregar suscripción de alerta y Editar suscripción son similares. Se diferencian en que la página Editar suscripción muestra el identificador de suscriptor (la cuenta de Microsoft Windows del usuario del portal actual) y tiene un conjunto diferente de botones. Figura 1 muestra las páginas Agregar suscripción de alerta y Editar suscripción.  

 ![Agregar suscripción de alerta edición](../esb-toolkit/media/ch8-addalerteditsubscription.gif "Ch8-AddAlertEditSubscription")  

 **Figura 1**  

 **Las páginas de ESB Management Portal Agregar suscripción de alerta y Editar suscripción**  

 Las páginas Agregar suscripción de alerta y Editar suscripción le permiten especificar y modificar los siguientes elementos:  

- Una dirección de correo electrónico personalizado que se usará para la suscripción (en lugar de la dirección de correo electrónico de tu cuenta de Microsoft Windows)  

- El período de tiempo cuando aceptará las notificaciones de alerta  

- Un período "black" para eventos como vacaciones  

- El intervalo durante el que el portal no enviará alertas duplicadas  

  Puede hacer lo siguiente en las páginas Agregar suscripción de alerta y Editar suscripción:  

- Active la casilla situada junto a la **correo electrónico personalizados** texto cuadro si desea usar una dirección de correo electrónico de la suscripción que es diferente a la dirección de correo electrónico de cuenta de Windows estándar y, a continuación, escriba la dirección de correo electrónico preferida en el cuadro de texto.  

- Active la casilla situada en la parte superior de la **programación** sección si desea especificar un período cuando el portal debe enviar alertas a usted y, a continuación, especifique las horas inicial y final para el período en el **Start Time** y **Hora de finalización** listas desplegables. Alertas que se producen fuera de este período se ponen en cola y entregadas durante el período especificado.  

- Escriba la fecha de inicio y fecha de finalización de un **negro de espera** si hay un período cuando no será posible recibir y actuar en las alertas. Use el formato mm/dd/aaaa para las dos fechas.  

- Seleccione un **intervalo** en **minutos** durante el que el portal de comparará las alertas emitidas y enviar sólo uno cuando se producen varias instancias de la misma alerta. Esto evita que un error que se producen rápidamente desde la creación de un gran número de mensajes de alerta idénticos.  

- Haga clic en el **guardar** botón para crear o actualizar la suscripción.  

- Haga clic en el **eliminar** botón (disponible solo en la página Editar suscripción) para eliminar la suscripción seleccionada.  

- Haga clic en el **cancelar** botón para volver a la [página del Visor de alertas](../esb-toolkit/alert-viewer-page.md) sin crear ni modificar la suscripción.
