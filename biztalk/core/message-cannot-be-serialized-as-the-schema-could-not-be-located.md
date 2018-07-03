---
title: No se puede serializar el mensaje ya no se pudo encontrar el esquema | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37897c04-650d-4695-846d-b8ba61365647
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f366fc619ac070d618345ce6bde9996710b1242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988189"
---
# <a name="message-cannot-be-serialized-as-the-schema-could-not-be-located"></a>No se puede serializar el mensaje ya que el esquema no ha podido localizarse
## <a name="details"></a>Detalles  
  
|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  Nombre del producto   |                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                            |
| Versión del producto |                                        [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                        |
|    Identificador del evento     |                                                                    -                                                                     |
|  Origen del evento   |                          EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
|    Componente    |                                                                Motor EDI                                                                |
|  Nombre simbólico  |                                              MessageSerializationFailureDueToMissingSchema                                               |
|  Texto del mensaje   | No se puede serializar el mensaje como el esquema {0} no se pudo encontrar. El esquema no está implementado o se han implementado varias copias. |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de envío no pudo serializar el intercambio saliente porque la canalización no pudo determinar el esquema que debía usar para serializar el intercambio. El esquema no está implementado o se han implementado varias copias del esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
1.  Si no se ha implementado el esquema asociado con un intercambio, abra Visual Studio, agregue el esquema a un proyecto de BizTalk y genere e implemente el proyecto.  
  
2.  Si se ha implementado más de una copia del esquema, abra Visual Studio y anule la implementación de todas las copias del esquema asociadas con el intercambio menos una.