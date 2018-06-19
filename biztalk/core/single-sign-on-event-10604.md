---
title: 'Inicio de sesión único: Evento 10604 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d9d6858fb13542ca642c9c48a8a187b66ba6526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270548"
---
# <a name="single-sign-on-event-10604"></a><span data-ttu-id="21bf1-102">Inicio de sesión único: Evento 10604</span><span class="sxs-lookup"><span data-stu-id="21bf1-102">Single Sign-On: Event 10604</span></span>
## <a name="details"></a><span data-ttu-id="21bf1-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="21bf1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21bf1-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="21bf1-104">Product Name</span></span>|<span data-ttu-id="21bf1-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="21bf1-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="21bf1-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="21bf1-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="21bf1-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="21bf1-107">Event ID</span></span>|<span data-ttu-id="21bf1-108">10604</span><span class="sxs-lookup"><span data-stu-id="21bf1-108">10604</span></span>|  
|<span data-ttu-id="21bf1-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="21bf1-109">Event Source</span></span>|<span data-ttu-id="21bf1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="21bf1-110">ENTSSO</span></span>|  
|<span data-ttu-id="21bf1-111">Componente</span><span class="sxs-lookup"><span data-stu-id="21bf1-111">Component</span></span>|<span data-ttu-id="21bf1-112">N/D</span><span class="sxs-lookup"><span data-stu-id="21bf1-112">N/A</span></span>|  
|<span data-ttu-id="21bf1-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="21bf1-113">Symbolic Name</span></span>|<span data-ttu-id="21bf1-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span><span class="sxs-lookup"><span data-stu-id="21bf1-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span></span>|  
|<span data-ttu-id="21bf1-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="21bf1-115">Message Text</span></span>|<span data-ttu-id="21bf1-116">La aplicación COM+ "Servidor de ENTSSO" no está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="21bf1-116">The 'ENTSSO Server' COM+ application is not configured correctly.</span></span> <span data-ttu-id="21bf1-117">Debe ser una aplicación de biblioteca COM+.</span><span class="sxs-lookup"><span data-stu-id="21bf1-117">It must be a COM+ library application.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="21bf1-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="21bf1-118">Explanation</span></span>  
 <span data-ttu-id="21bf1-119">La aplicación COM+ debe configurarse como una aplicación de biblioteca COM+.</span><span class="sxs-lookup"><span data-stu-id="21bf1-119">The COM+ application must be configured as a COM+ library application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21bf1-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="21bf1-120">User Action</span></span>  
 <span data-ttu-id="21bf1-121">En Complemento MMC de ENTSSO, expanda la carpeta COM+ y busque el servidor de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="21bf1-121">In the ENTSSO MMC Snap-In, expand the COM+ folder and locate your ENTSSO Server.</span></span> <span data-ttu-id="21bf1-122">Haga clic con el botón secundario en el servidor y, a continuación, haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="21bf1-122">Right-click the server, and then click Properties.</span></span> <span data-ttu-id="21bf1-123">En lugar de Aplicación de servidor, seleccione Aplicación de biblioteca y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="21bf1-123">Select Library Application instead of Server Application, and click OK.</span></span>