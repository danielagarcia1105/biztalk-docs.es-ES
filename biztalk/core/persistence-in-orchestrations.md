---
title: Persistencia en orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, persistence
- persistence
- BizTalk Server Orchestration Engine
ms.assetid: 2f79d294-f7df-4d84-ba76-50618506b6c6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184b4a7dde452902f404a5d6ed5dca5ee611e1e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008917"
---
# <a name="persistence-in-orchestrations"></a>Persistencia en orquestaciones
El motor de orquestaciones guarda toda la información de estado de una instancia de orquestación en varios puntos de persistencia para permitir la rehidratación de la instancia de orquestación. El estado incluye los componentes basados en .NET que se pueden usar en la orquestación, así como los mensajes y variables. El motor almacena la información de estado en los siguientes puntos de persistencia:  
  
- Final de un ámbito transaccional (atómico o de larga ejecución).  
  
- En los puntos de interrupción de depuración.  
  
- En la ejecución de otras orquestaciones a través de la forma Iniciar orquestación.  
  
- En la forma Envío (excepto en una transacción atómica).  
  
- Cuando una instancia de orquestación se suspende.  
  
- Cuando se apaga el sistema de forma controlada.  
  
- Cuando el motor determina que quiere deshidratar.  
  
- Cuando una instancia de orquestación ha finalizado.  
  
  El motor optimiza el número de puntos de persistencia dado que son caros, en especial cuando se trata de mensajes de gran tamaño. Como se muestra en las dos instancias de orquestación a continuación, en la orquestación con las formas Envío en un ámbito atómico, el motor determina un único punto de persistencia entre el final del ámbito transaccional y el final de la orquestación. En la otra orquestación, habrá dos puntos de persistencia, uno para la primera forma Envío y el segundo para la forma Envío más el final de la orquestación.  
  
  **Persistencia de orquestación**  
  
  ![Persistencia de orquestación](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")  
  
  Los objetos basados en .NET que use en las orquestaciones, sea de forma directa o indirecta, deben estar marcados como serializables a menos que se invoquen en ámbitos atómicos o si los objetos no tienen información de estado y se invocan únicamente a través de métodos estáticos. **System.Xml.XmlDocument** es un caso especial y no deben marcarse como serializable con independencia de la propiedad de transacción para un ámbito.  
  
  ¿Cómo el control especial **System.Xml.XmlDocument** trabajar:  
  
  Cuando el usuario define una variable **X** typu **T**, donde **T** es **System.Xml.XmlDocument** o una clase derivada de  **System.Xml.XmlDocument** , a continuación, el compilador tratará **X** como un objeto serializable.  
  
  Al serializar **X**, el tiempo de ejecución mantendrá los siguientes fragmentos de información: (a) el tipo real **Tr** del objeto **X** hace referencia a (b) el  **OuterXml** cadena del documento.  
  
  Al deserializar **X**, el tiempo de ejecución creará una instancia de **Tr** (Esto supone un constructor que no tome ningún parámetro) y llamará a **LoadXml** que proporciona el instancia con el guardado **OuterXml.  X** , a continuación, se establecerá para que apunte a la instancia recién creada de **Tr**.  
  
## <a name="see-also"></a>Vea también  
 [Transacciones](../core/transactions.md)