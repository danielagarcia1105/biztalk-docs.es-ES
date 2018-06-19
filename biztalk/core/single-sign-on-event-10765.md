---
title: 'Inicio de sesión único: Evento 10765 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0fbc04f4c8fc98a87de87a4cd48529a3ca7e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278420"
---
# <a name="single-sign-on-event-10765"></a><span data-ttu-id="9f716-102">Inicio de sesión único: Evento 10765</span><span class="sxs-lookup"><span data-stu-id="9f716-102">Single Sign-On: Event 10765</span></span>
## <a name="details"></a><span data-ttu-id="9f716-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9f716-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f716-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="9f716-104">Product Name</span></span>|<span data-ttu-id="9f716-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="9f716-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="9f716-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="9f716-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="9f716-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="9f716-107">Event ID</span></span>|<span data-ttu-id="9f716-108">10765</span><span class="sxs-lookup"><span data-stu-id="9f716-108">10765</span></span>|  
|<span data-ttu-id="9f716-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="9f716-109">Event Source</span></span>|<span data-ttu-id="9f716-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9f716-110">ENTSSO</span></span>|  
|<span data-ttu-id="9f716-111">Componente</span><span class="sxs-lookup"><span data-stu-id="9f716-111">Component</span></span>|<span data-ttu-id="9f716-112">N/D</span><span class="sxs-lookup"><span data-stu-id="9f716-112">N/A</span></span>|  
|<span data-ttu-id="9f716-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9f716-113">Symbolic Name</span></span>|<span data-ttu-id="9f716-114">ENTSSO_E_NO_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="9f716-114">ENTSSO_E_NO_CREDENTIALS</span></span>|  
|<span data-ttu-id="9f716-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9f716-115">Message Text</span></span>|<span data-ttu-id="9f716-116">No se establecieron credenciales para la asignación.</span><span class="sxs-lookup"><span data-stu-id="9f716-116">No credentials have been set for the mapping.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9f716-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="9f716-117">Explanation</span></span>  
 <span data-ttu-id="9f716-118">Se solicitó GetCredentials en una asignación, pero la asignación especificada no tiene credenciales.</span><span class="sxs-lookup"><span data-stu-id="9f716-118">You have requested a GetCredentials on a mapping, and the mapping specified has no credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f716-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9f716-119">User Action</span></span>  
 <span data-ttu-id="9f716-120">Use la línea de comandos o el complemento MMC para establecer las credenciales de la asignación.</span><span class="sxs-lookup"><span data-stu-id="9f716-120">Use the command line or the MMC Snap-in to set credentials for the mapping.</span></span>