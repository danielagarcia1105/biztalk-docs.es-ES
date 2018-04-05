---
title: 'Error: demasiadas entradas de datos en el nodo | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyDataInputsToNode
ms.assetid: 176805f0-2d6d-4072-b866-132b98c7e4b5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9e465f861c4048708f41ea86f04ffd52375dec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-data-inputs-to-node"></a>Error: demasiadas entradas de datos en el nodo
**Código de error**  
  
 btm1005  
  
 **Explicación**  
  
 Hay un mayor número de vínculos conectados al nodo indicado en el esquema de destino que el número de vínculos de entrada a la **bucle** functoid que esté conectado al nodo antecesor del nodo indicado. El número de vínculos, tanto del primer tipo como del segundo, debe coincidir.  
  
 **Acción del usuario**  
  
 Repetición del trabajo el número de vínculos conectados al nodo indicado y a la **bucle** functoid conectado al nodo antecesor para que coincidan.