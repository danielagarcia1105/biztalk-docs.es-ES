---
title: Nodos actividad y ActivityID | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbe92c28a3ca84cdd94236c1069c9d340cc4630f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983565"
---
# <a name="activity-and-activityid-nodes"></a>Nodos Actividad y ActivityID
Los nodos Actividad y ActivityID se utilizan para contener e identificar una definición de actividad. El nodo Actividad es la carpeta principal de los elementos en la definición de actividad. Todos los nodos de elementos de datos y eventos empresariales se subordinan al nodo de actividad asociado, y están contenidos en éste. El nombre del nodo Actividad debería reflejar el nombre de la propia actividad.  
  
 El nodo ActivityID es un elemento que se genera automáticamente en la definición de actividad y está destinado a contener un identificador único para la actividad. El nodo ActivityID se puede utilizar para realizar el seguimiento de identificadores proporcionados por usuarios o identificadores que genera el sistema. Por ejemplo, en un escenario en el que tiene un número de pedido como identificador único de todos los pedidos en el sistema, lo puede utilizar como ActivityID, en cuyo caso se asignará el valor de ActivityID desde algún origen de eventos, como el campo de número de pedido en el esquema de pedidos. Por otra parte, si el valor de pedido no es único, se puede dejar el nodo sin asignar y BAM generará automáticamente identificadores únicos en tiempo de ejecución.  
  
 Las actividades se pueden relacionar con otras actividades. En algunos casos, estas relaciones son parte explícita del modelo de observación.  En concreto, cuando cualquier vista de usuario incluye dos o más actividades, hay una relación automática entre esas actividades.  Cuando existe tal relación, un nodo de relación se crea automáticamente en el árbol de actividad del nodo Actividad para cada actividad homóloga conocida. En los escenarios en los que hay una relación de datos pero no existe ninguna vista de distribución, puede agregar un nodo de relación a un árbol de actividad de forma manual.  
  
 En cualquier caso, el objetivo del nodo de relación es proporcionar un identificador para la actividad relacionada. Por ejemplo, los envíos y pedidos pueden tener una relación de varios a varios (varios envíos cumplimentan un pedido, un envío puede llevar un producto que satisfaga muchos pedidos).  El registro de actividad de cada pedido puede tener varios punteros a envíos relacionados y cada registro de actividad de envío podría apuntar a uno o más pedidos.  En cuanto a la base de datos, el valor del nodo de relación es la clave externa en la tabla para la otra actividad.  
  
## <a name="working-with-activity-id-nodes"></a>Trabajar con nodos de Id. de actividad  
 Por ejemplo, considere el siguiente escenario: la orquestación EquityLoan contiene la carpeta de actividad LoanProcess. Hace referencia a eventos empresariales, incluido el siguiente:  
  
- LoanApplicationReceived                     
  
- CHRequest  
  
- CHResponse  
  
- AppraisalRequest  
  
- AppraisalResponse  
  
- Aprobada  
  
- Denegado  
  
  El nodo ActivityID permite que el programador de soluciones pueda extraer datos que identifican únicamente a la actividad, como el número de pedido o, en el caso del ejemplo anterior, el campo Nº de SS del mensaje. Si no arrastra ningún dato al nodo ActivityID, un GUID generado automáticamente identifica las actividades empresariales.  
  
  Para definir la relación entre hitos o eventos empresariales en orquestaciones diferentes, la orquestación de destino debe hacer referencia al ActivityID. Para obtener más información acerca de cómo implementar relaciones mediante TPE, consulte [nodos de relación](../core/relationship-nodes.md).  
  
## <a name="see-also"></a>Vea también  
 [Nodos Vista de actividad de TPE](../core/tpe-activity-view-nodes.md)