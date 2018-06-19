---
title: Antes de importar el módulo de administración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3c13dd-613a-4885-a5d2-ad3ee492ff25
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c11849c379a4654bed78a8e86ba263e6da428c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299452"
---
# <a name="before-you-import-the-management-pack"></a><span data-ttu-id="33e9f-102">Antes de importar el módulo de administración</span><span class="sxs-lookup"><span data-stu-id="33e9f-102">Before You Import the Management Pack</span></span>
<span data-ttu-id="33e9f-103">Como práctica recomendada, debe importar el módulo de administración de Windows Server para el sistema operativo que esté utilizando.</span><span class="sxs-lookup"><span data-stu-id="33e9f-103">As a best practice, you should import the Windows Server Management Pack for the operating system that you are using.</span></span> <span data-ttu-id="33e9f-104">Antes de importar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] módulo de administración, realice las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="33e9f-104">Before you import the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack, take the following actions:</span></span>  
  
-   <span data-ttu-id="33e9f-105">Asegúrese de que Operations Manager 2007 R2/2012 está instalado.</span><span class="sxs-lookup"><span data-stu-id="33e9f-105">Ensure that Operations Manager 2007 R2/2012 is installed.</span></span>  
  
-   <span data-ttu-id="33e9f-106">Debe ser miembro del grupo Administradores de SCOM o el grupo de autores de SCOM.</span><span class="sxs-lookup"><span data-stu-id="33e9f-106">You must be a member of either the SCOM Administrators group or the SCOM Authors group.</span></span> <span data-ttu-id="33e9f-107">Los administradores locales en el servidor de administración de SCOM tienen todos los derechos y permisos que se conceden al grupo de administradores de SCOM.</span><span class="sxs-lookup"><span data-stu-id="33e9f-107">Local administrators on the SCOM Management Server have all the rights and permissions that are granted to the SCOM Administrators group.</span></span>  
  
-   <span data-ttu-id="33e9f-108">Configurar los servidores BizTalk Server como los equipos administrados de Operations Manager mediante la implementación de los agentes de SCOM en cada servidor de BizTalk que desea administrar.</span><span class="sxs-lookup"><span data-stu-id="33e9f-108">Set up your BizTalk Servers as managed computers in Operations Manager by deploying the SCOM agents on each BizTalk Server that you want to manage.</span></span> <span data-ttu-id="33e9f-109">La implementación del agente SCOM implica las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="33e9f-109">The SCOM agent deployment involves the following tasks:</span></span>  
  
    -   <span data-ttu-id="33e9f-110">Instale al agente SCOM.</span><span class="sxs-lookup"><span data-stu-id="33e9f-110">Install the SCOM agent.</span></span>  
  
    -   <span data-ttu-id="33e9f-111">Cree una cuenta de agente de BizTalk SCOM.</span><span class="sxs-lookup"><span data-stu-id="33e9f-111">Create a BizTalk SCOM agent account.</span></span>  
  
    -   <span data-ttu-id="33e9f-112">Configurar un **ejecución** cuenta.</span><span class="sxs-lookup"><span data-stu-id="33e9f-112">Configure a **Run As** account.</span></span> <span data-ttu-id="33e9f-113">Agregue la cuenta de ejecución a los siguientes grupos:</span><span class="sxs-lookup"><span data-stu-id="33e9f-113">Add the Run As account to the following groups:</span></span>  
  
        -   <span data-ttu-id="33e9f-114">Grupos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="33e9f-114">BizTalk Groups.</span></span>  
  
        -   <span data-ttu-id="33e9f-115">Administradores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="33e9f-115">BizTalk Administrators.</span></span>  
  
        -   <span data-ttu-id="33e9f-116">Administradores SSO.</span><span class="sxs-lookup"><span data-stu-id="33e9f-116">SSO Administrators.</span></span>  
  
        -   <span data-ttu-id="33e9f-117">Administradores afiliados de SSO.</span><span class="sxs-lookup"><span data-stu-id="33e9f-117">SSO Affiliate Administrators.</span></span>  
  
    -   <span data-ttu-id="33e9f-118">Iniciar la supervisión.</span><span class="sxs-lookup"><span data-stu-id="33e9f-118">Initiate monitoring.</span></span>  
  
-   <span data-ttu-id="33e9f-119">En consola de Operations Manager, los equipos administrados se encuentran en un estado correcto.</span><span class="sxs-lookup"><span data-stu-id="33e9f-119">In Operation Manager Console, managed computers are in a healthy state.</span></span>  
  
-   <span data-ttu-id="33e9f-120">Configurar las cuentas de usuario que tienen que estar configurado, como perfiles ni requiere cuentas de ejecución.</span><span class="sxs-lookup"><span data-stu-id="33e9f-120">Configure any user accounts that have to be set up, such as any required Run As accounts or profiles.</span></span> <span data-ttu-id="33e9f-121">Este módulo de administración incluye perfiles de ejecución denominados "Cuenta de supervisión de BizTalk Server" y "Cuenta de detección de BizTalk Server" para definir credenciales específicas por agentes.</span><span class="sxs-lookup"><span data-stu-id="33e9f-121">This management pack includes Run As profiles named “BizTalk Server Monitoring Account” and “BizTalk Server Discovery Account” to define specific credentials on a per-agent basis.</span></span> <span data-ttu-id="33e9f-122">Es podrán que deba utilizar este perfil de ejecución para algunos agentes después de importar el módulo de administración.</span><span class="sxs-lookup"><span data-stu-id="33e9f-122">You may have to use this Run As profile for some agents after you import the management pack.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="33e9f-123">En esta sección</span><span class="sxs-lookup"><span data-stu-id="33e9f-123">In this section</span></span>  
  
-   [<span data-ttu-id="33e9f-124">Archivos de este módulo de administración</span><span class="sxs-lookup"><span data-stu-id="33e9f-124">Files in This Management Pack</span></span>](../technical-guides/files-in-this-management-pack.md)  
  
-   [<span data-ttu-id="33e9f-125">Módulos de administración adicionales recomendados</span><span class="sxs-lookup"><span data-stu-id="33e9f-125">Recommended Additional Management Packs</span></span>](../technical-guides/recommended-additional-management-packs.md)