---
title: Esquema no válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 063c60ed07d89429f14f7ed3b7c090cdc0bac033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008165"
---
# <a name="invalid-scheme"></a>Esquema no válido
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                  Esquema no válido. se esperaba el esquema "{0}"o"{1}"                   |
  
## <a name="explanation"></a>Explicación  
 Se ha producido una de las situaciones siguientes: la dirección que se especifica en el campo URI (identificador uniforme de recursos) debe comenzar con http:// o https://. O bien, el esquema no coincide con lo especificado en la implementación del elemento de enlace de transporte.  
  
## <a name="user-action"></a>Acción del usuario  
 Escriba un URI de dirección de proxy válido que empiece por http:// o https://