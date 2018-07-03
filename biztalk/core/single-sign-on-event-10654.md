---
title: 'De sesión único: Evento 10654 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca59040b340d033ab6c355c0440378f09d87000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974485"
---
# <a name="single-sign-on-event-10654"></a><span data-ttu-id="383f0-102">De sesión único: Evento 10654</span><span class="sxs-lookup"><span data-stu-id="383f0-102">Single Sign-On: Event 10654</span></span>
## <a name="details"></a><span data-ttu-id="383f0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="383f0-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="383f0-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="383f0-104">Product Name</span></span>   |                 <span data-ttu-id="383f0-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="383f0-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="383f0-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="383f0-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="383f0-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="383f0-107">Event ID</span></span>     |                           <span data-ttu-id="383f0-108">10654</span><span class="sxs-lookup"><span data-stu-id="383f0-108">10654</span></span>                            |
|  <span data-ttu-id="383f0-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="383f0-109">Event Source</span></span>   |                           <span data-ttu-id="383f0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="383f0-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="383f0-111">Componente</span><span class="sxs-lookup"><span data-stu-id="383f0-111">Component</span></span>    |                            <span data-ttu-id="383f0-112">N\D</span><span class="sxs-lookup"><span data-stu-id="383f0-112">N\A</span></span>                             |
|  <span data-ttu-id="383f0-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="383f0-113">Symbolic Name</span></span>  |        <span data-ttu-id="383f0-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="383f0-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="383f0-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="383f0-115">Message Text</span></span>   |    <span data-ttu-id="383f0-116">Acceso denegado al servidor de sincronización de contraseñas (para Windows).%r</span><span class="sxs-lookup"><span data-stu-id="383f0-116">Password sync server (for Windows) access denied.%r</span></span>     |

## <a name="explanation"></a><span data-ttu-id="383f0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="383f0-117">Explanation</span></span>  
 <span data-ttu-id="383f0-118">Este evento de error indica que se envió un mensaje al servidor [nombre] pero se bloqueó la respuesta.</span><span class="sxs-lookup"><span data-stu-id="383f0-118">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="383f0-119">Existen diversos motivos para este evento, como protocolo incorrecto o falta de permisos de seguridad suficientes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="383f0-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="383f0-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="383f0-120">User Action</span></span>  
 <span data-ttu-id="383f0-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="383f0-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="383f0-122">Tenga en cuenta la información de este mensaje y cualquier información relevante en el registro de eventos y póngase en contacto con soporte técnico de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="383f0-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="383f0-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="383f0-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="383f0-124">Sincronización de contraseñas</span><span class="sxs-lookup"><span data-stu-id="383f0-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
