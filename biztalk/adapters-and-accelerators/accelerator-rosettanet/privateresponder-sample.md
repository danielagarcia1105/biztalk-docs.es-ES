---
title: Ejemplo de PrivateResponder | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2e44157c1b7a4e545bad23c5d9b6dcd9fa87cfe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986871"
---
# <a name="privateresponder-sample"></a>Ejemplo de PrivateResponder
El ejemplo PrivateResponder.odx contiene el código para el proceso de Respondedor privado instalado por Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Este proceso privado genérico envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado basado en el adaptador de SQL de envío y puertos de recepción.  
  
 De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el ejemplo de \< *unidad*>: \Program archivos\\Microsoft BizTalk \<versión > Accelerator for RosettaNet\SDK\ PrivateResponder.  
  
## <a name="sample-contents"></a>Contenido del ejemplo  
 El proceso privado del Respondedor es el proceso empresarial que es interno para el servicio de respuesta. Proceso privado proporciona integración de back-end entre el proceso público del servicio de respuesta y el programa de línea de negocio de back-end. El proceso privado del Respondedor se comunica con el proceso público para responder a mensajes.  
  
 El proceso privado del Respondedor es único para cada implementación. Puede personalizar el ejemplo PrivateResponder.odx para sus fines. Se debe tener cuidado de que no afectar negativamente a que funcione el proceso público del Respondedor.  
  
 Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso privado del Respondedor](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)