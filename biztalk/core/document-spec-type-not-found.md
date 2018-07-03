---
title: No se encuentra el tipo de especificación de documento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb2a458-d0f4-420d-8d35-0e739167464f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b8bffb132921e7b939f251db21e0c6c7839dc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014229"
---
# <a name="document-spec-type-not-found"></a>No se ha encontrado el tipo de especificación de documento
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor EDI                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |                            El tipo de especificación de documento {0} no encontrado                            |
  
## <a name="explanation"></a>Explicación  
 Este error indica que no se encuentra el esquema.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, implemente el esquema del documento:  
  
1.  Iniciar **Microsoft Visual Studio**.  
  
2.  Cree o abra un proyecto existente.  
  
3.  Agregue el esquema al proyecto.  
  
4.  Implemente el proyecto en Visual Studio.