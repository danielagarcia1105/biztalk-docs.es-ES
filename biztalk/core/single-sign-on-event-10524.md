---
title: 'De sesión único: Evento 10524 | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55e26da3-f67f-4f87-92e5-2f8765b19989
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f873dab5d4d5f00897e498e2bb88b6ae9a2f040
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009509"
---
# <a name="single-sign-on-event-10524"></a><span data-ttu-id="5d442-102">De sesión único: Evento 10524</span><span class="sxs-lookup"><span data-stu-id="5d442-102">Single Sign-On: Event 10524</span></span>
## <a name="details"></a><span data-ttu-id="5d442-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d442-103">Details</span></span>  

|                 |                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5d442-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="5d442-104">Product Name</span></span>   |                                                                                  <span data-ttu-id="5d442-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="5d442-105">Enterprise Single Sign-On</span></span>                                                                                  |
| <span data-ttu-id="5d442-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="5d442-106">Product Version</span></span> |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                  |
|    <span data-ttu-id="5d442-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="5d442-107">Event ID</span></span>     |                                                                                            <span data-ttu-id="5d442-108">10524</span><span class="sxs-lookup"><span data-stu-id="5d442-108">10524</span></span>                                                                                            |
|  <span data-ttu-id="5d442-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="5d442-109">Event Source</span></span>   |                                                                                           <span data-ttu-id="5d442-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5d442-110">ENTSSO</span></span>                                                                                            |
|    <span data-ttu-id="5d442-111">Componente</span><span class="sxs-lookup"><span data-stu-id="5d442-111">Component</span></span>    |                                                                                             <span data-ttu-id="5d442-112">N\D</span><span class="sxs-lookup"><span data-stu-id="5d442-112">N\A</span></span>                                                                                             |
|  <span data-ttu-id="5d442-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5d442-113">Symbolic Name</span></span>  |                                                                               <span data-ttu-id="5d442-114">SSO_ERROR_RESTORE_SECRET_FAILED</span><span class="sxs-lookup"><span data-stu-id="5d442-114">SSO_ERROR_RESTORE_SECRET_FAILED</span></span>                                                                               |
|  <span data-ttu-id="5d442-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5d442-115">Message Text</span></span>   | <span data-ttu-id="5d442-116">No se pudieron restaurar los secretos principales.%r</span><span class="sxs-lookup"><span data-stu-id="5d442-116">Failed to restore the master secrets.%r</span></span><br /><br /> <span data-ttu-id="5d442-117">Nombre de archivo: %1 %r</span><span class="sxs-lookup"><span data-stu-id="5d442-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="5d442-118">MSID actual: %2 %r</span><span class="sxs-lookup"><span data-stu-id="5d442-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="5d442-119">MSID anterior: %3 %r</span><span class="sxs-lookup"><span data-stu-id="5d442-119">Previous MSID: %3%r</span></span><br /><br /> <span data-ttu-id="5d442-120">Usuario cliente: %4 %r</span><span class="sxs-lookup"><span data-stu-id="5d442-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="5d442-121">Código de error: %5</span><span class="sxs-lookup"><span data-stu-id="5d442-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="5d442-122">Explicación</span><span class="sxs-lookup"><span data-stu-id="5d442-122">Explanation</span></span>  
 <span data-ttu-id="5d442-123">Este evento de error indica que un usuario está intentando restaurar los secretos principales desde un archivo de copia de seguridad con error.</span><span class="sxs-lookup"><span data-stu-id="5d442-123">This Error event indicates that a user attempt to restore the master secrets from a backup file failed.</span></span> <span data-ttu-id="5d442-124">Esto puede deberse a problemas de permisos (se debe ser un administrador de SSO para restaurar el secreto principal) o es posible que el archivo de copia de seguridad esté dañado.</span><span class="sxs-lookup"><span data-stu-id="5d442-124">This might be due to permissions issues (you must be an SSO Administrator to restore the master secret) or possibly due to file corruption of the backup file.</span></span> <span data-ttu-id="5d442-125">En estos casos, debería haber mensajes relacionados en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5d442-125">In these cases there should be related messages in the Application event log.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5d442-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5d442-126">User Action</span></span>  
 <span data-ttu-id="5d442-127">Para resolver este error, realice una o varias de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5d442-127">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="5d442-128">Compruebe si el registro de eventos de la aplicación contiene eventos o errores asociados.</span><span class="sxs-lookup"><span data-stu-id="5d442-128">Check the Application event log for associated events or errors.</span></span>  

- <span data-ttu-id="5d442-129">Compruebe si dispone de los permisos de administrador de SSO correspondientes.</span><span class="sxs-lookup"><span data-stu-id="5d442-129">Check that you have the appropriate SSO Administrator permissions.</span></span>  

  <span data-ttu-id="5d442-130">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="5d442-130">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="5d442-131">Cómo restaurar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="5d442-131">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  

- [<span data-ttu-id="5d442-132">Cómo realizar copias de seguridad del secreto principal</span><span class="sxs-lookup"><span data-stu-id="5d442-132">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  

- [<span data-ttu-id="5d442-133">Cómo generar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="5d442-133">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)
