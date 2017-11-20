---
title: Usar SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO]
- SSO, managing
ms.assetid: e7245632-9c71-4b1f-836d-a4ea1dd6e5ee
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850425f140b526baf251568f09ab47db9115e8ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-sso"></a><span data-ttu-id="39616-102">Uso de SSO</span><span class="sxs-lookup"><span data-stu-id="39616-102">Using SSO</span></span>
<span data-ttu-id="39616-103">Puede utilizar el Complemento MMC o la utilidad de administración de líneas de comandos (ssomanage) para administrar el sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="39616-103">You can use either the MMC Snap-in or the command line management utility (ssomanage) to manage the SSO system.</span></span> <span data-ttu-id="39616-104">Esto incluye actividades tales como la actualización de la base de datos de SSO, la adición, eliminación y administración de aplicaciones o la administración de asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="39616-104">This includes activities such as updating the SSO database, adding, deleting, and managing applications, and administering user mappings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="39616-105">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar las herramientas de línea de comandos de SSO con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="39616-105">On a system that supports User Account Control (UAC), you may need to run the SSO command line tools with Administrative privileges.</span></span>  
  
 <span data-ttu-id="39616-106">Sólo los administradores de inicio de sesión único (SSO) pueden llevar a cabo estas tareas.</span><span class="sxs-lookup"><span data-stu-id="39616-106">Only Single Sign-On Administrators can perform these tasks.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39616-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="39616-107">In This Section</span></span>  
  
-   [<span data-ttu-id="39616-108">Cómo establecer el servidor de SSO</span><span class="sxs-lookup"><span data-stu-id="39616-108">How to Set the SSO Server</span></span>](../core/how-to-set-the-sso-server.md)  
  
-   [<span data-ttu-id="39616-109">Cómo habilitar SSO</span><span class="sxs-lookup"><span data-stu-id="39616-109">How to Enable SSO</span></span>](../core/how-to-enable-sso.md)  
  
-   [<span data-ttu-id="39616-110">Cómo cambiar el servidor secreto principal</span><span class="sxs-lookup"><span data-stu-id="39616-110">How to Change the Master Secret Server</span></span>](../core/how-to-change-the-master-secret-server.md)  
  
-   [<span data-ttu-id="39616-111">Cómo deshabilitar SSO</span><span class="sxs-lookup"><span data-stu-id="39616-111">How to Disable SSO</span></span>](../core/how-to-disable-sso.md)  
  
-   [<span data-ttu-id="39616-112">Cómo actualizar la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="39616-112">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  
  
-   [<span data-ttu-id="39616-113">Cómo mostrar la información de la base de datos SSO</span><span class="sxs-lookup"><span data-stu-id="39616-113">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
-   [<span data-ttu-id="39616-114">Cómo configurar los vales de SSO</span><span class="sxs-lookup"><span data-stu-id="39616-114">How to Configure the SSO Tickets</span></span>](../core/how-to-configure-the-sso-tickets.md)  
  
-   [<span data-ttu-id="39616-115">Cómo auditar SSO</span><span class="sxs-lookup"><span data-stu-id="39616-115">How to Audit SSO</span></span>](../core/how-to-audit-sso.md)  
  
-   [<span data-ttu-id="39616-116">Cómo habilitar SSL para SSO</span><span class="sxs-lookup"><span data-stu-id="39616-116">How to Enable SSL for SSO</span></span>](../core/how-to-enable-ssl-for-sso.md)  
  
-   [<span data-ttu-id="39616-117">Administrar el secreto principal</span><span class="sxs-lookup"><span data-stu-id="39616-117">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="39616-118">Cómo especificar administradores de SSO y los administradores afiliados de cuentas</span><span class="sxs-lookup"><span data-stu-id="39616-118">How to Specify SSO Administrators and Affiliate Administrators Accounts</span></span>](../core/how-to-specify-sso-administrators-and-affiliate-administrators-accounts.md)  
  
-   [<span data-ttu-id="39616-119">Administrar aplicaciones afiliadas</span><span class="sxs-lookup"><span data-stu-id="39616-119">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)  
  
-   [<span data-ttu-id="39616-120">Administrar asignaciones de usuario</span><span class="sxs-lookup"><span data-stu-id="39616-120">Managing User Mappings</span></span>](../core/managing-user-mappings.md)  
  
-   [<span data-ttu-id="39616-121">SSO iniciado por host</span><span class="sxs-lookup"><span data-stu-id="39616-121">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)