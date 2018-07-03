---
title: Diagrama físico | Microsoft Docs
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
ms.openlocfilehash: 695c8ca0fd03fd8324f5b0ab86d72c1c0b6daf9f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978637"
---
# <a name="physical-diagram"></a>Diagrama físico
Una implementación típica tiene el clúster equipos con BizTalk Server para la mensajería (enviar y recibir), los equipos de BizTalk Server para ejecutar el proceso empresarial (orquestación), los equipos de BizTalk Server para tener acceso a las plantillas de InfoPath (sitio MRSR), y equipos con SQL Server en clúster. La siguiente implementación garantiza un entorno seguro de la intranet y los usuarios de Internet.  
  
> [!NOTE]
>  Esta implementación típica es la configuración recomendada. Deberá comprobar sus propias necesidades empresariales y las configuraciones de servidor para asegurarse de que la implementación funciona correctamente.  
  
 Puede escalar esta implementación o reducir verticalmente, horizontalmente o, según el perfil de uso y las necesidades empresariales crecientes. Escenarios de escalabilidad típico incluyen la adición de uno o más servidores en cada clúster para garantizar una mayor disponibilidad o un mejor rendimiento. Las empresas más pequeñas que prefiera de escalado de su implementación para que tenga los mismos servidores que realizan varias funciones, como tener un nuevo [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] equipo controle de mensajería y orquestación. Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] admite la implementación en un único servidor. En la siguiente ilustración se muestra un ejemplo del entorno de implementación distribuida recomendada para una implementación completa de A4SWIFT.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
Ejemplo de una implementación completa de A4SWIFT