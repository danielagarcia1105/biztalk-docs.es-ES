---
title: El segmento debe tener un nombre con caracteres de al menos dos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f80bbc4a-151a-4094-8640-1944e8812730
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: def67be8b1c146bd6da37b669a71f2be15e22e2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985965"
---
# <a name="segment-should-have-a-name-with-at-least-two-characters"></a>El segmento debe tener un nombre con dos caracteres como mínimo
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                             SchemaCode103EInvalidTagLength                             |
|  Texto del mensaje   |                 El segmento debe tener un nombre con 2 caracteres como mínimo.                  |
  
## <a name="explanation"></a>Explicación  
 Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar el intercambio entrante porque el nombre de un segmento del intercambio no tiene al menos dos caracteres.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, pida al remitente del intercambio que se asegure de que el nombre de cada segmento del intercambio tenga al menos dos caracteres y vuelva a enviar el intercambio.