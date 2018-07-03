---
title: Opciones de configuración de ACK | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06cedaee1ca0ad574920cfb646f69d63157c8e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968061"
---
# <a name="ack-configuration-settings"></a>Opciones de configuración de confirmación
Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] analizador genera las confirmaciones según la configuración de administración de socios comerciales (TPM). La configuración de confirmación (ACK) es dependiente de la información del partner. No se utiliza el tipo de esquema. Cuando [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe un mensaje de confirmación con el campo MSH15 AL, unidades de búsqueda o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede enviar una confirmación para este mensaje en función del resultado de analizar el encabezado de la confirmación y la configuración de TPM. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Recupera la configuración de confirmación asociado y devuelve uno de cinco los siguientes:  
  
> [!NOTE]
>  La especificación de HL7 exige que utilice elementos 1 a 4 y para rellenar el campo MSH15 de un mensaje de confirmación que genera. Es el elemento 5 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-específico y denota no para generar una confirmación.  
  
1.  AL – siempre  
  
2.  NE: nunca  
  
3.  Unidades de búsqueda: correcto  
  
4.  ER: Error  
  
5.  NO – no generan una confirmación  
  
## <a name="ack-configuration-inconsistency"></a>Incoherencia de configuración de confirmación  
 En el caso de una incoherencia entre los valores dentro de la instancia de mensaje MSH15 y MSH16 campos y la configuración de interfaz de usuario de configuración de ACK [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación cuando uno de los dos desencadenadores de generación de confirmación lo requieren. En el caso de otras incoherencias, los datos de la instancia invalidará la configuración en la interfaz de usuario de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de confirmaciones de mensajes](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)   
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)