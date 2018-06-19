---
title: Administrar artefactos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ccca48682f009a24f538015b055c45dd79a9587
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262260"
---
# <a name="managing-artifacts"></a>Administrar artefactos
En esta sección se describe cómo administrar artefactos; se incluye una explicación de cómo agregarlos a una aplicación de BizTalk y de cómo quitarlos de ella, además del modo de configurar sus propiedades.  
  
 Los artefactos son los elementos contenidos en una aplicación de BizTalk y que resultan necesarios para que ésta se ejecute. Para obtener información general sobre cómo se utilizan los artefactos en una aplicación de BizTalk, consulte [¿qué es una aplicación de BizTalk?](../core/what-is-a-biztalk-application.md) Para obtener información general sobre los artefactos, vea [arquitectura en tiempo de ejecución](../core/runtime-architecture.md). Para obtener información acerca de cómo manipular artefactos al crear y modificar una aplicación de BizTalk, consulte [crear y modificar las aplicaciones de BizTalk](../core/creating-and-modifying-biztalk-applications.md).  

## <a name="tracking-artifacts"></a>Artefactos de seguimiento
Está realizando el seguimiento de una parte importante de la administración de los artefactos que se crea. La consola de administración de BizTalk Server permite configurar diversas opciones de seguimiento durante el tiempo de ejecución para orquestaciones, puertos de envío, puertos de recepción y canalizaciones. Se pueden cambiar las opciones de seguimiento de un elemento en cualquier momento, sin necesidad de interrumpir el proceso empresarial.

Las opciones de configuración del seguimiento permiten realizar el seguimiento de los siguientes tipos de datos:

- Datos de eventos de entrada o de salida. Por ejemplo, Id. del mensaje, horas de inicio y detención del artefacto.

- Propiedades de mensajes de entrada o de salida. Por ejemplo, propiedades generales y promocionadas de cada mensaje que procesa el artefacto.

- Cuerpos y partes de mensajes de entrada o de salida. Por ejemplo, el cuerpo y las partes de cada mensaje que procesa el artefacto.

- Orquestaciones. Datos de ejecución correspondientes a formas de orquestación.

[Ver datos de instancia y realiza el seguimiento de mensaje](../core/viewing-tracked-message-and-instance-data.md) proporciona alguna información válida. 


> [!TIP]
> Si establece opciones de seguimiento en una canalización, las opciones de seguimiento se establecen globalmente para todos los puertos que usa la canalización. Esto hace mucho más datos de seguimiento que tenga la intención y puede afectar al rendimiento del sistema. Durante el desarrollo, esto puede ser normal. En escenarios de producción, se recomienda habilitar las opciones de seguimiento en los puertos de envío y puertos, en lugar de las canalizaciones de recepción.
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Administrar orquestaciones](../core/managing-orchestrations.md)  
  
-   [Administrar vínculos de rol](../core/managing-role-links.md)  
  
-   [Administrar puertos de envío y grupos de puertos de envío](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [Administrar puertos de recepción](../core/managing-receive-ports.md)  
  
-   [Administrar ubicaciones de recepción](../core/managing-receive-locations.md)  
  
-   [Administración de directivas](../core/managing-policies.md)  
  
-   [Administrar esquemas](../core/managing-schemas.md)  
  
-   [Administración de mapas](../core/managing-maps.md)  
  
-   [Administrar canalizaciones](../core/managing-pipelines.md)  
  
-   [Administración de recursos](../core/managing-resources.md)