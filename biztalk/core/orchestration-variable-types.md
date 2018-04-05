---
title: Tipos de variables de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, variables
ms.assetid: 34990be2-35b6-40ec-b107-42a1c7b45aca
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f388cf112a84d1e6ace00d3930cd6d815d728d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-variable-types"></a>Tipos de variables de orquestación
Puede declarar variables de los tipos predefinidos siguientes:  
  
|||||  
|-|-|-|-|  
|boolean|byte|char|datetime|  
|decimal|double|int16|int32|  
|int64|long|sbyte|sola|  
|string|timespan|uint16|uint32|  
|uint64||||  
  
 También puede declarar variables de algunos tipos basados en .NET a los que se hace referencia en su proyecto.  
  
## <a name="considerations-for-declare-orchestration-variables"></a>Consideraciones para declarar variables de orquestación  
 Cuando declare variables de orquestación, tenga en cuenta lo siguiente:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]propiedades de contexto con varios valores de es compatible con ciertos enrutamiento por contenidos escenarios, pero no pueden utilizar estas propiedades en las orquestaciones.  
  
-   Para que se admitan la suspensión y la rehidratación de las orquestaciones, todas las variables de orquestación deben ser almacenar su estado de forma persistente.  Normalmente, esto se consigue por el tipo o clase de la variable que sea serializable o que permita secuencias.  
  
-   Estos tipos basados en .NET (clases) deben ser clases serializables.  Pueden implementar esto al ser declarados con el atributo “[Serializable]” o al implementar de forma explícita la interfaz .NET ISerializable (en el espacio de nombres System.Runtime.Serialization).  
  
-   Si el tipo basado en .NET es realmente un contenedor al que se puede llamar en tiempo de ejecución (RCW) de un componente COM subyacente, ese componente debe implementar las interfaces necesarias para que el RCW sea una clase de .NET serializable (por ejemplo, IPersistStream, IPersistStreamInit).  
  
-   Debido a que los tipos basados en .NET (o de COM subyacente) se ejecutan dentro del flujo de una orquestación, los métodos de estos tipos no deben retrasar la ejecución de la orquestación (por ejemplo, a través de la contención de recursos, etc.).  Y todo uso que estas implementaciones de tipos hagan de los recursos afectará a la instancia de host en la que se ejecute la orquestación que llama.