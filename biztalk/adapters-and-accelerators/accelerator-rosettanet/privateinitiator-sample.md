---
title: Ejemplo de PrivateInitiator | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ab84d145939191a8bdbca9afb44d04fdf24b3e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011285"
---
# <a name="privateinitiator-sample"></a>Ejemplo de PrivateInitiator
El ejemplo PrivateInitiator.odx contiene el código para el proceso privado del iniciador instalado por Microsoft® BizTalk Server. Se trata de un proceso privado genérico que envía y recibe mensajes de contenido del servicio RNIF del valor predeterminado basado en el adaptador de SQL de envío y puertos de recepción.  
  
 De forma predeterminada, el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el ejemplo de \< *unidad*\>: \Program archivos\\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\PrivateInitiator.  
  
## <a name="sample-contents"></a>Contenido del ejemplo  
 Proceso privado del iniciador es el proceso empresarial que es interno al iniciador. Proceso privado proporciona integración de back-end entre el proceso público del iniciador y el programa de línea de negocio de back-end. Proceso privado del iniciador se comunica con el proceso público para iniciar los mensajes.  
  
 Proceso privado del iniciador es único para cada implementación. Puede personalizar el ejemplo PrivateInitiator.odx para sus fines. Debe asegurarse de que se no afectar el funcionamiento del proceso público del iniciador.  
  
 Para obtener más información, incluida una descripción del flujo de mensajes, vea [proceso privado del iniciador](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de orquestaciones](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [Procesos privados](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)