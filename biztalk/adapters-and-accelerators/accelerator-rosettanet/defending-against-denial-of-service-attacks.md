---
title: Defensa contra los ataques por denegación de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 667b9d321f7703f770297b001ef2a99be2bf4902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209708"
---
# <a name="defending-against-denial-of-service-attacks"></a><span data-ttu-id="8b954-102">Defensa contra los ataques por denegación de servicio</span><span class="sxs-lookup"><span data-stu-id="8b954-102">Defending Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="8b954-103">Un usuario puede iniciar un ataque de denegación de servicio en una instalación de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] agotando el RNIFReceive.aspx de página de recepción.</span><span class="sxs-lookup"><span data-stu-id="8b954-103">Someone could start a denial-of-service attack against an installation of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] by stressing the RNIFReceive.aspx receive page.</span></span> <span data-ttu-id="8b954-104">Puede hacerlo mediante el envío de grandes cantidades de mensajes vacíos a esa página.</span><span class="sxs-lookup"><span data-stu-id="8b954-104">They could do so by sending large numbers of empty messages to that page.</span></span> <span data-ttu-id="8b954-105">Si no está activada, este tipo de ataque podría saturar el registro de eventos con eventos publicados por el ASPX izquierda recibe la página.</span><span class="sxs-lookup"><span data-stu-id="8b954-105">If left unchecked, such an attack could flood the event log with events published by the ASPX receive page.</span></span>  
  
## <a name="defending-against-an-attack"></a><span data-ttu-id="8b954-106">Defensa contra un ataque</span><span class="sxs-lookup"><span data-stu-id="8b954-106">Defending Against an Attack</span></span>  
 <span data-ttu-id="8b954-107">Para proteger el servidor contra los ataques de denegación de servicio, se recomienda que mantenga el registro de eventos con un tamaño razonable y tomar medidas para tratar con un número excesivo de eventos.</span><span class="sxs-lookup"><span data-stu-id="8b954-107">To defend your server against denial-of-service attacks, it is recommended that you maintain the event log at a reasonable size and take steps to deal with excessive numbers of events.</span></span> <span data-ttu-id="8b954-108">Puede hacerlo estableciendo el tamaño máximo del registro, seleccionando una manera de sobrescribir eventos o usar [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) para administrar el tamaño del registro.</span><span class="sxs-lookup"><span data-stu-id="8b954-108">You can accomplish this by setting the maximum log size, selecting a way of overwriting events, or using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) to manage the size of the log.</span></span> <span data-ttu-id="8b954-109">Para obtener más información, consulte la ayuda para [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span><span class="sxs-lookup"><span data-stu-id="8b954-109">For more information, see Help for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b954-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b954-110">See Also</span></span>  
 [<span data-ttu-id="8b954-111">Administrar la configuración, certificados, las bases de datos y seguridad</span><span class="sxs-lookup"><span data-stu-id="8b954-111">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)