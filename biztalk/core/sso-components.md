---
title: Componentes de SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1111f1a0dfac47412ae28b58f93ddc51e1f562b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276476"
---
# <a name="sso-components"></a><span data-ttu-id="1468d-102">Componentes de SSO</span><span class="sxs-lookup"><span data-stu-id="1468d-102">SSO Components</span></span>
<span data-ttu-id="1468d-103">Los subservicios del servicio de inicio de sesión único (SSO) empresarial son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1468d-103">The sub services of the Enterprise Single Sign-On (SSO) service are as follows:</span></span>  
  
-   <span data-ttu-id="1468d-104">**Asignación.**</span><span class="sxs-lookup"><span data-stu-id="1468d-104">**Mapping.**</span></span> <span data-ttu-id="1468d-105">Este componente asigna la cuenta de usuario en el sistema de Windows a cuentas de usuarios de los sistemas de servidor.</span><span class="sxs-lookup"><span data-stu-id="1468d-105">This component maps the user account in the Windows system to the user accounts in the back-end systems.</span></span>  
  
-   <span data-ttu-id="1468d-106">**Búsqueda.**</span><span class="sxs-lookup"><span data-stu-id="1468d-106">**Lookup.**</span></span> <span data-ttu-id="1468d-107">Este componente busca las credenciales de usuario en la base de datos de SSO en el sistema de servidor.</span><span class="sxs-lookup"><span data-stu-id="1468d-107">This component looks up the user credentials in the SSO database in the back-end system.</span></span> <span data-ttu-id="1468d-108">Éste es el componente en tiempo de ejecución de SSO.</span><span class="sxs-lookup"><span data-stu-id="1468d-108">This is the SSO runtime component.</span></span>  
  
-   <span data-ttu-id="1468d-109">**Administración.**</span><span class="sxs-lookup"><span data-stu-id="1468d-109">**Administration.**</span></span> <span data-ttu-id="1468d-110">Este componente administra las aplicaciones afiliadas y las asignaciones para cada aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="1468d-110">This component manages the affiliate applications and the mappings for each affiliate application.</span></span>  
  
-   <span data-ttu-id="1468d-111">**Secreto.**</span><span class="sxs-lookup"><span data-stu-id="1468d-111">**Secret.**</span></span> <span data-ttu-id="1468d-112">Este componente genera el secreto principal y lo distribuye a los servidores de SSO del sistema.</span><span class="sxs-lookup"><span data-stu-id="1468d-112">This component generates the master secret and distributes it to the other SSO servers in the system.</span></span> <span data-ttu-id="1468d-113">Sólo está activo en el servidor de inicio de sesión único (SSO) que actúa como servidor secreto principal.</span><span class="sxs-lookup"><span data-stu-id="1468d-113">It is only active on the Single Sign-On server that is acting as the master secret server.</span></span>  
  
-   <span data-ttu-id="1468d-114">**Sincronización de contraseñas.**</span><span class="sxs-lookup"><span data-stu-id="1468d-114">**Password Synchronization.**</span></span> <span data-ttu-id="1468d-115">Este componente simplifica la administración de la base de datos de SSO y sincroniza las contraseñas en todos los directorios de usuario.</span><span class="sxs-lookup"><span data-stu-id="1468d-115">This component simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1468d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1468d-116">See Also</span></span>  
 <span data-ttu-id="1468d-117">[Servidor de SSO](../core/sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="1468d-117">[SSO Server](../core/sso-server.md) </span></span>  
 [<span data-ttu-id="1468d-118">Instalación de SSO</span><span class="sxs-lookup"><span data-stu-id="1468d-118">Installing SSO</span></span>](../core/installing-sso.md)