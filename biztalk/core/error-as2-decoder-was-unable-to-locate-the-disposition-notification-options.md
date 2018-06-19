---
title: El descodificador AS2 no pudo localizar el encabezado HTTP Disposition-Notification-Options | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6de4b9a6-17b2-4455-9dbd-a6bb69fac1d5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 966860c7f2b7b47187b861ed6b81fb14a4753872
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240020"
---
# <a name="the-as2-decoder-was-unable-to-locate-the-disposition-notification-options-http-header"></a>El descodificador AS2 no ha podido localizar el encabezado HTTP Disposition-Notification-Options
## <a name="details"></a>Detalles  
  
|||  
|-|-|  
|Nombre del producto|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Versión del producto|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|Identificador del evento|-|  
|Origen del evento|EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|Componente|Motor AS2|  
|Nombre simbólico|AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError|  
|Texto del mensaje|El descodificador AS2 no ha podido localizar el encabezado HTTP Disposition-Notification-Options necesario para la generación de MDN.|  
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción no pudo generar el MDN porque el mensaje AS2 de entrada no incluyó el encabezado Disposition-Notification-Options que indica si el MDN debe firmarse o no y qué algoritmo MIC debe usarse.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del mensaje AS2 que incluya el encabezado Disposition-Notification-Options en el mensaje y, a continuación, vuelva a enviar el mensaje.