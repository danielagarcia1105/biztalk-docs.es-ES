---
title: Enviar informe de detalles de estado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbc9d44-9a9a-4272-a138-ebd126a9f809
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2335b10da205258f32a6676a6fee2a3ff32fef65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="resend-status-details-report"></a>Reenvío del informe de detalles de estado
En este informe de estado se muestra información sobre el número de reintentos efectuados cuando las propiedades de entidad y de receptor AS2 de una entidad se han configurado para reenviar el mensaje AS2 si no se ha recibido un MDN.  
  
 Para mostrar este informe haciendo doble clic en un mensaje en el informe de estado AS2/MDN y, a continuación, haga clic en **ver estado de mensajería confiable**. En la página de reenvío de detalles de estado se mostrará información sobre los intentos de reenvío efectuados para ese mensaje.  
  
 Este informe solo está disponible si ha seleccionado **reenviar mensaje AS2 si no se recibe MDN** en la entidad como propiedades de receptor del mensaje AS2 de la entidad relacionada.  
  
 En el informe se muestra información sobre los reintentos efectuados para el mensaje en las páginas siguientes:  
  
|Página|Datos mostrados|  
|----------|--------------------|  
|**General**|El índice del intento de envío actual, así como la configuración de reenvío.|  
|**Historial de reenvío**|Historial de los intentos de envío del mensaje.|