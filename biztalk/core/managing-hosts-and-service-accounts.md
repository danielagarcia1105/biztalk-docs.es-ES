---
title: Administración de Hosts y las cuentas de servicio | Documentos de Microsoft
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
ms.openlocfilehash: 0099e683fba7c5f4e2400ad2f9ce005928b0a2aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262388"
---
# <a name="managing-hosts-and-service-accounts"></a><span data-ttu-id="dbbef-102">Administrar hosts y cuentas de servicio</span><span class="sxs-lookup"><span data-stu-id="dbbef-102">Managing Hosts and Service Accounts</span></span>
<span data-ttu-id="dbbef-103">Después de configurar BizTalk Server, tendrá que administrar grupos de Windows y cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="dbbef-103">After you configure BizTalk Server, you must manage Windows groups and user accounts.</span></span> <span data-ttu-id="dbbef-104">En esta sección se proporciona información acerca de cómo administrar estas cuentas para BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="dbbef-104">This section provides information about how to manage these accounts for BizTalk Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbbef-105">Para una instalación multiservidor de BizTalk Server, tendrá que utilizar un grupo global de dominio.</span><span class="sxs-lookup"><span data-stu-id="dbbef-105">For a multiserver installation of BizTalk Server you must use a Domain Global group.</span></span> <span data-ttu-id="dbbef-106">Para una instalación de un solo servidor de BizTalk Server, podrá utilizar un grupo global de dominio o un grupo local.</span><span class="sxs-lookup"><span data-stu-id="dbbef-106">For a single server installation of BizTalk Server you can use either a Domain Global group or a local group.</span></span>  
  
 <span data-ttu-id="dbbef-107">Para realizar las tareas siguientes, tendrá que ser un administrador de Windows:</span><span class="sxs-lookup"><span data-stu-id="dbbef-107">You must be a Windows administrator to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="dbbef-108">Crear un grupo de Windows de host</span><span class="sxs-lookup"><span data-stu-id="dbbef-108">Create a host Windows group</span></span>  
  
-   <span data-ttu-id="dbbef-109">Crear cuentas de servicio para cada instancia de host</span><span class="sxs-lookup"><span data-stu-id="dbbef-109">Create service accounts for each host instance</span></span>  
  
-   <span data-ttu-id="dbbef-110">Agregar cuentas de servicio al grupo de Windows de host</span><span class="sxs-lookup"><span data-stu-id="dbbef-110">Add the service accounts to the host Windows group</span></span>  
  
-   <span data-ttu-id="dbbef-111">Modificar el grupo de Windows asociado al host</span><span class="sxs-lookup"><span data-stu-id="dbbef-111">Modify the Windows group associated with the host</span></span>  
  
 <span data-ttu-id="dbbef-112">Para una lista completa y una descripción de los grupos y sus cuentas de usuarios afiliados en BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="dbbef-112">For a complete list and description of the groups and their affiliated user accounts in the BizTalk Server, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="dbbef-113">Para obtener más información de derechos de usuario mínimos de seguridad para tareas administrativas, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).</span><span class="sxs-lookup"><span data-stu-id="dbbef-113">For more information the minimum security user rights for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dbbef-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dbbef-114">In This Section</span></span>  
  
-   [<span data-ttu-id="dbbef-115">Cómo crear servicio cuentas para nuevos Hosts e instancias de Host</span><span class="sxs-lookup"><span data-stu-id="dbbef-115">How to Create Service Accounts for New Hosts and Host Instances</span></span>](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [<span data-ttu-id="dbbef-116">Cómo cambiar contraseñas y cuentas de servicio</span><span class="sxs-lookup"><span data-stu-id="dbbef-116">How to Change Service Accounts and Passwords</span></span>](../core/how-to-change-service-accounts-and-passwords.md)