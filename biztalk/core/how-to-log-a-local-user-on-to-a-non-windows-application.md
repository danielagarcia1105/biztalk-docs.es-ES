---
title: Cómo registrar un usuario Local en una aplicación distinta de Windows | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55957f4-22c4-48b5-827a-ab41d8f846ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3c2e9ffaede20e29987938a436ad2a091920fce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253876"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a><span data-ttu-id="02d3d-102">Cómo registrar un usuario Local en una aplicación distinta de Windows</span><span class="sxs-lookup"><span data-stu-id="02d3d-102">How to Log a Local User on to a Non-Windows Application</span></span>
<span data-ttu-id="02d3d-103">Una vez configurado el usuario con una aplicación afiliada, puede usar el inicio de sesión único (SSO) para obtener acceso a las credenciales y al nombre de usuario externos del usuario actual.</span><span class="sxs-lookup"><span data-stu-id="02d3d-103">After you set up your user with an affiliate application, you can use Single Sign-On (SSO) to access the external user name and credentials of the current user.</span></span> <span data-ttu-id="02d3d-104">Con estas credenciales, el usuario puede iniciar sesión en la aplicación afiliada que se ejecuta en un servidor de host.</span><span class="sxs-lookup"><span data-stu-id="02d3d-104">Using these credentials, you can then log your user on to the affiliate application that is running on a host server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02d3d-105">Además de establecer los protocolos de seguridad pertinentes para SSO, puede que sea necesario establecer seguridad adicional para permitir que la aplicación llame a SSO en el contexto de seguridad adecuado.</span><span class="sxs-lookup"><span data-stu-id="02d3d-105">In addition to setting the appropriate security protocols for SSO, you might also need to set additional security to allow your application to call SSO in the correct security context.</span></span> <span data-ttu-id="02d3d-106">Si la aplicación no puede llamar a SSO en el contexto de seguridad adecuado, SSO denegará el acceso a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02d3d-106">If your application cannot call SSO in the correct security context, SSO will deny access to your application.</span></span>  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a><span data-ttu-id="02d3d-107">Para establecer el contexto de seguridad de una aplicación de SSO</span><span class="sxs-lookup"><span data-stu-id="02d3d-107">To set the security context for an SSO application</span></span>  
  
1.  <span data-ttu-id="02d3d-108">Identifique las credenciales necesarias para que la aplicación se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="02d3d-108">Identify what credentials your application needs to run successfully.</span></span>  
  
     <span data-ttu-id="02d3d-109">Por ejemplo, una aplicación que usa servicios web o comunicación remota de .NET Framework hospedada en IIS necesita suplantar al cliente para transferir las credenciales adecuadas a SSO.</span><span class="sxs-lookup"><span data-stu-id="02d3d-109">For example, an application that uses Web services or .NET Framework remoting hosted in IIS needs to impersonate the client in order to pass the appropriate credentials on to SSO.</span></span>  
  
2.  <span data-ttu-id="02d3d-110">Confirme que la configuración de seguridad relevante, como la de los directorios virtuales, grupos de aplicaciones y archivos web.config, se establece de forma que se proporcione a la aplicación dichas credenciales.</span><span class="sxs-lookup"><span data-stu-id="02d3d-110">Confirm that the relevant security settings, such as those on virtual directories, application pools, and web.config files, are set to provide your application with those credentials.</span></span>  
  
     <span data-ttu-id="02d3d-111">Para obtener más información acerca de cómo establecer las credenciales de seguridad, consulte [Building Secure ASP.NET Applications: autenticación, autorización y comunicación segura](http://go.microsoft.com/fwlink/?LinkId=193906).</span><span class="sxs-lookup"><span data-stu-id="02d3d-111">For more information about how to set security credentials, see [Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](http://go.microsoft.com/fwlink/?LinkId=193906).</span></span>  
  
     <span data-ttu-id="02d3d-112">Para obtener más información acerca de la transferencia de credenciales a un servicio Web ASP.NET, vea [HOW TO: pasar credenciales actuales para un servicio Web ASP.NET](http://go.microsoft.com/fwlink/?LinkId=193907).</span><span class="sxs-lookup"><span data-stu-id="02d3d-112">For more information about passing credentials for an ASP.NET Web service, see [HOW TO: Pass Current Credentials to an ASP.NET Web Service](http://go.microsoft.com/fwlink/?LinkId=193907).</span></span>  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a><span data-ttu-id="02d3d-113">Para hacer que un usuario local inicie sesión en una aplicación de host</span><span class="sxs-lookup"><span data-stu-id="02d3d-113">To log a local user on to a host application</span></span>  
  
1.  <span data-ttu-id="02d3d-114">Espere a recibir la solicitud para hacer que el usuario actual inicie sesión en una aplicación que se esté ejecutando en el servidor de host.</span><span class="sxs-lookup"><span data-stu-id="02d3d-114">Receive the request to log the current user on to an application running on the host server.</span></span>  
  
     <span data-ttu-id="02d3d-115">Es responsabilidad suya determinar cómo el usuario actual solicita el inicio de sesión en una aplicación de host.</span><span class="sxs-lookup"><span data-stu-id="02d3d-115">It is your responsibility to determine how the current user requests to be logged on to a host application.</span></span>  
  
2.  <span data-ttu-id="02d3d-116">Recuperar las credenciales del usuario actual que está usando `ISSOLookup1.GetCredentials` o `ISSOLookup2.GetCredentials`.</span><span class="sxs-lookup"><span data-stu-id="02d3d-116">Retrieve the credentials for the current user who is using `ISSOLookup1.GetCredentials` or `ISSOLookup2.GetCredentials`.</span></span>  
  
     <span data-ttu-id="02d3d-117">Debe proporcionar el nombre de la aplicación de host junto con cualquier marca pertinente.</span><span class="sxs-lookup"><span data-stu-id="02d3d-117">You must supply the name of the host application together with any relevant flags.</span></span> <span data-ttu-id="02d3d-118">`GetCredentials`Devuelve el nombre de usuario asociado y las credenciales de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="02d3d-118">`GetCredentials` returns the associated user name and credentials for the host application.</span></span>  
  
     <span data-ttu-id="02d3d-119">Tenga en cuenta que puede usar `ISSOLookup1` o `ISSOLookup2`.</span><span class="sxs-lookup"><span data-stu-id="02d3d-119">Note that you can use either `ISSOLookup1` or `ISSOLookup2`.</span></span> <span data-ttu-id="02d3d-120">La única diferencia es que `ISSOLookup2` también tiene un método para registrar un usuario remoto en una aplicación de windows local.</span><span class="sxs-lookup"><span data-stu-id="02d3d-120">The only difference is that `ISSOLookup2` also has a method for logging a remote user on to a local windows application.</span></span>  
  
3.  <span data-ttu-id="02d3d-121">Utilice las credenciales y el nombre de usuario externos para iniciar sesión en la aplicación de host.</span><span class="sxs-lookup"><span data-stu-id="02d3d-121">Use the external user name and credentials to log on to the host application.</span></span>  
  
     <span data-ttu-id="02d3d-122">Es responsabilidad suya determinar cómo utilizar las credenciales para iniciar sesión en la aplicación de host.</span><span class="sxs-lookup"><span data-stu-id="02d3d-122">It is your responsibility to determine how to use the credentials to log on to the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d3d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d3d-123">See Also</span></span>  
 [<span data-ttu-id="02d3d-124">Cómo registrar un usuario remoto en una aplicación Local</span><span class="sxs-lookup"><span data-stu-id="02d3d-124">How to Log a Remote User on to a Local Application</span></span>](../core/how-to-log-a-remote-user-on-to-a-local-application.md)