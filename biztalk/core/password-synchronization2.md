---
title: Contraseña Synchronization2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9c12bc9ff5190fe0a76c92b1cfee2233b9d206a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264364"
---
# <a name="password-synchronization"></a><span data-ttu-id="cfe29-102">Sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cfe29-102">Password Synchronization</span></span>
<span data-ttu-id="cfe29-103">El propósito de la característica Sincronización de contraseñas es simplificar la administración de la base de datos de SSO y mantener las contraseñas sincronizadas entre directorios de usuario.</span><span class="sxs-lookup"><span data-stu-id="cfe29-103">The purpose of Password Synchronization is to simplify administration of the SSO database, and to keep passwords in sync across user directories.</span></span>  
  
 <span data-ttu-id="cfe29-104">Estas dos tareas se llevan a cabo mediante el uso de adaptadores de sincronización de contraseñas, y los temas de esta sección explican la utilidad de línea de comandos para crear y administrar esos adaptadores.</span><span class="sxs-lookup"><span data-stu-id="cfe29-104">These two tasks are accomplished through the use of password synchronization adapters, and the topics in this section describe the command line utility for creating and managing those adapters.</span></span>  
  
 <span data-ttu-id="cfe29-105">Hay tres tipos de subcaracterísticas de sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="cfe29-105">There are three types of password synchronization sub-features.</span></span>  
  
 <span data-ttu-id="cfe29-106">El primer tipo es **Windows a externo** (por ejemplo, Active Directory a RACF).</span><span class="sxs-lookup"><span data-stu-id="cfe29-106">The first type is **Windows to External** (for example, Active Directory to RACF).</span></span> <span data-ttu-id="cfe29-107">En este escenario, se captura un cambio de contraseña de usuario de Windows y se envía al servidor de SSO empresarial asignado para recibir cambios de contraseña de controladores de dominio.</span><span class="sxs-lookup"><span data-stu-id="cfe29-107">In this scenario, a Windows user's password change is captured and sent to the Enterprise SSO Server assigned to receive password changes from domain controllers.</span></span> <span data-ttu-id="cfe29-108">Después se reenvía el cambio de contraseña a un sistema externo y la asignación en la base de datos de SSO se mantiene en sincronización con el cambio realizado en el sistema externo.</span><span class="sxs-lookup"><span data-stu-id="cfe29-108">This then forwards the password change to an external system and the mapping in the SSO database is kept in sync with the change made on the external system.</span></span>  
  
 <span data-ttu-id="cfe29-109">El segundo tipo es **externo a Windows, sincronización completa**.</span><span class="sxs-lookup"><span data-stu-id="cfe29-109">The second type is **External to Windows - Full synchronization**.</span></span> <span data-ttu-id="cfe29-110">En este escenario, se captura una contraseña en el sistema externo y se envía al servidor de inicio de sesión único empresarial asignado para la sincronización de contraseñas, que a su vez actualiza la contraseña en la base de datos de SSO, y también actualiza la contraseña de usuario de Windows en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cfe29-110">In this scenario, a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database, and also updates the Windows user's password in Active Directory.</span></span>  
  
 <span data-ttu-id="cfe29-111">El tercer tipo es **externo a Windows, sincronización parcial**.</span><span class="sxs-lookup"><span data-stu-id="cfe29-111">The third type is **External to Windows - Partial synchronization**.</span></span> <span data-ttu-id="cfe29-112">En este escenario, se captura una contraseña en el sistema externo y se envía al servidor de inicio de sesión único empresarial asignado para la sincronización de contraseñas, que a su vez actualiza la contraseña en la base de datos de SSO.</span><span class="sxs-lookup"><span data-stu-id="cfe29-112">In this scenario a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cfe29-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cfe29-113">In This Section</span></span>  
  
-   [<span data-ttu-id="cfe29-114">Cómo instalar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cfe29-114">How to Install Password Synchronization</span></span>](../core/how-to-install-password-synchronization.md)  
  
-   [<span data-ttu-id="cfe29-115">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cfe29-115">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   [<span data-ttu-id="cfe29-116">Cómo configurar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cfe29-116">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="cfe29-117">Cómo administrar la sincronización de contraseña</span><span class="sxs-lookup"><span data-stu-id="cfe29-117">How to Manage Password Synchronization</span></span>](../core/how-to-manage-password-synchronization.md)