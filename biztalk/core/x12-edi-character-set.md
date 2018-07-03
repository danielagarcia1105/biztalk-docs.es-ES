---
title: X12 juego de caracteres EDI | Microsoft Docs
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
ms.openlocfilehash: 9bd501c81b92f4fa7824009a949fd6c7e58eaf3b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023106"
---
# <a name="x12-edi-character-set"></a>Juego de caracteres X12 de EDI
Al usar el carácter Ñ o un acento grave (`), especifique lo siguiente:  


|                                                                   |                                  Juego de caracteres                                   |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------|
|             Solo el carácter Ñ en el documento EDI              |                            Usar el juego de caracteres ampliado                            |
|           Solo un acento grave (\`) en el documento EDI            |                              Usar el juego de caracteres UTF8                              |
| El carácter Ñ **y** un acento grave (\`) en el mismo documento: | -El documento de entrada debe tener codificación UTF8<br />-Use el juego de caracteres UTF8 |

 Los siguientes vínculos proporcionan más información sobre los juegos de caracteres EDI:  

 [Juegos de caracteres de EDI](http://go.microsoft.com/fwlink/p/?LinkId=271249)  

 [Compatibilidad de juegos de caracteres de EDI](http://go.microsoft.com/fwlink/p/?LinkId=271250)