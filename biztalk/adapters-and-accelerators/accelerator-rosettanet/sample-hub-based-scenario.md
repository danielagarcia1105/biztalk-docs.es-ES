---
title: Ejemplo de escenario basado en concentrador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- hub-and-spoke systems
- supply chains, hub-and-spoke systems
- examples, supply chains
- trading partners, supply chains
ms.assetid: ee92c24d-a281-4950-a61e-9cb3bd08d291
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b417398786e602379d16d6734a5ed366b9d6f2ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210420"
---
# <a name="sample-hub-based-scenario"></a>Escenario de ejemplo basado en concentrador
En muchos escenarios de cadena de suministro, una empresa trabajará con cada uno de sus socios comerciales para establecer una conexión de RosettaNet Implementation Framework (RNIF). Se trata de un método eficaz para estandarizar las comunicaciones en toda la cadena de suministro. Este escenario se describe en [escenario de cadena de suministro de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md).  
  
 Otra manera de automatizar las transacciones en toda la cadena de suministro consiste en que la empresa contrate a otra organización para configurar y administrar el sistema integrado. Este es un escenario basado en concentrador.  
  
## <a name="how-a-hub-based-system-works"></a>Cómo funciona un sistema basado en concentrador  
 En un sistema basado en concentrador, la empresa que contrata un sistema integrado se conecta a la empresa de concentrador mediante una conexión RNIF. A continuación, el concentrador se conecta a todos los socios comerciales de la empresa usando el tipo de conexión electrónica que sea necesario. La empresa de concentrador proporciona opciones de conexión a todos los socios comerciales: Conexiones RNIF, EDI, archivo plano, aplicaciones web o conexiones no compatibles de propietario. La administración del sistema de comunicaciones es asunto de la empresa de concentrador. La ilustración siguiente muestra el funcionamiento de este sistema.  
  
 ![&#60; No hay ningún cambio &#62; ] (../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")  
  
 Un sistema basado en concentrador tiene muchas ventajas:  
  
-   La empresa contratante no tiene que preocuparse por la complejidad de la cadena de suministro, ya que se encarga de ello la empresa de concentrador.  
  
-   La empresa contratante no tiene que mantener o actualizar el sistema y no es responsable del tiempo de inactividad; la empresa de concentrador se responsabiliza del mantenimiento del sistema y del tiempo de inactividad.  
  
-   La empresa contratante se beneficia de las ventajas de un sistema compatible con RosettaNet, lo que incluye la estandarización, la automatización, el ahorro de costos y la visibilidad.  
  
-   La empresa contratante automatiza por completo su cadena de suministro con diversas conexiones electrónicas que ofrecen a todos los socios comerciales una selección de conexiones. La empresa contratante no necesita tener conocimientos tecnológicos en diversas opciones de conexión.  
  
-   Un socio comercial puede seguir usando una conexión de propietario, siempre y cuando lo admita la empresa de concentrador.  
  
-   El sistema es flexible. No es necesario que los socios comerciales adopten un sistema compatible con RosettaNet. Sin embargo, si lo hacen, podrán beneficiarse de dicho sistema.  
  
## <a name="see-also"></a>Vea también  
 [Cómo BizTalk Server resuelve la necesidad empresarial](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [La necesidad de integración de socios comerciales](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md)   
 [El desafío de la cadena de suministro](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md)   
 [La solución de la cadena de suministro](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md)   
 [Escenario de cadena de suministro de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)