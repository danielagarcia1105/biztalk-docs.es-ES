---
title: "Adaptador de WCF preguntas más frecuentes: Control de errores WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdbd1ea6-4898-415c-ac5e-f804565759a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efbac0b7aaffd6121cba406031a8330cfd5bbf2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-wcf-error-handling"></a>P+F del adaptador WCF: Control de errores WCF
## <a name="how-do-the-wcf-adapters-handle-errors-and-soap-faults-during-message-processing"></a>¿Cómo controlan los adaptadores de WCF los errores y los errores de SOAP durante el procesamiento de mensajes?  
 Para una ubicación de recepción, puede configurar una de las dos opciones de control de errores en el **control de errores** sección en la **mensajes** pestaña en el **propiedades de transporte** cuadro de diálogo cuadro.  
  
 Si el **suspender el mensaje de solicitud en caso de error** opción está seleccionada, se suspenderá el mensaje de solicitud entrante debe haber un error de procesamiento en la canalización de recepción o un error en el enrutamiento del mensaje. Esto permite al remitente del mensaje realizar correctamente la transmisión a BizTalk Server y recibir un mensaje de confirmación (ACK). El servidor BizTalk Server suspenderá el mensaje y registrará un registro de error completo para el mensaje con error. Sin embargo, no devuelve la excepción del mensaje al remitente en este caso. Esto se aplica únicamente a puertos unidireccionales. Si está activada, enviará una confirmación y si está desactivada, enviará una NACK. Para los puertos bidireccionales, si se produce un error de procesamiento, BizTalk siempre recibirá una NACK.  
  
 Sin embargo, si el cliente necesita tener acceso a la excepción Error, seleccione la **incluir detalles de la excepción en errores** opción. Cuando se selecciona esta opción, si se produce un error de procesamiento devuelve un error de SOAP al usuario que realiza la llamada. Esto es lo mismo que especificar el comportamiento de serviceDebug con "includeexceptiondetailsinfaults"establecido en True en la **comportamiento** ficha de los adaptadores de WCF-Custom o WCF-CustomIsolated. La excepción detallada se envía ahora al cliente. Esta opción es más práctica y segura de usar durante el desarrollo de una aplicación que en producción porque es más probable que los mensajes de errores internos no se envíen a los llamadores del servicio.  
  
 Para el puerto de envío bidireccional, puede elegir si desea reenviar mensajes de error SOAP en la llamada original a través de una petición-respuesta puerto de envío seleccionando **propagar mensaje de error**. Si esta opción no se selecciona, el servidor BizTalk Server primero generará una NACK y luego suspenderá el mensaje. Si se selecciona, el servidor BizTalk Server tratará el mensaje como un mensaje de respuesta de WCF válido del servicio externo y el mensaje de respuesta no se suspenderá porque se propaga.  
  
## <a name="how-do-the-wcf-adapters-handle-message-transmission-timing-issues"></a>¿Cómo manejan los adaptadores de WCF los problemas de control de tiempo de transmisión de mensajes?  
 Puede controlar problemas de sincronización para los adaptadores de WCF mediante el **enlace** pestaña en el **propiedades de transporte** cuadro de diálogo. Estos valores son **abiertos**, **enviar**, y **tiempo de espera de cierre**. (También hay un tiempo de espera de recepción que se puede establecer mediante el uso de adaptadores personalizados). Estos valores son, respectivamente, el tiempo que tiene un canal para abrir, enviar y cerrar (y recibir en adaptadores personalizados) las operaciones antes de finalizar. Los valores predeterminados de los tres valores son 1 minuto como mínimo y un período máximo de 23:59.