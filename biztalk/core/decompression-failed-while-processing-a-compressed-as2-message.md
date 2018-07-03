---
title: Error de descompresión al procesar un mensaje AS2 comprimido. | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c77bead00b97bf6fa072223485f2d1cc422053b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001893"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a>Error de descompresión al procesar un mensaje AS2 comprimido.
## <a name="details"></a>Detalles  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  Nombre del producto   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| Versión del producto |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    Identificador del evento     |                                           -                                            |
|  Origen del evento   | EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
|    Componente    |                                       Motor AS2                                       |
|  Nombre simbólico  |                                           -                                            |
|  Texto del mensaje   |       Error de descompresión al procesar un mensaje AS2 comprimido. Error: {0}       |
  
## <a name="explanation"></a>Explicación  
 Este evento de error,  indica que la canalización de recepción o el componente de descodificador AS2 no pudo descomprimir el mensaje AS2.  
  
## <a name="user-action"></a>Acción del usuario  
 Para resolver este error, realice una de las siguientes acciones:  
  
-   Compruebe que el contenedor de compresión del mensaje AS2 es válido.  
  
-   Compruebe que la descompresión está habilitada para BizTalk Server. Para ello, compruebe que la propiedad "Debe comprimirse el mensaje" está activada en la página Entidad como remitente del mensaje AS2 del cuadro de diálogo Propiedades de AS2 (si está activada la propiedad Invalidar propiedades de mensajes entrantes).  
  
-   Use la descripción del error proporcionada en el texto del mensaje de error para identificar el problema específico.