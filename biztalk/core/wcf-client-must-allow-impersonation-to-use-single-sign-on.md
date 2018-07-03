---
title: Cliente de WCF debe permitir la suplantación utilice Single Sign-On | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5b9f294-4d8a-4a12-91e8-8d325db7c420
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2d5ebfc9853f10417c1d2ad2c41a0d2531ff6de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971477"
---
# <a name="wcf-client-must-allow-impersonation-to-use-single-sign-on"></a><span data-ttu-id="6542a-102">El cliente de WCF debe permitir que la Suplantación utilice el inicio de sesión único</span><span class="sxs-lookup"><span data-stu-id="6542a-102">WCF client must allow impersonation to use Single Sign-On</span></span>
## <a name="details"></a><span data-ttu-id="6542a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6542a-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="6542a-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="6542a-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="6542a-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="6542a-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="6542a-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="6542a-106">Event ID</span></span>     |                                         <span data-ttu-id="6542a-107">0</span><span class="sxs-lookup"><span data-stu-id="6542a-107">0</span></span>                                          |
|  <span data-ttu-id="6542a-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="6542a-108">Event Source</span></span>   |                                         <span data-ttu-id="6542a-109">0</span><span class="sxs-lookup"><span data-stu-id="6542a-109">0</span></span>                                          |
|    <span data-ttu-id="6542a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6542a-110">Component</span></span>    |                                         <span data-ttu-id="6542a-111">0</span><span class="sxs-lookup"><span data-stu-id="6542a-111">0</span></span>                                          |
|  <span data-ttu-id="6542a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6542a-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="6542a-113">0</span><span class="sxs-lookup"><span data-stu-id="6542a-113">0</span></span>                                          |
|  <span data-ttu-id="6542a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6542a-114">Message Text</span></span>   |           <span data-ttu-id="6542a-115">El cliente de WCF debe permitir que la Suplantación utilice el inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="6542a-115">The WCF client must allow impersonation to use Single Sign-On</span></span>            |

## <a name="explanation"></a><span data-ttu-id="6542a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="6542a-116">Explanation</span></span>  
 <span data-ttu-id="6542a-117">El inicio de sesión único (SSO) está habilitado en la ubicación de recepción pero el cliente de WCF no permite la suplantación.</span><span class="sxs-lookup"><span data-stu-id="6542a-117">Single Sign-On (SSO) is enabled in the receive location but the WCF client does not allow impersonation.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6542a-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6542a-118">User Action</span></span>  
 <span data-ttu-id="6542a-119">Asegúrese de que el cliente de WCF que invoca el servicio permita la suplantación.</span><span class="sxs-lookup"><span data-stu-id="6542a-119">Ensure that the WCF client invoking the service allows impersonation.</span></span>  

1. <span data-ttu-id="6542a-120">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="6542a-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="6542a-121">En la raíz de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="6542a-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="6542a-122">Busque la aplicación y, a continuación, busque su transporte.</span><span class="sxs-lookup"><span data-stu-id="6542a-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="6542a-123">Haga clic con el botón secundario en el nombre del transporte.</span><span class="sxs-lookup"><span data-stu-id="6542a-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="6542a-124">Haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6542a-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="6542a-125">En el puerto **tipo** lista, seleccione **WCF-Custom** (o **WCF-CustomIsolate**).</span><span class="sxs-lookup"><span data-stu-id="6542a-125">In the port **Type** list, select **WCF-Custom** (or **WCF-CustomIsolate**).</span></span>  

7. <span data-ttu-id="6542a-126">Haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="6542a-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="6542a-127">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **comportamiento** ficha.</span><span class="sxs-lookup"><span data-stu-id="6542a-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="6542a-128">En el **comportamiento** sección, haga clic en **ServiceAuthorization**.</span><span class="sxs-lookup"><span data-stu-id="6542a-128">In the **Behavior** section, click **ServiceAuthorization**.</span></span> <span data-ttu-id="6542a-129">En el **configuración** sección, la propiedad **ImpersonateCallerForAllOperations** debe establecerse en **True**.</span><span class="sxs-lookup"><span data-stu-id="6542a-129">In the **Configuration** section, the property **ImpersonateCallerForAllOperations** should be set to **True**.</span></span>  

10. <span data-ttu-id="6542a-130">En el **WCF [**<em>tipo de transporte</em>**] propiedades de transporte** cuadro de diálogo, haga clic en el **otros** ficha.</span><span class="sxs-lookup"><span data-stu-id="6542a-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Other** tab.</span></span>  

11. <span data-ttu-id="6542a-131">En las secciones credenciales, seleccione la opción **Use Single Sign-On**.</span><span class="sxs-lookup"><span data-stu-id="6542a-131">In the Credentials sections, select the option **Use Single Sign-On**.</span></span>
