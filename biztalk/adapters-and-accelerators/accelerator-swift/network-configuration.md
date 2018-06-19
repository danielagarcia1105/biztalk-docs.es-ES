---
title: Configuración de red | Documentos de Microsoft
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
ms.openlocfilehash: 83a9e8ffe6b278c91429835c3ae32c96d45ef22e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214428"
---
# <a name="network-configuration"></a>Configuración de red
Esta sección proporciona instrucciones para configurar la red en su implementación. Para obtener más información, consulte [preparar para la implementación](../../adapters-and-accelerators/accelerator-swift/preparing-for-deployment.md).  
  
 Definir redes de área local virtuales (VLAN) en el conmutador y, a continuación, conecte los cables adecuados. Al definir las VLAN, designa puertos en el conmutador para cada segmento de red o la capa. Debe crear una VLAN para cada uno de los siguientes entornos:  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]nivel de envío y recepción  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]nivel de orquestación y base de datos  
  
-   Red corporativa  
  
 Después de definir las VLAN, puede conectar los cables de red de los servidores a los puertos correspondientes en el conmutador.  
  
 Esta sección contiene:  
  
-   [Diagrama físico](../../adapters-and-accelerators/accelerator-swift/physical-diagram.md)  
  
-   [Equilibrio de carga de red](../../adapters-and-accelerators/accelerator-swift/network-load-balancing.md)