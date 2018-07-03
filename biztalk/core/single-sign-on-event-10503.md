---
title: 'De sesión único: Evento 10503 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b90af01551359b5caa1a5404facc9e3fece95673
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990717"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="c2d65-102">De sesión único: Evento 10503</span><span class="sxs-lookup"><span data-stu-id="c2d65-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="c2d65-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c2d65-103">Details</span></span>  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  <span data-ttu-id="c2d65-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c2d65-104">Product Name</span></span>   |                   <span data-ttu-id="c2d65-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="c2d65-105">Enterprise Single Sign-On</span></span>                   |
| <span data-ttu-id="c2d65-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c2d65-106">Product Version</span></span> |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="c2d65-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c2d65-107">Event ID</span></span>     |                             <span data-ttu-id="c2d65-108">10503</span><span class="sxs-lookup"><span data-stu-id="c2d65-108">10503</span></span>                             |
|  <span data-ttu-id="c2d65-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c2d65-109">Event Source</span></span>   |                            <span data-ttu-id="c2d65-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2d65-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="c2d65-111">Componente</span><span class="sxs-lookup"><span data-stu-id="c2d65-111">Component</span></span>    |                              <span data-ttu-id="c2d65-112">N\D</span><span class="sxs-lookup"><span data-stu-id="c2d65-112">N\A</span></span>                              |
|  <span data-ttu-id="c2d65-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c2d65-113">Symbolic Name</span></span>  |                <span data-ttu-id="c2d65-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="c2d65-114">SSO_ERROR_SERVICE_START_FAILED</span></span>                 |
|  <span data-ttu-id="c2d65-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c2d65-115">Message Text</span></span>   | <span data-ttu-id="c2d65-116">Error al iniciar el servicio SSO.%r</span><span class="sxs-lookup"><span data-stu-id="c2d65-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="c2d65-117">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="c2d65-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c2d65-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="c2d65-118">Explanation</span></span>  
 <span data-ttu-id="c2d65-119">Este evento de error indica que el servicio ENTSSO no pudo iniciarse debido a una excepción.</span><span class="sxs-lookup"><span data-stu-id="c2d65-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c2d65-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c2d65-120">User Action</span></span>  
 <span data-ttu-id="c2d65-121">Para resolver este error, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c2d65-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="c2d65-122">Compruebe si en los registros de eventos del sistema y la aplicación existen errores relacionados de ENTSSO u otros servicios.</span><span class="sxs-lookup"><span data-stu-id="c2d65-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="c2d65-123">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c2d65-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c2d65-124">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="c2d65-124">Using SSO</span></span>](../core/using-sso.md)
