---
title: Cómo se controlan las excepciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 004e4f29bcfc292edb33bae816a52b588a89771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246668"
---
# <a name="how-exceptions-are-handled"></a>Cómo se controlan las excepciones
Cuando se produce una excepción dentro de un ámbito, cada subproceso lógico de ejecución de éste se detiene. El motor de tiempo de ejecución intenta encontrar un controlador de excepción para la correspondiente excepción.  
  
 Si se encuentra uno que coincida con el tipo específico o uno con sus tipos base, el control se transfiere a ese controlador y se ejecuta su código.  
  
> [!NOTE]
>  El tipo de excepción debe derivarse de **System.Exception**.  
  
 Los controladores de excepción son secuenciales; esto significa que se comprobarán en cada excepción concreta para ver si pueden controlarla. Para que funcionen correctamente, los controladores de excepción deben colocarse de modo que aquellos que controlen más tipos específicos aparezcan en primer lugar seguidos de los que controlan tipos más generales. De este modo, se asegura que una excepción de un tipo específico recibe el control por parte del controlador adecuado y no de uno diseñado para controlar un tipo base.  
  
 Si el controlador de excepción se completa con normalidad, el control se transfiere al ámbito circundante. Si no se ha producido una excepción en el ámbito circundante, la orquestación continúa su ejecución. Si el controlador de excepción finaliza con una instrucción de inicio, se vuelve a iniciar la excepción original para el ámbito circundante para actuar sobre ella, a menos que especifique una excepción diferente que desea que se inicie.  
  
 Si no se consigue localizar ningún controlador de excepción, se ejecutará el controlador de excepción predeterminado. El controlador de excepción predeterminado de un ámbito llamará a las compensaciones de las transacciones anidadas y, a continuación, volverá a iniciar la excepción. Si escribe su propio controlador de excepción, puede decidir que la excepción no se propague.  
  
## <a name="see-also"></a>Vea también  
 [Excepciones](../core/exceptions.md)