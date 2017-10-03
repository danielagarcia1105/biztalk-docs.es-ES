---
title: "Pasos de solución de escenario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77751c15-9b67-4587-8bc8-2be65f13d339
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dff3b2feda86ad0b8edbbded26a290c7276a63af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-solution-steps"></a>Pasos de solución de escenario
El marco de trabajo de administración de excepciones de ESB proporciona una solución sencilla para controlar una excepción cuando un mensaje de factura contiene datos no válidos que se produzca un error durante el procesamiento, como se describe anteriormente en este tema. Éste es un enfoque que puede seguir:  
  
1.  Asignar la responsabilidad de la aplicación de informes financieros recientemente implementada basada en Microsoft BizTalk a un desarrollador en su equipo.  
  
2.  Llega un mensaje de error ESB nuevo en el Portal de administración de ESB; el mensaje indica un problema de integridad de datos en una orquestación en la aplicación de BizTalk de informes financieros.  
  
3.  El administrador u operador notifica al desarrollador de la nueva excepción o el desarrollador registra para recibir notificaciones automáticas cuando se produce una excepción. Esta notificación puede producirse por uno de los siguientes motivos:  
  
    -   Puede producirse porque la excepción supera un umbral predefinido en basado en eventos actividad supervisión económica (BAM).  
  
    -   Puede producirse porque existe una suscripción de BizTalk para la aplicación específica, el servicio, el ámbito y el código de error que reenvía la excepción para el desarrollador.  
  
4.  El desarrollador examina el mensaje de error, los mensajes de orquestaciones individuales y sus valores de propiedad de contexto persistente. Los programadores pueden ver esta información a través del Portal de administración de ESB o mediante Microsoft Outlook a través de una suscripción de BizTalk.  
  
5.  El programador determina que se trata de un error común. Requiere intervención manual y la corrección por el equipo de finanzas, seguido de reenvío para el sistema.  
  
6.  El programador crea e implementa un proyecto de orquestación de BizTalk independiente que se suscribe a un tipo específico de aplicación y la excepción.  
  
7.  El proyecto de orquestación recupera el mensaje no válido desde el mensaje de error ESB, envía el mensaje al equipo de finanzas para su corrección, correlaciona el mensaje a la orquestación corregido y lo reenvía.  
  
8.  Una semana más adelante, el desarrollador navega al Portal de administración de ESB para descubrir que las tendencias de la excepción de aplicación para mensajes no válidos han disminuido considerablemente desde que se implementó esta solución.