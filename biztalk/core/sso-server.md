---
title: Servidor de SSO | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f2f24911a0336a734125436d97dbce6f9e0b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sso-server"></a><span data-ttu-id="f5f39-102">Servidor de SSO</span><span class="sxs-lookup"><span data-stu-id="f5f39-102">SSO Server</span></span>
<span data-ttu-id="f5f39-103">El servidor de inicio de sesión único (SSO) empresarial puede realizar cualquiera de las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5f39-103">The Enterprise Single Sign-On (SSO) server can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="f5f39-104">**Funciones como el servidor secreto principal.**</span><span class="sxs-lookup"><span data-stu-id="f5f39-104">**Functions as the master secret server.**</span></span> <span data-ttu-id="f5f39-105">El servidor secreto principal contiene una copia persistida del secreto o clave principal que se utiliza para cifrar las credenciales en el sistema de SSO.</span><span class="sxs-lookup"><span data-stu-id="f5f39-105">The master secret server holds a persisted copy of the master secret, or key, used to encrypt all the credentials in the SSO system.</span></span> <span data-ttu-id="f5f39-106">Aunque el servidor secreto principal puede actuar como servidor para búsquedas y administración, por motivos de seguridad se recomienda que utilice este servidor para actuar sólo como servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="f5f39-106">Though the master secret server can act as a server for lookups and administration, it is recommended to use this server to act only as a master secret server for security reasons.</span></span> <span data-ttu-id="f5f39-107">Para obtener más información acerca de las funciones que realiza el servidor secreto principal, consulte [servidor secreto principal](../core/master-secret-server.md).</span><span class="sxs-lookup"><span data-stu-id="f5f39-107">For more information about the functions the master secret server performs, see [Master Secret Server](../core/master-secret-server.md).</span></span>  
  
-   <span data-ttu-id="f5f39-108">**Realiza operaciones administrativas.**</span><span class="sxs-lookup"><span data-stu-id="f5f39-108">**Performs administrative operations.**</span></span> <span data-ttu-id="f5f39-109">Los administradores de SSO pueden utilizar cualquier servidor de inicio de sesión único para realizar tareas administrativas, como administrar aplicaciones afiliadas, establecer credenciales de usuario y que administrar asignaciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="f5f39-109">SSO administrators can use any of the Single Sign-On Servers to perform administrative tasks such as managing affiliate applications, setting user credentials, and managing user mappings.</span></span>  
  
-   <span data-ttu-id="f5f39-110">**Realiza operaciones de búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="f5f39-110">**Performs lookup operations.**</span></span> <span data-ttu-id="f5f39-111">El servidor de SSO utiliza el componente de tiempo de ejecución para buscar las credenciales de usuario.</span><span class="sxs-lookup"><span data-stu-id="f5f39-111">The SSO server uses the runtime component to look up the user credentials.</span></span>  
  
-   <span data-ttu-id="f5f39-112">**Emite y canjea vales.**</span><span class="sxs-lookup"><span data-stu-id="f5f39-112">**Issues and Redeems Tickets.**</span></span> <span data-ttu-id="f5f39-113">El servidor de SSO también emite y canjea vales de SSO.</span><span class="sxs-lookup"><span data-stu-id="f5f39-113">The SSO server also issues and redeems SSO tickets.</span></span>  
  
-   <span data-ttu-id="f5f39-114">**Sincronización de contraseñas.**</span><span class="sxs-lookup"><span data-stu-id="f5f39-114">**Password Synchronization.**</span></span> <span data-ttu-id="f5f39-115">Puede crear y administrar adaptadores de sincronización de contraseñas en el servidor de SSO.</span><span class="sxs-lookup"><span data-stu-id="f5f39-115">You can create and manage password synchronization adapters on the SSO Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f39-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5f39-116">See Also</span></span>  
 <span data-ttu-id="f5f39-117">[Uso de SSO](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="f5f39-117">[Using SSO](../core/using-sso.md) </span></span>  
 [<span data-ttu-id="f5f39-118">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="f5f39-118">Installing SSO</span></span>](../core/installing-sso.md)