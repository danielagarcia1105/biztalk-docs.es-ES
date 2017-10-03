---
title: "Inicio de sesión único: Evento 11049 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ac6095950e02e7e73ab287b180bc22d88b4191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11049"></a><span data-ttu-id="8bb82-102">Inicio de sesión único: Evento 11049</span><span class="sxs-lookup"><span data-stu-id="8bb82-102">Single Sign-On: Event 11049</span></span>
## <a name="details"></a><span data-ttu-id="8bb82-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8bb82-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8bb82-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8bb82-104">Product Name</span></span>|<span data-ttu-id="8bb82-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8bb82-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="8bb82-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8bb82-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="8bb82-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8bb82-107">Event ID</span></span>|<span data-ttu-id="8bb82-108">11049</span><span class="sxs-lookup"><span data-stu-id="8bb82-108">11049</span></span>|  
|<span data-ttu-id="8bb82-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8bb82-109">Event Source</span></span>|<span data-ttu-id="8bb82-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8bb82-110">ENTSSO</span></span>|  
|<span data-ttu-id="8bb82-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8bb82-111">Component</span></span>|<span data-ttu-id="8bb82-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8bb82-112">N/A</span></span>|  
|<span data-ttu-id="8bb82-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8bb82-113">Symbolic Name</span></span>|<span data-ttu-id="8bb82-114">SSO_ERROR_DTC_FAILED</span><span class="sxs-lookup"><span data-stu-id="8bb82-114">SSO_ERROR_DTC_FAILED</span></span>|  
|<span data-ttu-id="8bb82-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8bb82-115">Message Text</span></span>|<span data-ttu-id="8bb82-116">No se pudo obtener MSDTC.</span><span class="sxs-lookup"><span data-stu-id="8bb82-116">Could not get MSDTC.</span></span> <span data-ttu-id="8bb82-117">SSO necesita MSDTC para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="8bb82-117">SSO requires MSDTC for correct operation.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8bb82-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="8bb82-118">Explanation</span></span>  
 <span data-ttu-id="8bb82-119">El sistema ENTSSO no pudo conectarse con Microsoft DTC (Coordinador de transacciones distribuidas).</span><span class="sxs-lookup"><span data-stu-id="8bb82-119">The ENTSSO system could not connect to the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8bb82-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8bb82-120">User Action</span></span>  
 <span data-ttu-id="8bb82-121">Compruebe si MSDTC se encuentra operativo actualmente.</span><span class="sxs-lookup"><span data-stu-id="8bb82-121">Check to see if MSDTC is currently operational.</span></span>  
  
 <span data-ttu-id="8bb82-122">Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span><span class="sxs-lookup"><span data-stu-id="8bb82-122">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>