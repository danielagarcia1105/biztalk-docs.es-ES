---
title: SWIFT remolque | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT Trailer schema
- schemas, SWIFT
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: b6d64584-0514-4c87-98c0-33755efc4695
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc3155ac21f55e7c61483b9287429f9b722f6a84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214500"
---
# <a name="swift-trailers"></a>Finalizadores SWIFT
Cada mensaje SWIFT tiene uno o más finalizadores según sea necesario por los requisitos de exchange y la seguridad del mensaje. Finalizadores de sistema, si procede, siguen los finalizadores de usuario. Cada finalizador dentro del bloque de finalizador aparece dentro de un subbloques delimitados por más pares de paréntesis. Cada subbloques comienza con tres letras que indica el tipo de finalizador, seguido de dos puntos.  
  
 El esquema de finalizador de SWIFT (SWIFT Trailer.xsd) contiene el formato para lo siguiente:  
  
-   El delimitador final del bloque de texto  
  
-   Finalizadores de usuario (información de usuario y del sistema)  
  
-   Finalizadores de sistema  
  
 El delimitador final del bloque de texto es "-"}. El bloque de finalizador comienza con "{5:". El contenido del bloque de finalizador incluye información de usuario (suma de comprobación, autenticación de mensajes, autenticación propietario etc.) y de información del sistema (mensajes retrasada, referencia de mensajes, mensajes duplicados posibles y así sucesivamente). Finalizadores agregadas por SWIFT también proporcionan un bloque terceros, delimitado por "{S:". El *manual de usuario de SWIFT*, tema "Descripción del servicio FINÉS", se describe detalladamente el contenido del bloque 5. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]no valida el contenido del bloque S.  
  
 La interfaz FIN real o la red SWIFT anexa los finalizadores. Si un mensaje contiene un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] lleva el finalizador con el mensaje. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]no se genera un error si un mensaje no contenía un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje. Como con encabezados, todas las entradas de finalizador, incluidos los bloques de por sí mismos, son opcionales en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  
  
 Esta sección contiene:  
  
-   [Finalizadores de usuario](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
-   [Finalizadores de sistema](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)