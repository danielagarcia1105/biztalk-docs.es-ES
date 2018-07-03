---
title: 'De sesión único: Evento 10605 | Microsoft Docs'
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
ms.openlocfilehash: c578462759d2eeb69767d21191e028ef9e8ce1e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972517"
---
# <a name="single-sign-on-event-10605"></a><span data-ttu-id="b3c00-102">De sesión único: Evento 10605</span><span class="sxs-lookup"><span data-stu-id="b3c00-102">Single Sign-On: Event 10605</span></span>
## <a name="details"></a><span data-ttu-id="b3c00-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b3c00-103">Details</span></span>  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b3c00-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b3c00-104">Product Name</span></span>   |                                                                       <span data-ttu-id="b3c00-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="b3c00-105">Enterprise Single Sign-On</span></span>                                                                       |
| <span data-ttu-id="b3c00-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b3c00-106">Product Version</span></span> |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="b3c00-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b3c00-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="b3c00-108">10605</span><span class="sxs-lookup"><span data-stu-id="b3c00-108">10605</span></span>                                                                                 |
|  <span data-ttu-id="b3c00-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b3c00-109">Event Source</span></span>   |                                                                                <span data-ttu-id="b3c00-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b3c00-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="b3c00-111">Componente</span><span class="sxs-lookup"><span data-stu-id="b3c00-111">Component</span></span>    |                                                                                  <span data-ttu-id="b3c00-112">N/D</span><span class="sxs-lookup"><span data-stu-id="b3c00-112">N/A</span></span>                                                                                  |
|  <span data-ttu-id="b3c00-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b3c00-113">Symbolic Name</span></span>  |                                                                         <span data-ttu-id="b3c00-114">SSO_ERROR_DTC_IMPORT</span><span class="sxs-lookup"><span data-stu-id="b3c00-114">SSO_ERROR_DTC_IMPORT</span></span>                                                                          |
|  <span data-ttu-id="b3c00-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b3c00-115">Message Text</span></span>   | <span data-ttu-id="b3c00-116">No se pudo importar una transacción de DTC.</span><span class="sxs-lookup"><span data-stu-id="b3c00-116">Could not import a DTC transaction.</span></span> <span data-ttu-id="b3c00-117">Compruebe que MSDTC está correctamente configurado para funcionamiento remoto.</span><span class="sxs-lookup"><span data-stu-id="b3c00-117">Please check that MSDTC is configured correctly for remote operation.</span></span> <span data-ttu-id="b3c00-118">Consulte la documentación de details.%r</span><span class="sxs-lookup"><span data-stu-id="b3c00-118">See documentation for details.%r</span></span><br /><br /> <span data-ttu-id="b3c00-119">Código de error: %1</span><span class="sxs-lookup"><span data-stu-id="b3c00-119">Error Code: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b3c00-120">Explicación</span><span class="sxs-lookup"><span data-stu-id="b3c00-120">Explanation</span></span>  
 <span data-ttu-id="b3c00-121">Existe un problema con Microsoft DTC (Coordinador de transacciones distribuidas).</span><span class="sxs-lookup"><span data-stu-id="b3c00-121">There is a problem with the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b3c00-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b3c00-122">User Action</span></span>  
 <span data-ttu-id="b3c00-123">Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span><span class="sxs-lookup"><span data-stu-id="b3c00-123">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>