---
title: Configuración de red | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: fb6265b8-2e6d-4344-bb44-4f4fd995382d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fb693b9718b7c92e24f3537bea7ef27267f9a05
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967445"
---
# <a name="network-configuration"></a>Configuración de red
Esta sección proporciona instrucciones para configurar la red en su implementación. Para obtener más información, consulte [preparación para la implementación](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).  

 Definir las redes de área local virtuales (VLAN) en el conmutador y, a continuación, conecte los cables adecuados. Al definir las VLAN, que designa los puertos del conmutador para cada nivel o un segmento de red. Debe crear una VLAN para cada uno de los siguientes entornos:  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] nivel de envío y recepción  

- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] nivel de orquestación y de base de datos  

- Red corporativa  

  Después de haber definido las VLAN, puede conectar los cables de red de los servidores a los puertos correspondientes en el conmutador.  

  Esta sección contiene:  

- [Diagrama físico](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  

- [Equilibrio de carga de red](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)
