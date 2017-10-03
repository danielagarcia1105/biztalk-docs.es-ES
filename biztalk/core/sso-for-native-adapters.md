---
title: SSO para adaptadores nativos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45aaf357d943853cc9504762437f554f1d28efb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sso-for-native-adapters"></a><span data-ttu-id="6d29c-102">SSO para adaptadores nativos</span><span class="sxs-lookup"><span data-stu-id="6d29c-102">SSO for Native Adapters</span></span>
<span data-ttu-id="6d29c-103">El inicio de sesión único (SSO) empresarial le permite iniciar sesión sólo una vez al interoperar con diferentes sistemas informáticos o sitios Web.</span><span class="sxs-lookup"><span data-stu-id="6d29c-103">Enterprise Single Sign-On (SSO) enables you to sign on only once when interoperating with different computer systems or Web sites.</span></span> <span data-ttu-id="6d29c-104">Esta característica de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] permite a los adaptadores de BizTalk proporcionar el Id. de usuario y las credenciales apropiadas para varias aplicaciones de la red que utilizan un mecanismo de autenticación común basado en sus credenciales de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="6d29c-104">This feature of Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables BizTalk adapters to provide the appropriate user ID and credentials to multiple applications within your network that use a common authentication mechanism based on your Microsoft Windows credentials.</span></span> <span data-ttu-id="6d29c-105">Después de que Windows haya autenticado sus credenciales, no necesita proporcionar credenciales adicionales para conectarse a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6d29c-105">After Windows authenticates your credentials, you do not need to provide additional credentials to connect to the applications.</span></span>  
  
 <span data-ttu-id="6d29c-106">SSO está disponible para los adaptadores de HTTP y SOAP aunque está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6d29c-106">SSO is available for the HTTP and SOAP adapters, although it is disabled by default.</span></span> <span data-ttu-id="6d29c-107">Para el adaptador de HTTP, puede configurar el puerto de envío y la ubicación de recepción para que utilicen SSO. Para el adaptador de SOAP, puede configurar solo la ubicación de recepción para que utilice SSO.</span><span class="sxs-lookup"><span data-stu-id="6d29c-107">For the HTTP adapter, you can configure the send port and receive location to use SSO; for the SOAP adapter, you can configure only the receive location to use SSO.</span></span> <span data-ttu-id="6d29c-108">Para los dos adaptadores, utilice la consola de administración de BizTalk Server para configurar SSO.</span><span class="sxs-lookup"><span data-stu-id="6d29c-108">For both adapters, you use the BizTalk Server Administration console to configure SSO.</span></span>  
  
 <span data-ttu-id="6d29c-109">La autenticación en SSO se basa principalmente en la autenticación de Windows y en los grupos de Windows que se crearon en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6d29c-109">Authentication in SSO relies primarily on Windows authentication and the Windows groups created in Active Directory.</span></span> <span data-ttu-id="6d29c-110">Todas las operaciones que completó el usuario o el administrador con SSO necesitan que Windows autentique primero el usuario o administrador.</span><span class="sxs-lookup"><span data-stu-id="6d29c-110">All operations completed by a user or administrator with SSO require that Windows authenticate the user or administrator first.</span></span>  
  
 <span data-ttu-id="6d29c-111">Para obtener más información acerca del funcionamiento de SSO con los adaptadores de HTTP y SOAP, vea el tema apropiado en la sección Vea también.</span><span class="sxs-lookup"><span data-stu-id="6d29c-111">For more information about how SSO works with the HTTP and SOAP adapters, see the appropriate topics in See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d29c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d29c-112">See Also</span></span>  
 <span data-ttu-id="6d29c-113">[Uso de SSO](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="6d29c-113">[Using SSO](../core/using-sso.md) </span></span>  
 <span data-ttu-id="6d29c-114">[Adaptador de HTTP](../core/http-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6d29c-114">[HTTP Adapter](../core/http-adapter.md) </span></span>  
 [<span data-ttu-id="6d29c-115">Adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="6d29c-115">SOAP Adapter</span></span>](../core/soap-adapter.md)