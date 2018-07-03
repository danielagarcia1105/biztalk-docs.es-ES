---
title: 'De sesión único: Evento 10653 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9f0edb3ce5fa7f8fb59c4b65914a9c8b6640adc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969461"
---
# <a name="single-sign-on-event-10653"></a><span data-ttu-id="46b6f-102">De sesión único: Evento 10653</span><span class="sxs-lookup"><span data-stu-id="46b6f-102">Single Sign-On: Event 10653</span></span>
## <a name="details"></a><span data-ttu-id="46b6f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="46b6f-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="46b6f-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="46b6f-104">Product Name</span></span>   |                 <span data-ttu-id="46b6f-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="46b6f-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="46b6f-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="46b6f-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="46b6f-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="46b6f-107">Event ID</span></span>     |                           <span data-ttu-id="46b6f-108">10653</span><span class="sxs-lookup"><span data-stu-id="46b6f-108">10653</span></span>                            |
|  <span data-ttu-id="46b6f-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="46b6f-109">Event Source</span></span>   |                           <span data-ttu-id="46b6f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="46b6f-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="46b6f-111">Componente</span><span class="sxs-lookup"><span data-stu-id="46b6f-111">Component</span></span>    |                            <span data-ttu-id="46b6f-112">N\D</span><span class="sxs-lookup"><span data-stu-id="46b6f-112">N\A</span></span>                             |
|  <span data-ttu-id="46b6f-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="46b6f-113">Symbolic Name</span></span>  |        <span data-ttu-id="46b6f-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="46b6f-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="46b6f-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="46b6f-115">Message Text</span></span>   |    <span data-ttu-id="46b6f-116">Acceso denegado al servidor de sincronización de contraseñas (para adaptadores).%r</span><span class="sxs-lookup"><span data-stu-id="46b6f-116">Password sync server (for adapters) access denied.%r</span></span>    |

## <a name="explanation"></a><span data-ttu-id="46b6f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="46b6f-117">Explanation</span></span>  
 <span data-ttu-id="46b6f-118">Este evento de error indica que un cliente intentó comunicarse con el servidor pero se rechazó la llamada.</span><span class="sxs-lookup"><span data-stu-id="46b6f-118">This Error event indicates that a client attempted to contact the server but the call was refused.</span></span> <span data-ttu-id="46b6f-119">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes.</span><span class="sxs-lookup"><span data-stu-id="46b6f-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  

## <a name="user-action"></a><span data-ttu-id="46b6f-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="46b6f-120">User Action</span></span>  
 <span data-ttu-id="46b6f-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="46b6f-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="46b6f-122">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46b6f-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="46b6f-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="46b6f-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="46b6f-124">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="46b6f-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
