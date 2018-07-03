---
title: 'De sesión único: Evento 10604 | Microsoft Docs'
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
ms.openlocfilehash: 48996ec333c9035e57393e270db06ca173cfc9e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990589"
---
# <a name="single-sign-on-event-10604"></a><span data-ttu-id="da2fd-102">De sesión único: Evento 10604</span><span class="sxs-lookup"><span data-stu-id="da2fd-102">Single Sign-On: Event 10604</span></span>
## <a name="details"></a><span data-ttu-id="da2fd-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="da2fd-103">Details</span></span>  
  
|                 |                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="da2fd-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="da2fd-104">Product Name</span></span>   |                                        <span data-ttu-id="da2fd-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="da2fd-105">Enterprise Single Sign-On</span></span>                                         |
| <span data-ttu-id="da2fd-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="da2fd-106">Product Version</span></span> |                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                        |
|    <span data-ttu-id="da2fd-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="da2fd-107">Event ID</span></span>     |                                                  <span data-ttu-id="da2fd-108">10604</span><span class="sxs-lookup"><span data-stu-id="da2fd-108">10604</span></span>                                                   |
|  <span data-ttu-id="da2fd-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="da2fd-109">Event Source</span></span>   |                                                  <span data-ttu-id="da2fd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="da2fd-110">ENTSSO</span></span>                                                  |
|    <span data-ttu-id="da2fd-111">Componente</span><span class="sxs-lookup"><span data-stu-id="da2fd-111">Component</span></span>    |                                                   <span data-ttu-id="da2fd-112">N/D</span><span class="sxs-lookup"><span data-stu-id="da2fd-112">N/A</span></span>                                                    |
|  <span data-ttu-id="da2fd-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="da2fd-113">Symbolic Name</span></span>  |                                      <span data-ttu-id="da2fd-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span><span class="sxs-lookup"><span data-stu-id="da2fd-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span></span>                                       |
|  <span data-ttu-id="da2fd-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="da2fd-115">Message Text</span></span>   | <span data-ttu-id="da2fd-116">La aplicación COM+ "Servidor de ENTSSO" no está configurada correctamente.</span><span class="sxs-lookup"><span data-stu-id="da2fd-116">The 'ENTSSO Server' COM+ application is not configured correctly.</span></span> <span data-ttu-id="da2fd-117">Debe ser una aplicación de biblioteca COM+.</span><span class="sxs-lookup"><span data-stu-id="da2fd-117">It must be a COM+ library application.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="da2fd-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="da2fd-118">Explanation</span></span>  
 <span data-ttu-id="da2fd-119">La aplicación COM+ debe configurarse como una aplicación de biblioteca COM+.</span><span class="sxs-lookup"><span data-stu-id="da2fd-119">The COM+ application must be configured as a COM+ library application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da2fd-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="da2fd-120">User Action</span></span>  
 <span data-ttu-id="da2fd-121">En Complemento MMC de ENTSSO, expanda la carpeta COM+ y busque el servidor de ENTSSO.</span><span class="sxs-lookup"><span data-stu-id="da2fd-121">In the ENTSSO MMC Snap-In, expand the COM+ folder and locate your ENTSSO Server.</span></span> <span data-ttu-id="da2fd-122">Haga clic con el botón secundario en el servidor y, a continuación, haga clic en Propiedades.</span><span class="sxs-lookup"><span data-stu-id="da2fd-122">Right-click the server, and then click Properties.</span></span> <span data-ttu-id="da2fd-123">En lugar de Aplicación de servidor, seleccione Aplicación de biblioteca y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="da2fd-123">Select Library Application instead of Server Application, and click OK.</span></span>