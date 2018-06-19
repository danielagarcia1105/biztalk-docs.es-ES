---
title: Opciones de configuración de confirmación | Documentos de Microsoft
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
ms.openlocfilehash: 93dea42fd084f22b4644f0acbb21860d69f75027
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204412"
---
# <a name="ack-configuration-settings"></a>Opciones de configuración de confirmación
El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] analizador genera las confirmaciones en función de la configuración de administración de socios comerciales (TPM). La configuración de confirmación (ACK) es dependiente de la información de socios comerciales. No se utiliza el tipo de esquema. Cuando [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] recibe un mensaje de confirmación con el campo MSH15 AL, SU o ER, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] puede enviar una confirmación para este mensaje en función del resultado de analizar el encabezado de confirmación y la configuración de TPM. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Recupera la configuración de confirmación asociado y devuelve uno de los cinco valores siguientes:  
  
> [!NOTE]
>  La especificación de HL7 exige que utiliza elementos 1 a 4 y para rellenar el campo MSH15 de un mensaje de confirmación que genera. Elemento 5 es [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-específico y denota no para generar una confirmación.  
  
1.  AL – siempre  
  
2.  NE: nunca  
  
3.  SU: correcto  
  
4.  ER: Error  
  
5.  NO – no generan una confirmación  
  
## <a name="ack-configuration-inconsistency"></a>Incoherencia de configuración de confirmación  
 En el caso de incoherencia entre los valores dentro de la instancia de mensaje MSH15 y MSH16 campos y la configuración de la interfaz de usuario de confirmación configuración [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] envía una confirmación cuando uno de los dos desencadenadores de generación de confirmación lo requieren. En el caso de otras incoherencias, los datos de la instancia sobrescribirá la configuración en la interfaz de usuario de configuración.  
  
## <a name="see-also"></a>Vea también  
 [Configurar confirmaciones de mensajes](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)   
 [Creación y procesamiento de confirmaciones](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)