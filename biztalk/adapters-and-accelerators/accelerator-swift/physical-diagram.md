---
title: Diagrama físico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: 4291727b-8687-496a-8f03-0da4b3201967
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fcd0558d8fe3d45063a53800b1f3c082a2ba056
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213964"
---
# <a name="physical-diagram"></a>Diagrama físico
Una implementación típica agrupado equipos con BizTalk Server para la mensajería (enviar y recibir), equipos de BizTalk Server para ejecutar el proceso empresarial (orquestación), los equipos con BizTalk Server para tener acceso a las plantillas de InfoPath (sitio MRSR), y equipos con SQL Server en clúster. La siguiente implementación garantiza un entorno seguro desde la intranet y los usuarios de Internet.  
  
> [!NOTE]
>  Esta implementación típica es la configuración recomendada. Debe comprobar sus propias necesidades empresariales y las configuraciones de servidor para asegurarse de que la implementación funciona correctamente.  
  
 Se puede ajustar esta implementación hacia arriba o hacia abajo, hacia fuera o hacia atrás, según el perfil de uso y sus crecientes necesidades empresariales. Los escenarios de escalabilidad típicos incluyen agregar uno o más servidores en cada clúster para garantizar la alta disponibilidad o un mejor rendimiento. Las empresas más pequeñas podría ser preferible escalar su implementación para que los mismos servidores realice varias funciones, como tener una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] equipo controlar de mensajería y orquestación. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]admite la implementación en un solo servidor. En la siguiente ilustración muestra un ejemplo del entorno de implementación distribuida recomendada para una implementación completa de A4SWIFT.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
Ejemplo de una implementación completa de A4SWIFT