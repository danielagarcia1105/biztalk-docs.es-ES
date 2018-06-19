---
title: La inicialización del adaptador de recepción de SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce53aff3-6189-4033-b318-d703037518e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35ed17325252f1954f20cb25f963a5bd7a57d5e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224204"
---
# <a name="swift-receive-adapter-initialization"></a><span data-ttu-id="7b343-102">La inicialización del adaptador de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="7b343-102">SWIFT Receive Adapter Initialization</span></span>
<span data-ttu-id="7b343-103">El proceso de inicialización para la aplicación de servidor SWIFT es similar a la de la aplicación cliente SWIFT.</span><span class="sxs-lookup"><span data-stu-id="7b343-103">The initialization process for the SWIFT server application is similar to that for the SWIFT client application.</span></span> <span data-ttu-id="7b343-104">Los argumentos de inicialización se pasan como parámetros de línea de comandos para el receptor ejecutables.</span><span class="sxs-lookup"><span data-stu-id="7b343-104">The initialization arguments are passed as command line parameters to the receiver executable.</span></span> <span data-ttu-id="7b343-105">El nombre de aplicación configurado en la ubicación de recepción durante el tiempo de diseño, se pasa como un argumento de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7b343-105">The application name, configured in the receive location during design time, is passed as a command line argument.</span></span> <span data-ttu-id="7b343-106">Este nombre de la aplicación se utiliza para construir el URI para recuperar las propiedades configuradas de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="7b343-106">This application name is used to construct the receive location URI to retrieve the configured properties.</span></span>  
  
 <span data-ttu-id="7b343-107">Para obtener información acerca de cómo utilizar el argumento de línea de comandos, vea el tema "Cómo configurar la recepción adaptador entorno" en Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] Guía de instalación y configuración.</span><span class="sxs-lookup"><span data-stu-id="7b343-107">For information about using the command line argument, see the "How to Configure the Receive Adapter Environment" topic in Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] Installation and Configuration Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b343-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b343-108">See Also</span></span>  
 <span data-ttu-id="7b343-109">[Arquitectura del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="7b343-109">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="7b343-110">[URI del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="7b343-110">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="7b343-111">[Contexto de seguridad del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="7b343-111">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 <span data-ttu-id="7b343-112">[Modos sincrónico y diferido del adaptador de recepción de SWIFT](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="7b343-112">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="7b343-113">Adaptador de almacenamiento y reenvío de recepción de SWIFT</span><span class="sxs-lookup"><span data-stu-id="7b343-113">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)