---
title: 'De sesión único: Evento 11049 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b86cf3d5361a912cd976d8a27e83981b71237e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997509"
---
# <a name="single-sign-on-event-11049"></a><span data-ttu-id="43eb7-102">De sesión único: Evento 11049</span><span class="sxs-lookup"><span data-stu-id="43eb7-102">Single Sign-On: Event 11049</span></span>
## <a name="details"></a><span data-ttu-id="43eb7-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="43eb7-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="43eb7-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="43eb7-104">Product Name</span></span>   |                   <span data-ttu-id="43eb7-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="43eb7-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="43eb7-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="43eb7-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="43eb7-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="43eb7-107">Event ID</span></span>     |                             <span data-ttu-id="43eb7-108">11049</span><span class="sxs-lookup"><span data-stu-id="43eb7-108">11049</span></span>                              |
|  <span data-ttu-id="43eb7-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="43eb7-109">Event Source</span></span>   |                             <span data-ttu-id="43eb7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="43eb7-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="43eb7-111">Componente</span><span class="sxs-lookup"><span data-stu-id="43eb7-111">Component</span></span>    |                              <span data-ttu-id="43eb7-112">N/D</span><span class="sxs-lookup"><span data-stu-id="43eb7-112">N/A</span></span>                               |
|  <span data-ttu-id="43eb7-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="43eb7-113">Symbolic Name</span></span>  |                      <span data-ttu-id="43eb7-114">SSO_ERROR_DTC_FAILED</span><span class="sxs-lookup"><span data-stu-id="43eb7-114">SSO_ERROR_DTC_FAILED</span></span>                      |
|  <span data-ttu-id="43eb7-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="43eb7-115">Message Text</span></span>   | <span data-ttu-id="43eb7-116">No se pudo obtener MSDTC.</span><span class="sxs-lookup"><span data-stu-id="43eb7-116">Could not get MSDTC.</span></span> <span data-ttu-id="43eb7-117">SSO necesita MSDTC para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="43eb7-117">SSO requires MSDTC for correct operation.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="43eb7-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="43eb7-118">Explanation</span></span>  
 <span data-ttu-id="43eb7-119">El sistema ENTSSO no pudo conectarse con Microsoft DTC (Coordinador de transacciones distribuidas).</span><span class="sxs-lookup"><span data-stu-id="43eb7-119">The ENTSSO system could not connect to the Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="43eb7-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="43eb7-120">User Action</span></span>  
 <span data-ttu-id="43eb7-121">Compruebe si MSDTC se encuentra operativo actualmente.</span><span class="sxs-lookup"><span data-stu-id="43eb7-121">Check to see if MSDTC is currently operational.</span></span>  
  
 <span data-ttu-id="43eb7-122">Para obtener ayuda sobre problemas de MSDTC, vea [solución de problemas con MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span><span class="sxs-lookup"><span data-stu-id="43eb7-122">For help on MSDTC issues, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>