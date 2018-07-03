---
title: Administración de Hosts y cuentas de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, managing
- managing [user accounts]
- service accounts, security
- managing [hosts], security
- security, hosts
- managing [Windows groups]
- hosts, security
- security, service accounts
- Windows groups, managing
- user accounts, managing
ms.assetid: 25797571-f1f9-42a4-8fff-5b03076bbe36
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0f33a484d67981bb72908243b82e7835e0390e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016118"
---
# <a name="managing-hosts-and-service-accounts"></a><span data-ttu-id="219eb-102">Administrar hosts y cuentas de servicio</span><span class="sxs-lookup"><span data-stu-id="219eb-102">Managing Hosts and Service Accounts</span></span>
<span data-ttu-id="219eb-103">Después de configurar BizTalk Server, tendrá que administrar grupos de Windows y cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="219eb-103">After you configure BizTalk Server, you must manage Windows groups and user accounts.</span></span> <span data-ttu-id="219eb-104">En esta sección se proporciona información acerca de cómo administrar estas cuentas para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="219eb-104">This section provides information about how to manage these accounts for BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="219eb-105">Para una instalación multiservidor de BizTalk Server, tendrá que utilizar un grupo global de dominio.</span><span class="sxs-lookup"><span data-stu-id="219eb-105">For a multiserver installation of BizTalk Server you must use a Domain Global group.</span></span> <span data-ttu-id="219eb-106">Para una instalación de un solo servidor de BizTalk Server, podrá utilizar un grupo global de dominio o un grupo local.</span><span class="sxs-lookup"><span data-stu-id="219eb-106">For a single server installation of BizTalk Server you can use either a Domain Global group or a local group.</span></span>  
  
 <span data-ttu-id="219eb-107">Para realizar las tareas siguientes, tendrá que ser un administrador de Windows:</span><span class="sxs-lookup"><span data-stu-id="219eb-107">You must be a Windows administrator to perform the following tasks:</span></span>  
  
- <span data-ttu-id="219eb-108">Crear un grupo de Windows de host</span><span class="sxs-lookup"><span data-stu-id="219eb-108">Create a host Windows group</span></span>  
  
- <span data-ttu-id="219eb-109">Crear cuentas de servicio para cada instancia de host</span><span class="sxs-lookup"><span data-stu-id="219eb-109">Create service accounts for each host instance</span></span>  
  
- <span data-ttu-id="219eb-110">Agregar cuentas de servicio al grupo de Windows de host</span><span class="sxs-lookup"><span data-stu-id="219eb-110">Add the service accounts to the host Windows group</span></span>  
  
- <span data-ttu-id="219eb-111">Modificar el grupo de Windows asociado al host</span><span class="sxs-lookup"><span data-stu-id="219eb-111">Modify the Windows group associated with the host</span></span>  
  
  <span data-ttu-id="219eb-112">Para una lista completa y una descripción de los grupos y sus cuentas de usuarios afiliados en BizTalk Server, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="219eb-112">For a complete list and description of the groups and their affiliated user accounts in the BizTalk Server, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="219eb-113">Para obtener más información de derechos de usuario mínimos de seguridad para las tareas administrativas, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).</span><span class="sxs-lookup"><span data-stu-id="219eb-113">For more information the minimum security user rights for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="219eb-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="219eb-114">In This Section</span></span>  
  
-   [<span data-ttu-id="219eb-115">Cómo crear el servicio de cuentas para nuevos Hosts e instancias de Host</span><span class="sxs-lookup"><span data-stu-id="219eb-115">How to Create Service Accounts for New Hosts and Host Instances</span></span>](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [<span data-ttu-id="219eb-116">Cómo cambiar contraseñas y cuentas de servicio</span><span class="sxs-lookup"><span data-stu-id="219eb-116">How to Change Service Accounts and Passwords</span></span>](../core/how-to-change-service-accounts-and-passwords.md)