---
title: 'Paso 2: Configurar NLB en los servidores | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Network Load Balancing
- configuring, NLB
- NLB
ms.assetid: 30b2f645-b495-49a5-852b-cf89d25fd2b7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d174ba336a94d44aaffdb2605542035304d9ff
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-configuring-nlb-on-the-servers"></a>Paso 2: Configurar NLB en los servidores
Después de haber instalado la plataforma base y configura los servidores con la configuración de red adecuado (consulte [paso 1: instalación de la plataforma Base](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)), puede que necesite habilitar el equilibrio de carga en los servidores front-end HTTP de BizTalk y BizTalk Servidores de mensajería. Este paso es necesario únicamente si tiene uno o más HTTP de BizTalk servidores front-end instalados en un equipo independiente de uno o más servidores de mensajería de BizTalk.  
  
 Equilibrio de carga garantiza la alta disponibilidad de la comunicación entre los equipos cliente (los usuarios de Internet Explorer se examinan en el sitio MRSR) y los servidores MRSR y entre los servidores MRSR y los servidores de mensajería.  
  
 Equilibrio de carga en el **público** interfaces de los servidores front-end HTTP es necesario para permitir a los usuarios de Intranet para conectarse a los servidores Web de IIS en estos equipos. Equilibrio de carga en el **privada** interfaces de los servidores front-end HTTP es necesario para habilitar los servidores de mensajería ponerse en contacto con los servicios web en estos equipos.  
  
 En los servidores de mensajes, suponiendo que hay dos servidores, configurar el equilibrio de carga en el **privada** adaptadores de red.  
  
 Para obtener más información, consulte a la Guía de implementación de BizTalk Server.