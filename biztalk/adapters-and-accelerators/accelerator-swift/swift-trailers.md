---
title: Finalizadores SWIFT | Microsoft Docs
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
ms.openlocfilehash: 1457c05b37c3f5b1dfcc5887c1a3f6ce27fcb0d4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004845"
---
# <a name="swift-trailers"></a>Finalizadores SWIFT
Cada mensaje SWIFT tiene uno o más finalizadores según sea necesario por los requisitos de exchange y la seguridad de mensaje. Finalizadores del sistema, si procede, siguen los finalizadores de usuario. Cada finalizador dentro del bloque de finalizador aparece dentro de un subblock delimitado por más pares de llaves. Cada subblock comienza con tres letras que indica el tipo de finalizador, seguido de dos puntos.  
  
 El esquema de finalizador de SWIFT (SWIFT Trailer.xsd) contiene el formato siguiente:  
  
- El delimitador final del bloque de texto  
  
- Finalizadores de usuario (información de usuario y del sistema)  
  
- Finalizadores del sistema  
  
  El delimitador final del bloque de texto es "-"}. El bloque de finalizador comienza con "{5:". El contenido del bloque de finalizador incluye información de usuario (suma de comprobación, la autenticación de mensajes, autenticación etc.) e información del sistema (mensaje demorado, referencia de mensajes, mensajes duplicados posibles y así sucesivamente). Finalizadores SWIFT agregados también proporcionan un tercer bloque, delimitado por "{S:". El *manual del usuario de SWIFT*, "Descripción del servicio FIN", se describe detalladamente el contenido del bloque 5. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no valida el contenido del bloque S.  
  
  La interfaz FIN real o la red SWIFT anexa los finalizadores. Si un mensaje contiene un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] lleva a cabo el finalizador con el mensaje. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] no se genera un error si un mensaje no contiene un finalizador cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] recibe el mensaje. Como sucede con los encabezados, todas las entradas de finalizador, incluidos los bloques de por sí mismos, son opcionales en [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].  
  
  Esta sección contiene:  
  
- [Finalizadores de usuario](../../adapters-and-accelerators/accelerator-swift/user-trailers.md)  
  
- [Finalizadores del sistema](../../adapters-and-accelerators/accelerator-swift/system-trailers.md)  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con esquemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)