---
title: "Mecanismo de enrutamiento de orquestación excepciones de error de ESB | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa05f44b-7fb2-48fd-886d-c6d179904e6d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afda61ea19587b327f0fe773b150eeb8f88a4f7a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-failed-orchestration-exception-routing-mechanism"></a>Error de ESB mecanismo de enrutamiento de excepciones de orquestación
El mecanismo de excepción enrutamiento de orquestación de error de ESB proporciona las siguientes características:  
  
-   **Crear mensajes de error que capturar propiedades de ambiente.** El **CreateFaultMessage** método genera un mensaje de error que contiene la orquestación nombre del servicio y el Id. de instancia de servicio, la forma de orquestación está activada, el nombre de la aplicación a la que está la orquestación implementa, el nombre del servidor de procesamiento de la orquestación y la fecha de la excepción y la hora (en formato UTC). Agrega también implícitamente actual **System.Exception** objeto generado en el controlador de excepciones de la forma de orquestación actual.  
  
-   **Agregar mensajes de orquestación existente a un mensaje de error**. El **AddMessage** método conserva la configuración de XLANG del mensaje de orquestación y todas las propiedades de contexto de mensaje en el mensaje de error.  
  
-   **Agregar explícitamente un objeto de excepción existente a un mensaje de error**. El **SetFaultMsgException** método serializa el objeto como un **System.Exception** y conserva en el mensaje de error.  
  
-   **Recuperar una colección de mensajes sin tipo enumerada desde un mensaje de error recibido por un suscriptor**. El **GetMessages** método recupera todos los mensajes almacenados desde la orquestación errores como mensajes XLANG. Devuelve todas las propiedades de contexto original de cada mensaje almacenado en cada mensaje XLANG.  
  
-   **Recuperar un mensaje de orquestación XLANG fuertemente tipado de un mensaje de error recibido por un suscriptor**. El **GetMessage** método recupera un mensaje persistente de un tipo específico desde el mensaje de error como un mensaje XLANG. Devuelve todas las propiedades de contexto original del mensaje almacenado en el mensaje XLANG. También admite la recuperación de la **System.Exception** objeto generado por la orquestación error y recupera un persistente **System.Exception** objeto desde el mensaje de error.