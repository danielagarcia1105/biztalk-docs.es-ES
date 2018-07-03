---
title: BtarnClean | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BtarnClean utility
- assemblies, undeploying
- BTARN, deleting artifacts
- orchestrations, unenlisting
- ports, stopping
- orchestrations, stopping
- ports, deleting
- BTARN, BtarnClean utility
ms.assetid: fbecbb88-9b18-4b4b-a286-0bfa783f2320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f94c69552a59cf8cae8a12e056502ae405638e69
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992845"
---
# <a name="btarnclean"></a>BtarnClean
Use la utilidad BtarnClean para limpiar Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] artefactos desactivado de un equipo. Esto incluye las acciones siguientes:  
  
- Detener y dar de baja todas las [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] orquestaciones  
  
- Detener y eliminar todos los puertos asociados  
  
- Anular la implementación de todas las DLL. Ensamblados Solutions.btarn  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>archivos \Program (x86) \ Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK  
  
## <a name="running-btarnclean"></a>Ejecutar BtarnClean  
  
#### <a name="to-run-btarnclean"></a>Para ejecutar BtarnClean  
  
1.  Abra un símbolo del sistema.  
  
2.  Mover a \< *unidad*\>\ archivos de programa (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.  
  
3.  En el símbolo del sistema, escriba **BtarnClean**y presione ENTRAR.  
  
     La utilidad le pedirá que confirme que desea continuar.  
  
## <a name="remarks"></a>Notas  
 Si ejecuta la utilidad BtarnClean en un equipo que tiene un artefacto de BizTalk que depende de otros artefactos, BtarnClean indicará que no puede quitar el artefacto. La utilidad dejar dicho artefacto en su lugar y continuará para quitar otros artefactos. Puede quitar las dependencias y, a continuación, volver a ejecutar la utilidad.  
  
 Si ejecuta la utilidad BtarnClean en un equipo que forma parte de una implementación de varios equipos, el resto de los servidores de dicha implementación se verá afectado cuando se quiten los artefactos.  
  
 Si ejecuta la utilidad BtarnClean cuando existen varios procesos creados por los desarrolladores, la utilidad no quitará los procesos que estén en uso.  
  
 La utilidad BtarnClean no quitará una ubicación de recepción primaria si el artefacto de un usuario usa dicha ubicación de recepción. Si este es el caso, debe eliminar el puerto de recepción.  
  
 Si desea quitar la configuración de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] después de ejecutar la utilidad, ejecute Configuration.exe /u desde la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] carpeta.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
