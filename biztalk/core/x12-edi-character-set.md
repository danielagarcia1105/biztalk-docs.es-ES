---
title: X12 juego de caracteres EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76e7b327-b0bd-4f16-8bfe-6c0184059f2b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46bcf25317d38846c6376b1fa25572b926c92992
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289036"
---
# <a name="x12-edi-character-set"></a>Juego de caracteres X12 de EDI
Al usar el carácter Ñ o un acento grave (`), especifique lo siguiente:  
  
||Juego de caracteres|  
|-|-------------------|  
|Solo el carácter Ñ en el documento EDI|Usar el juego de caracteres ampliado|  
|Solo el acento grave (`) en el documento EDI|Usar el juego de caracteres UTF8|  
|El carácter Ñ **y** un acento grave (') en el mismo documento:|-El documento de entrada debe tener codificación UTF8<br />-Use el juego de caracteres UTF8|  
  
 Los siguientes vínculos proporcionan más información sobre los juegos de caracteres EDI:  
  
 [Juegos de caracteres EDI](http://go.microsoft.com/fwlink/p/?LinkId=271249)  
  
 [Compatibilidad con juego de caracteres de EDI](http://go.microsoft.com/fwlink/p/?LinkId=271250)