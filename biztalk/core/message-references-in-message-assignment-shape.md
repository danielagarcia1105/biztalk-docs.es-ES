---
title: Las referencias de la forma asignación de mensajes de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, code samples
- code samples, messages
- messages, objects
ms.assetid: 428f7eb8-001e-4147-b1c8-f9bb6f3a80f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834eefa991b6cad89a04a836f63d1b9af73fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262812"
---
# <a name="message-references-in-message-assignment-shape"></a>Referencias de mensaje en la forma asignación de mensajes
La primera vez que se asigna un objeto basado en .NET a un mensaje o a una parte de mensaje, ese mensaje contiene y mantiene una referencia al objeto.  
  
 Para la eficacia y la escalabilidad, el motor de orquestaciones no realiza una "copia en profundidad" del objeto: es decir, no copiar todo el contenido del objeto para el mensaje.  
  
 Posteriormente, si asigna el objeto a otro mensaje o a otra parte de mensaje, todas las modificaciones que haya realizado en el original también se realizarán en el segundo mensaje o segunda parte de mensaje. Debería evitar esta situación, ya que los resultados son impredecibles.  
  
 Si necesita que el segundo mensaje tenga una copia distinta del objeto, debería asignar el primer mensaje o primera parte de mensaje al segundo mensaje o segunda parte de mensaje.  
  
 Considere el ejemplo siguiente:  
  
 Erróneo:  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 En este caso, myMsg2.myInt se ha sobrescrito y ahora tiene el valor 5.  
  
 Correcto:  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 En este caso, myMsg2.myInt sigue teniendo el valor 100, como se esperaba.  
  
## <a name="see-also"></a>Vea también  
 [Construir mensajes](../core/constructing-messages.md)