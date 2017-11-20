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
ms.openlocfilehash: f10a05f23012990a1a0cc3dd50e0ca3db4282c84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configuring-nlb-on-the-servers"></a><span data-ttu-id="f1f7c-102">Paso 2: Configurar NLB en los servidores</span><span class="sxs-lookup"><span data-stu-id="f1f7c-102">Step 2: Configuring NLB on the Servers</span></span>
<span data-ttu-id="f1f7c-103">Después de haber instalado la plataforma base y configura los servidores con la configuración de red adecuado (consulte [paso 1: instalación de la plataforma Base](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)), puede que necesite habilitar el equilibrio de carga en los servidores front-end HTTP de BizTalk y BizTalk Servidores de mensajería.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-103">After you have installed the base platform and configured the servers with the proper network settings (see [Step 1: Installing the Base Platform](../../adapters-and-accelerators/accelerator-swift/step-1-installing-the-base-platform.md)), you may need to enable load balancing on BizTalk HTTP front-end servers and the BizTalk Messaging servers.</span></span> <span data-ttu-id="f1f7c-104">Este paso es necesario únicamente si tiene uno o más HTTP de BizTalk servidores front-end instalados en un equipo independiente de uno o más servidores de mensajería de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-104">This step is needed only if you have one or more BizTalk HTTP front-end servers installed on a separate computer from one or more BizTalk Messaging servers.</span></span>  
  
 <span data-ttu-id="f1f7c-105">Equilibrio de carga garantiza la alta disponibilidad de la comunicación entre los equipos cliente (los usuarios de Internet Explorer se examinan en el sitio MRSR) y los servidores MRSR y entre los servidores MRSR y los servidores de mensajería.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-105">Load balancing ensures high-availability communication between the client computers (Internet Explorer users browsing to the MRSR site) and the MRSR servers, and between the MRSR servers and the messaging servers.</span></span>  
  
 <span data-ttu-id="f1f7c-106">Equilibrio de carga en el **público** interfaces de los servidores front-end HTTP es necesario para permitir a los usuarios de Intranet para conectarse a los servidores Web de IIS en estos equipos.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-106">Load balancing on the **Public** interfaces of the HTTP front-end servers is required to enable the Intranet users to connect to the IIS Web servers on these computers.</span></span> <span data-ttu-id="f1f7c-107">Equilibrio de carga en el **privada** interfaces de los servidores front-end HTTP es necesario para habilitar los servidores de mensajería ponerse en contacto con los servicios web en estos equipos.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-107">Load balancing on the **Private** interfaces of the HTTP front-end servers is required to enable the messaging servers to contact the web services on these computers.</span></span>  
  
 <span data-ttu-id="f1f7c-108">En los servidores de mensajes, suponiendo que hay dos servidores, configurar el equilibrio de carga en el **privada** adaptadores de red.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-108">On the messaging servers, assuming there are two servers, configure load balancing on the **Private** network adapters.</span></span>  
  
 <span data-ttu-id="f1f7c-109">Para obtener más información, consulte el [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Guía de implementación.</span><span class="sxs-lookup"><span data-stu-id="f1f7c-109">For more information, see the [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Deployment Guide.</span></span>