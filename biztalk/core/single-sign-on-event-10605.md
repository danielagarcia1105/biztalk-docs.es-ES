---
title: 'Inicio de sesión único: Evento 10605 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e7d0fb4befaacd8734f866f2c11c7446d4e5854
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270316"
---
# <a name="single-sign-on-event-10605"></a><span data-ttu-id="eb3a8-102">Inicio de sesión único: Evento 10605</span><span class="sxs-lookup"><span data-stu-id="eb3a8-102">Single Sign-On: Event 10605</span></span>
## <a name="details"></a><span data-ttu-id="eb3a8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="eb3a8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb3a8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="eb3a8-104">Product Name</span></span>|<span data-ttu-id="eb3a8-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="eb3a8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="eb3a8-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="eb3a8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="eb3a8-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="eb3a8-107">Event ID</span></span>|<span data-ttu-id="eb3a8-108">10605</span><span class="sxs-lookup"><span data-stu-id="eb3a8-108">10605</span></span>|  
|<span data-ttu-id="eb3a8-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="eb3a8-109">Event Source</span></span>|<span data-ttu-id="eb3a8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="eb3a8-110">ENTSSO</span></span>|  
|<span data-ttu-id="eb3a8-111">Componente</span><span class="sxs-lookup"><span data-stu-id="eb3a8-111">Component</span></span>|<span data-ttu-id="eb3a8-112">N/D</span><span class="sxs-lookup"><span data-stu-id="eb3a8-112">N/A</span></span>|  
|<span data-ttu-id="eb3a8-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="eb3a8-113">Symbolic Name</span></span>|<span data-ttu-id="eb3a8-114">SSO_ERROR_DTC_IMPORT</span><span class="sxs-lookup"><span data-stu-id="eb3a8-114">SSO_ERROR_DTC_IMPORT</span></span>|  
|<span data-ttu-id="eb3a8-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="eb3a8-115">Message Text</span></span>|<span data-ttu-id="eb3a8-116">No se pudo importar una transacción de DTC.</span><span class="sxs-lookup"><span data-stu-id="eb3a8-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="eb3a8-117">Compruebe que MSDTC está correctamente configurado para funcionamiento remoto.</span><span class="sxs-lookup"><span data-stu-id="eb3a8-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="eb3a8-118">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="eb3a8-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="eb3a8-119">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="eb3a8-119">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="eb3a8-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="eb3a8-120">Explanation</span></span>  
 <span data-ttu-id="eb3a8-121">Existe un problema con Microsoft DTC (Coordinador de transacciones distribuidas).</span><span class="sxs-lookup"><span data-stu-id="eb3a8-121">There is a problem with the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="eb3a8-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="eb3a8-122">User Action</span></span>  
 <span data-ttu-id="eb3a8-123">Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span><span class="sxs-lookup"><span data-stu-id="eb3a8-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>