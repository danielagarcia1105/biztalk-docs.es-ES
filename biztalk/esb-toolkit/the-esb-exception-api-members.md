---
title: Los miembros de la API de excepción de ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a095549-7e5d-4a7c-96d2-8fc6ca3efd63
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e267f8533948fc46c4604ebfffb6d22367a321e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295588"
---
# <a name="the-esb-exception-api-members"></a>Los miembros de la API de excepción de ESB
El **ESB. ExceptionHandling** ensamblado expone métodos públicos para crear mensajes de error y para administrar y recuperarlos para el procesamiento, como se describe en la tabla siguiente.  
  
|Caso de uso y de miembro|Description|  
|-------------------------|-----------------|  
|**CreateFaultMessage** [ámbito del controlador de excepción]|**pública estática XLANGMessage CreateFaultMessage()** no toma ningún parámetro. Devuelve una instancia del mensaje de error ESB como un **XLANGMessage** instancia rellenado con el nombre de orquestación actual, Id. de instancia de orquestación (GUID), **System.Exception** instancia y otra propiedades de ambiente. **Nota:** necesita esta interfaz de programación de aplicaciones (API) que se llame solo desde un bloque de excepción dentro de la XLANG.|  
|**AddMessage** [ámbito del controlador de excepción]|**AddMessage public static void (faultMessage, existingMessage)** toma como parámetros dos **XLANGMessage** instancias; el primero es un mensaje de error ESB recién creada y la segunda es cualquier instancia de mensaje existente en el orquestación. El método conserva la instancia de mensaje existente y sus propiedades de contexto de mensaje en el mensaje de error y hace que esté disponible para el uso de la recuperación del **GetMessage** método. Sin valor devuelto.|  
|**SetException** [ámbito del controlador de excepción]|**pública SetException static void (faultMessage, exception)** toma como parámetros de un mensaje de error ESB como un **XLANGMessage** instancia y **excepción** como un **objeto**  instancia. El método continúa la excepción en el mensaje de error existente y hace que esté disponible para el uso de la recuperación del **GetException** método. Sin valor devuelto.|  
|**GetMessage** [suscriptor/procesador]|**pública XLANGMessage GetMessage(faultMessage, messageName) estático** toma como parámetros un ESB error mensaje recibido de una suscripción como un **XLANGMessage** instancia y el (**cadena**) nombre del mensaje que se agregó anteriormente al mensaje de error (en el controlador de excepciones de la forma orquestación de origen). Devuelve un **XLANGMessage** instancia que coincida con el nombre del mensaje y que contiene todas las original propiedades de contexto, incluidas las propiedades promocionadas personalizadas.|  
|**GetMessages** [suscriptor/procesador]|**pública MessageCollection GetMessages(faultMessage) estático** toma como parámetro único recibe un mensaje de error ESB de una suscripción como un **XLANGMessage** instancia. Devuelve un **MessageCollection** instancia rellenado con todos los **XLANGMessage** instancias agregados previamente al mensaje de error (en el controlador de excepciones de la forma orquestación de origen). Cada **XLANGMessage** instancia contiene todos las original propiedades de contexto, incluidas las propiedades promocionadas personalizadas.|  
|**GetException** [suscriptor/procesador]|**System.Exception GetException(faultMessage) estática pública** toma como parámetro único recibió un mensaje de error de una suscripción como un **XLANGMessage** instancia. Devuelve el **System.Exception** objeto agregado previamente al mensaje de error (en el controlador de excepciones de la forma orquestación de origen).|  
|**FaultSeverity** [/ procesador de suscriptor y ámbito del controlador de excepción]|Propiedad de lectura y escritura públicas del mensaje de error ESB **XLANGMessage** clase que expone la gravedad de un mensaje de error. Un valor de la **códigos de error** enumeración: **información** (0), **advertencia** (1), **Error** (2), **grave**(3), o **crítico** (4).|  
|**MessageCollection** [suscriptor/procesador]|Una colección de los mensajes devueltos por la **GetMessages** método. Esta clase se deriva de **ArrayList** e implementa un enumerador para permitir la iteración usando el **MoveNext** método.|