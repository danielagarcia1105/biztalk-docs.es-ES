---
title: "Compatibilidad con SSO para adaptadores de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d590ada6b8ee80c942714a698d0001c207ac6751
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sso-support-for-send-adapters"></a><span data-ttu-id="5f1c8-102">Compatibilidad de SSO para adaptadores de envío</span><span class="sxs-lookup"><span data-stu-id="5f1c8-102">SSO Support for Send Adapters</span></span>
<span data-ttu-id="5f1c8-103">El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales, de red y de dominio.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="5f1c8-104">Cuando crea un adaptador de transporte, puede aprovechar las API de SSO para controlar las credenciales de usuario que un adaptador de transporte usa para tener acceso a las aplicaciones servidor.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-104">When you create a transport adapter, you can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="5f1c8-105">Suele ser necesario configurar los adaptadores de transporte que no son compatibles con SSO con un conjunto único de credenciales que usen para tener acceso a aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="5f1c8-106">Para muchos sistemas de servidor, es posible que la autenticación de cuenta única no satisfaga todas las exigencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="5f1c8-107">Muchas aplicaciones proporcionan diferentes derechos de acceso en función del usuario que tenga acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="5f1c8-108">SSO permite que los adaptadores elijan de forma dinámica las credenciales que van a usar para el extremo según el usuario que esté intentando tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-send-adapters-work-with-sso"></a><span data-ttu-id="5f1c8-109">Cómo funcionan los adaptadores de envío con SSO</span><span class="sxs-lookup"><span data-stu-id="5f1c8-109">How Send Adapters Work with SSO</span></span>  
 <span data-ttu-id="5f1c8-110">Enviar adaptadores compatibles con SSO validar y canjear el vale y Obtén las credenciales de usuario del sistema SSO mediante la **ISSOTicket.ValidateAndRedeemTicket** API.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-110">Send adapters that support SSO validate and redeem the ticket and obtain the user credentials from the SSO system by using the **ISSOTicket.ValidateAndRedeemTicket** API.</span></span> <span data-ttu-id="5f1c8-111">Una vez obtenidas las credenciales, el adaptador las usa para autenticar con el extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-111">The adapter uses the obtained credentials to authenticate with the destination endpoint.</span></span>  
  
 <span data-ttu-id="5f1c8-112">El fragmento de código siguiente muestra cómo un adaptador de envío obtiene las credenciales de usuario desde el sistema SSO:</span><span class="sxs-lookup"><span data-stu-id="5f1c8-112">The following code fragment demonstrates how a send adapter obtains the user credentials from the SSO system:</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                        IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_UserName = null;  
     private string m_UserPassword = null;  
  
 // Get user credentials from SSO  
 // AffiliateAppVal is the name of SSO affiliate   
 // application for the specific destination endpoint  
     private void GetUserCredentials(  
 IBaseMessage message,   
 string AffiliateAppVal )  
     {  
 string creds[] = null;  
 string externalUserName = null;  
  
 ISSOTicket ssoTicket = new ISSOTicket();  
 creds = ssoTicket.ValidateAndRedeemTicket(  
 message,   
 AffiliateAppVal,   
 0,   
 out externalUserName);  
  
 m_UserName = externalUserName;  
 m_UserPassword = creds[0];  
     }  
...  
}  
```  
  
## <a name="party-resolution"></a><span data-ttu-id="5f1c8-113">Resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="5f1c8-113">Party Resolution</span></span>  
 <span data-ttu-id="5f1c8-114">La misión del componente de canalización de resolución de entidades consiste en asignar el certificado de remitente o el identificador de seguridad de remitente (SID) a la correspondiente entidad de BizTalk Server configurada.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-114">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="5f1c8-115">Adaptadores que tienen esta información a su disposición deben establecer el mensaje del dos sistema propiedades de contexto, **WindowsUser** y **SignatureCertificate**, que será consumido por la resolución de entidades de nivel inferior componente si ha configurado.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-115">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="5f1c8-116">El **WindowsUser** propiedad se rellena con el usuario de dominio del remitente, por ejemplo redmond\myBtsUser.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-116">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="5f1c8-117">El **SignatureCertificate** propiedad se rellena con la huella digital del certificado de autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-117">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="5f1c8-118">Administración de contraseñas</span><span class="sxs-lookup"><span data-stu-id="5f1c8-118">Managing passwords</span></span>  
 <span data-ttu-id="5f1c8-119">Si coloca las credenciales directamente en las propiedades de un extremo, el campo de contraseña estará en blanco cuando necesite exportar un archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-119">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="5f1c8-120">Por ello, el usuario deberá volver a escribir la contraseña como administrador.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-120">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="5f1c8-121">Para evitar este contratiempo, use SSO para las credenciales.</span><span class="sxs-lookup"><span data-stu-id="5f1c8-121">You can avoid this difficulty by using SSO for credentials.</span></span>