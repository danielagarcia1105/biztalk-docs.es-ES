---
title: No se admite porque la información de codificación de UNB1.1 no coincide con la codificación real del juego de caracteres | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 085ea8e3-e0d8-45bd-9985-6787b00e4d5a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ef85488281c6ddd7fe8ecdb0f096a21bbc30c06
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978389"
---
# <a name="character-set-not-supported-because-the-encoding-information-in-unb11-does-not-match-the-actual-encoding"></a>Juego de caracteres no admitido porque la información de codificación de UNB1.1 no coincide con la codificación real del intercambio
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| Versión del producto |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                              |
|    Identificador del evento     |                                                                          -                                                                          |
|  Origen del evento   |                               EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                |
|    Componente    |                                                                     Motor EDI                                                                      |
|  Nombre simbólico  |                                                                          -                                                                          |
|  Texto del mensaje   | Juego de caracteres no admitido. Podría deberse a que la información de codificación de UNB1.1 no coincide con la codificación real del intercambio. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción EDI no pudo procesar el intercambio EDIFACT entrante porque los caracteres usados en el intercambio no se ajustaban al conjunto de caracteres identificados en el campo UNB1.1 del intercambio.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Cambie los caracteres usados en el intercambio de modo que se ajusten al conjunto de caracteres especificado en el campo UNB1.1 del intercambio.  
  
-   Cambie el conjunto de caracteres especificado en el campo UNB1.1 del intercambio de modo que todos los caracteres del intercambio formen parte del conjunto de caracteres.