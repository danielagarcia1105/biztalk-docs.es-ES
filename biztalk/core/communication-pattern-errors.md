---
title: Errores de patrón de comunicación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef9f7f4419d6c95b9b11343f395ab8e3d17c7c34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021087"
---
# <a name="communication-pattern-errors"></a>Errores de patrón de comunicación
Información para diagnosticar y resolver errores de patrón de comunicación de WCF.  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a>No se admiten los mensajes de error en los puertos unidireccionales
  
|                 |                                                       Detalles del error                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| Versión del producto |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    Identificador del evento     |                                                             0                                                             |
|  Origen del evento   |                                                             0                                                             |
|    Componente    |                                                             0                                                             |
|  Nombre simbólico  |                                                             0                                                             |
|  Texto del mensaje   | No se admiten los mensajes de error en los puertos unidireccionales. Corrija la descripción del servicio "{0}"tipo de puerto"{1}" y vuelva a ejecutar el Asistente |
  
## <a name="explanation"></a>Explicación  
 Este error indica que el servicio que se está intentando consumir es un servicio unidireccional y que tiene un error especificado.  
  
## <a name="user-action"></a>Acción del usuario  
 Corrija el servicio al cambiar el patrón de comunicación de unidireccional a solicitud-respuesta. O bien, quite el error del código.
 
 