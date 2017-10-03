---
title: "Cómo registrar un usuario remoto en una aplicación Local | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f638007c3c4eb1f85a5b5a701dd2b456c2d220d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a><span data-ttu-id="69df8-102">Cómo registrar un usuario remoto en una aplicación Local</span><span class="sxs-lookup"><span data-stu-id="69df8-102">How to Log a Remote User on to a Local Application</span></span>
<span data-ttu-id="69df8-103">La otra gran característica del servicio de inicio de sesión único empresarial (ENTSSO) es que admite un proceso iniciado por host (HIP).</span><span class="sxs-lookup"><span data-stu-id="69df8-103">The other main feature of Enterprise Single Sign-On service (ENTSSO) is supporting a host-initiated process (HIP).</span></span> <span data-ttu-id="69df8-104">ENTSSO interactúa con HIP cuando un usuario remoto intenta obtener acceso a un recurso local de Windows.</span><span class="sxs-lookup"><span data-stu-id="69df8-104">ENTSSO interacts with HIP when a remote user tries to access a local Windows resource.</span></span> <span data-ttu-id="69df8-105">Si utiliza ENTSSO, puede recibir la solicitud del usuario de host y solicitar acceso a la aplicación local de Windows.</span><span class="sxs-lookup"><span data-stu-id="69df8-105">Using ENTSSO, you can receive the request from the host user and request access to the local Windows application.</span></span>  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a><span data-ttu-id="69df8-106">Inicie sesión un usuario remoto en una aplicación de Windows local</span><span class="sxs-lookup"><span data-stu-id="69df8-106">Log a remote user on to a local Windows application</span></span>  
  
1.  <span data-ttu-id="69df8-107">Espere a recibir la solicitud del usuario remoto.</span><span class="sxs-lookup"><span data-stu-id="69df8-107">Receive the request from the remote user.</span></span>  
  
     <span data-ttu-id="69df8-108">Es responsabilidad suya determinar cómo obtener una solicitud del usuario remoto.</span><span class="sxs-lookup"><span data-stu-id="69df8-108">It is your responsibility to determine how to retrieve a request from the remote user.</span></span>  
  
2.  <span data-ttu-id="69df8-109">Solicite mediante `ISSOLookup2.LogonExternalUser` que se dé al usuario remoto acceso a la aplicación afiliada especificada.</span><span class="sxs-lookup"><span data-stu-id="69df8-109">Request that the remote user be given access to the specified affiliate application, using `ISSOLookup2.LogonExternalUser`.</span></span>  
  
     <span data-ttu-id="69df8-110">`LogonExternalUser` se transporta en el nombre de la aplicación a la que el usuario externo desea obtener acceso, en el nombre del usuario externo, en las credenciales asociadas al usuario externo y en cualquier marca pertinente.</span><span class="sxs-lookup"><span data-stu-id="69df8-110">`LogonExternalUser` passes in the name of the application the external user wishes to access, the name of the external user, the associated credentials for the external user, and any relevant flags.</span></span> <span data-ttu-id="69df8-111">Si se realiza correctamente, `LogonExternalUser` devuelve un identificador a un token de acceso de Windows.</span><span class="sxs-lookup"><span data-stu-id="69df8-111">If successful, `LogonExternalUser` returns a handle to a Windows access token.</span></span>  
  
     <span data-ttu-id="69df8-112">El usuario remoto debe estar identificado ya en la base de datos de inicio de sesión único (SSO), tener las credenciales en la base de datos y estar asociado con una aplicación afiliada.</span><span class="sxs-lookup"><span data-stu-id="69df8-112">The remote user must already be identified in the Single Sign-On database, have their credentials in the database, and be associated with an affiliate application.</span></span> <span data-ttu-id="69df8-113">En caso contrario, `LogonExternalUser` devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="69df8-113">Otherwise, `LogonExternalUser` returns an error.</span></span> <span data-ttu-id="69df8-114">Puede mantener los nombres y credenciales de usuario actualizados mediante Sincronización de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="69df8-114">You can keep the user names and credentials up to date using Password Sync.</span></span>  
  
     <span data-ttu-id="69df8-115">Además, debe tener habilitada la transición de protocolo.</span><span class="sxs-lookup"><span data-stu-id="69df8-115">In addition, you must have protocol transition enabled.</span></span>  
  
3.  <span data-ttu-id="69df8-116">Use el identificador de Windows que devuelve `LogonExternalUser` para suplantar al usuario que representa el token.</span><span class="sxs-lookup"><span data-stu-id="69df8-116">Use the Windows handle returned from `LogonExternalUser` to impersonate the user that the token represents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69df8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="69df8-117">See Also</span></span>  
 <span data-ttu-id="69df8-118">[Cómo registrar un usuario Local en una aplicación distinta de Windows](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="69df8-118">[How to Log a Local User on to a Non-Windows Application](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span></span>  
 <span data-ttu-id="69df8-119">**ISSOLookup2.LogonExternalUser (método)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="69df8-119">**ISSOLookup2.LogonExternalUser Method** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>