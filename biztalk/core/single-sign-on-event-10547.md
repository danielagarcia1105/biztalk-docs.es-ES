---
title: "Inicio de sesión único: Evento 10547 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6162461b1eb04993ca681049fe1fbb797ca014
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10547"></a><span data-ttu-id="05d50-102">Inicio de sesión único: Evento 10547</span><span class="sxs-lookup"><span data-stu-id="05d50-102">Single Sign-On: Event 10547</span></span>
## <a name="details"></a><span data-ttu-id="05d50-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="05d50-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="05d50-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="05d50-104">Product Name</span></span>|<span data-ttu-id="05d50-105">Inicio de sesión único (SSO) empresarial</span><span class="sxs-lookup"><span data-stu-id="05d50-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="05d50-106">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="05d50-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="05d50-107">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="05d50-107">Event ID</span></span>|<span data-ttu-id="05d50-108">10547</span><span class="sxs-lookup"><span data-stu-id="05d50-108">10547</span></span>|  
|<span data-ttu-id="05d50-109">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="05d50-109">Event Source</span></span>|<span data-ttu-id="05d50-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="05d50-110">ENTSSO</span></span>|  
|<span data-ttu-id="05d50-111">Componente</span><span class="sxs-lookup"><span data-stu-id="05d50-111">Component</span></span>|<span data-ttu-id="05d50-112">CO</span><span class="sxs-lookup"><span data-stu-id="05d50-112">CO</span></span>|  
|<span data-ttu-id="05d50-113">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="05d50-113">Symbolic Name</span></span>|<span data-ttu-id="05d50-114">SSO_WARN_UPDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="05d50-114">SSO_WARN_UPDATE_FAILED</span></span>|  
|<span data-ttu-id="05d50-115">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="05d50-115">Message Text</span></span>|<span data-ttu-id="05d50-116">No se pudieron actualizar las credenciales en la base de datos de SSO durante el recifrado.</span><span class="sxs-lookup"><span data-stu-id="05d50-116">Failed to update the credentials in the SSO database during re-encryption</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="05d50-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="05d50-117">Explanation</span></span>  
 <span data-ttu-id="05d50-118">Este evento de advertencia indica que no fue posible actualizar las credenciales con el resultado del nuevo cifrado.</span><span class="sxs-lookup"><span data-stu-id="05d50-118">This Warning event indicates that it was not possible to update the credentials with the result of the new encryption.</span></span> <span data-ttu-id="05d50-119">Cuando se cambia el secreto principal, ya sea al generar un secreto nuevo o al restaurar un secreto anterior, se vuelve a realizar el cifrado en la base de datos de SSO para descifrar todos los servicios cifrados con el secreto anterior y volver a cifrarlos con el secreto nuevo.</span><span class="sxs-lookup"><span data-stu-id="05d50-119">When the master secret is changed, either by generating a new secret or by restoring an old secret, a re-encryption is performed on the SSO database to decrypt all the secrets encrypted with the old secret, and re-encrypt them with the new secret.</span></span> <span data-ttu-id="05d50-120">Este evento puede producirse si las credenciales se eliminaron debido a que estaban en proceso de ser cifradas nuevamente.</span><span class="sxs-lookup"><span data-stu-id="05d50-120">This event can occur if the credentials were deleted as they were in the process of being re-encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="05d50-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="05d50-121">User Action</span></span>  
 <span data-ttu-id="05d50-122">Para resolver esta advertencia, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05d50-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="05d50-123">Espere a que se produzca otro recifrado después de un breve retardo, si esto no se produce automáticamente, reinicie el servicio SSO que desencadenará un nuevo recifrado si es necesario.</span><span class="sxs-lookup"><span data-stu-id="05d50-123">Wait for another re-encryption to occur after a short delay; if that does not occur automatically, restart the SSO service which will trigger a new re-encryption if one is required.</span></span>  
  
 <span data-ttu-id="05d50-124">Para obtener más información, consulte los siguientes recursos en la Ayuda de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="05d50-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="05d50-125">Entendiendo SSO</span><span class="sxs-lookup"><span data-stu-id="05d50-125">Understanding SSO</span></span>](../core/understanding-sso.md)