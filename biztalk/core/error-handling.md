---
title: Control de errores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Messaging Engine, errors
- errors, Messaging Engine
- errors, messages
- messages, errors
ms.assetid: ebc889cc-eeac-483c-baf3-407a218f6d14
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cbf0d898f7af193220cf8f1c24e809aefa1b782
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-handling"></a>Tratamiento de errores
La ruta que sigue un mensaje a través del subsistema de mensajería de BizTalk Server abarca varios puntos de procesamiento y transferencia. En cada punto a lo largo de esta ruta, se pueden producir errores tanto en la infraestructura de BizTalk Server como en los elementos proporcionados por la aplicación, como los componentes de canalización personalizados y las orquestaciones.  
  
 Esta sección y las contenidas en ella describen los modos de error típicos que se producen en fases de procesamiento conocidas y cómo se controlan estos modos de error mediante la configuración y los elementos proporcionados por la aplicación (como las orquestaciones) de BizTalk Server. Entre las consecuencias de los errores se incluye la disposición del mensaje, la captura y el registro de información de diagnóstico y una serie de consideraciones sobre el funcionamiento.  
  
 Los eventos que se producen cuando un mensaje tiene errores dependen de la ubicación del error y del estado del enrutamiento de mensajes con errores y del procesamiento de intercambio recuperable. La tabla siguiente resume el comportamiento del error y reanuda la ubicación de error de canalizaciones y suscripción.  
  
|Tipo de error|Enrutamiento de mensajes con errores|Procesamiento de intercambio recuperable|Comportamiento del error|Reanudar ubicación|  
|------------------|----------------------------|----------------------------------------|----------------------|---------------------|  
|Canalización|Deshabilitado|Deshabilitado|El mensaje se suspende antes de la canalización|Antes de la canalización.|  
|Canalización|Deshabilitado|Habilitado|El mensaje se suspende después de la canalización|Antes de la canalización. Para obtener más información sobre el procesamiento de intercambio recuperable, consulte [procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md).|  
|Canalización|Habilitado|Deshabilitado|El mensaje se publica con propiedades promocionadas de contexto del mensaje relacionado con el informe de errores|El mensaje no se suspende. Para obtener más información acerca de los mensajes error de enrutamientos, consulte [utilizando Error Message Routing](../core/using-failed-message-routing.md).|  
|Canalización|Habilitado|Habilitado|El mensaje se publica con propiedades promocionadas de contexto del mensaje relacionado con el informe de errores.|El mensaje no se suspende.|  
|Suscripción|Deshabilitado|Deshabilitado|El mensaje se suspende antes de la canalización. Informe de error de enrutamiento creado.|El mensaje se reanudará antes de la canalización. El informe de error de enrutamiento es no reanudable.|  
|Suscripción|Deshabilitado|Habilitado|El mensaje se suspende después de la canalización. Informe de error de enrutamiento creado.|El mensaje se reanudará antes de la canalización. El informe de error de enrutamiento es no reanudable. Para obtener más información sobre el procesamiento de intercambio recuperable, consulte [procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md).|  
|Suscripción|Habilitado|Deshabilitado|El mensaje se publica con propiedades promocionadas de contexto del mensaje relacionado con el informe de errores. Informe de error de enrutamiento creado.|El mensaje no se suspende. El informe de error de enrutamiento es no reanudable. Para obtener más información acerca de los mensajes error de enrutamientos, consulte [utilizando Error Message Routing](../core/using-failed-message-routing.md).|  
|Suscripción|Habilitado|Habilitado|El mensaje se publica con propiedades promocionadas de contexto del mensaje relacionado con el informe de errores. Informe de error de enrutamiento creado.|El mensaje no se suspende. El informe de error de enrutamiento es no reanudable.|  
  
 Muchos de los modos de error enumerados se corresponden con características específicas de BizTalk Server que están diseñadas para el modo de errores, como el procesamiento de intercambio recuperable y los informes de errores. Otros modos de error están relacionados con cómo BizTalk Server comunica la información de errores a los elementos de aplicación y cómo dichos elementos de aplicación (por ejemplo componentes de canalizaciones personalizados, adaptadores y orquestaciones) comunican a su vez la información de errores a BizTalk Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Usar el enrutamiento de mensajes con errores](../core/using-failed-message-routing.md)  
  
-   [Cómo habilitar el enrutamiento para mensajes con errores](../core/how-to-enable-routing-for-failed-messages.md)  
  
-   [Usar confirmaciones](../core/using-acknowledgments.md)  
  
## <a name="see-also"></a>Vea también  
 [Procesamiento de intercambio recuperable](../core/recoverable-interchange-processing.md)   
 [Tipos de errores de mensaje](../core/types-of-message-failures.md)