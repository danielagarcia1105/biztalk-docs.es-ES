---
title: "Control de flujos de datos entrantes en componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fc34da3a5c8e65f81cd6bbbb699f52506cdc6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a>Controlar secuencias de datos entrantes en componentes de canalización
Las siguientes consideraciones se deben tener en cuenta cuando se escribe un código de desensamblador personalizado para los componentes de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a>No cerrar la secuencia de datos entrantes del código desensamblador personalizado  
 Cuando escriba un código de desensamblador personalizado para los componentes de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de no cerrar la secuencia de datos entrantes correspondiente. La secuencia entrante de mensaje de entrada es un recurso compartido. La secuencia entrante también la usa el componente de seguimiento de cuerpos de mensaje en el motor de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
 Si cierra implícita o explícitamente la secuencia entrante, se pueden perder los datos de seguimiento y no podrá examinar los datos de la secuencia mediante el seguimiento de eventos de mensaje e instancias de servicio en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a>Utilizar el método Seek de la clase Stream para establecer el puntero de la secuencia de datos en el inicio de la secuencia  
 Asegúrese de leer desde la secuencia de datos entrantes hasta que se alcance el final de la secuencia. Por ejemplo, si el código personalizado solicita una lectura de 300 KB de datos y el código sólo recibe 34 KB, no suponga que se ha alcanzado el final de la secuencia. El código personalizado siempre debería leer desde la secuencia entrante hasta que se devuelvan 0 bytes.  
  
 Antes de devolver la secuencia de datos en la lógica de componentes personalizada, vuelva a establecer el puntero de la secuencia de datos al principio de la secuencia. Por ejemplo, este código muestra la lógica para utilizar el método seek para señalar el principio de la secuencia antes de devolver la secuencia:  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 Si no lo realiza y la secuencia se le desde el final del componente actual, el componente siguiente recibe lo que parece ser una secuencia vacía porque el puntero de la secuencia de datos no está establecido al principio de la secuencia. Se puede generar un error inesperado en los componentes de canalización posteriores al analizar y validar.