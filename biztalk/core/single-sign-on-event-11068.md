---
title: 'De sesión único: Evento 11068 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f09a1191-ae67-4156-a8a5-d24e4439fc68
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 218da642493981211de4a0e10b504ea8f434945f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020498"
---
# <a name="single-sign-on-event-11068"></a><span data-ttu-id="8a553-102">De sesión único: Evento 11068</span><span class="sxs-lookup"><span data-stu-id="8a553-102">Single Sign-On: Event 11068</span></span>
## <a name="details"></a><span data-ttu-id="8a553-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8a553-103">Details</span></span>  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8a553-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="8a553-104">Product Name</span></span>   |                                                                      <span data-ttu-id="8a553-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="8a553-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="8a553-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="8a553-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    <span data-ttu-id="8a553-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="8a553-107">Event ID</span></span>     |                                                                                <span data-ttu-id="8a553-108">11068</span><span class="sxs-lookup"><span data-stu-id="8a553-108">11068</span></span>                                                                                |
|  <span data-ttu-id="8a553-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="8a553-109">Event Source</span></span>   |                                                                               <span data-ttu-id="8a553-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8a553-110">ENTSSO</span></span>                                                                                |
|    <span data-ttu-id="8a553-111">Componente</span><span class="sxs-lookup"><span data-stu-id="8a553-111">Component</span></span>    |                                                                                 <span data-ttu-id="8a553-112">N/D</span><span class="sxs-lookup"><span data-stu-id="8a553-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="8a553-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8a553-113">Symbolic Name</span></span>  |                                                          <span data-ttu-id="8a553-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span><span class="sxs-lookup"><span data-stu-id="8a553-114">SSO_ERROR_LOOKUP_CALLBACK_ACCESS_DENIED_NO_REMOTE</span></span>                                                          |
|  <span data-ttu-id="8a553-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8a553-115">Message Text</span></span>   | <span data-ttu-id="8a553-116">Acceso denegado al servidor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8a553-116">Lookup server access denied.</span></span> <span data-ttu-id="8a553-117">Este servidor de SSO actualmente no está configurado para permitir búsqueda remota.</span><span class="sxs-lookup"><span data-stu-id="8a553-117">This SSO server is currently not configured to allow remote lookup.</span></span> <span data-ttu-id="8a553-118">Use 'ssoconfig -remoteLookup yes' o la MMC de administración de SSO.%r</span><span class="sxs-lookup"><span data-stu-id="8a553-118">Use 'ssoconfig -remoteLookup yes' or the SSO Administration MMC.%r</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="8a553-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="8a553-119">Explanation</span></span>  
 <span data-ttu-id="8a553-120">Se denegó el acceso al servidor de búsqueda porque el servidor de ENTSSO no está configurado para permitir búsqueda remota.</span><span class="sxs-lookup"><span data-stu-id="8a553-120">Lookup server access has been denied because the ENTSSO server is not configured to allow remote lookup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8a553-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8a553-121">User Action</span></span>  
 <span data-ttu-id="8a553-122">Para permitir búsqueda remota, en el **servidores complemento**, **avanzadas** ficha, seleccione **Permitir búsqueda remota**.</span><span class="sxs-lookup"><span data-stu-id="8a553-122">To allow remote lookup, in the **Servers Snap-In**, **Advanced** tab, select **Allow Remote Lookup**.</span></span>  
  
 <span data-ttu-id="8a553-123">Para obtener más información, consulte [cómo usar el complemento de servidores](../core/how-to-use-the-servers-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="8a553-123">For more information, see [How to Use the Servers Snap-in](../core/how-to-use-the-servers-snap-in.md).</span></span>