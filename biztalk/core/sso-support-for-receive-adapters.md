---
title: Compatibilidad con SSO para adaptadores de recepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4767387c-f24b-4986-aaed-6724c5d6b347
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3c992f47ad46b4a9d5ee095ad650f6cc492179
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sso-support-for-receive-adapters"></a><span data-ttu-id="cdaf9-102">Compatibilidad de SSO para adaptadores de recepción</span><span class="sxs-lookup"><span data-stu-id="cdaf9-102">SSO Support for Receive Adapters</span></span>
<span data-ttu-id="cdaf9-103">El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales, de red y de dominio.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-103">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local, network, and domain boundaries.</span></span> <span data-ttu-id="cdaf9-104">Los escritores del adaptador de transporte pueden aprovechar las API de SSO para controlar las credenciales de usuario que un adaptador de transporte usa para tener acceso a las aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-104">Transport adapter writers can leverage SSO APIs to handle the user credentials that a transport adapter uses to access back-end applications.</span></span>  
  
 <span data-ttu-id="cdaf9-105">Suele ser necesario configurar los adaptadores de transporte que no son compatibles con SSO con un conjunto único de credenciales que usen para tener acceso a aplicaciones de servidor.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-105">Transport adapters that do not support SSO are usually required to be configured with a single set of credentials that they use for accessing back-end applications.</span></span> <span data-ttu-id="cdaf9-106">Para muchos sistemas de servidor, es posible que la autenticación de cuenta única no satisfaga todas las exigencias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-106">For many back-end systems, single account authentication may not satisfy all security enforcements.</span></span> <span data-ttu-id="cdaf9-107">Muchas aplicaciones proporcionan diferentes derechos de acceso en función del usuario que tenga acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-107">Many applications provide different access rights depending on the user who is accessing them.</span></span> <span data-ttu-id="cdaf9-108">SSO permite que los adaptadores elijan de forma dinámica las credenciales que van a usar para el extremo según el usuario que esté intentando tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-108">SSO allows adapters to dynamically choose the credentials to use for the endpoint based on the user who is trying to access it.</span></span>  
  
## <a name="how-receive-adapters-work-with-sso"></a><span data-ttu-id="cdaf9-109">Cómo funcionan los adaptadores de recepción con SSO</span><span class="sxs-lookup"><span data-stu-id="cdaf9-109">How Receive Adapters Work with SSO</span></span>  
 <span data-ttu-id="cdaf9-110">Los adaptadores de recepción compatibles con SSO realizan los pasos siguientes después de recibir un mensaje y antes de publicarlo en BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="cdaf9-110">Receive adapters that support SSO perform the following steps after receiving a message and before publishing it to BizTalk Server:</span></span>  
  
1.  <span data-ttu-id="cdaf9-111">El adaptador suplanta al remitente y obtiene el vale de SSO en nombre del remitente con el **ISSOTicket.IssueTicket** API.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-111">The adapter impersonates the sender and obtains the SSO ticket on behalf of the sender by using the **ISSOTicket.IssueTicket** API.</span></span>  
  
2.  <span data-ttu-id="cdaf9-112">Después de obtener correctamente un vale de SSO, el adaptador lo almacena en la propiedad de contexto del mensaje “SSOTicket” en el espacio de nombres del sistema.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-112">After successfully obtaining an SSO ticket the adapter stores it on the message context property “SSOTicket” under the system namespace.</span></span>  
  
 <span data-ttu-id="cdaf9-113">El fragmento de código siguiente muestra cómo se obtiene el vale y cómo se almacena en el contexto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-113">The following code fragment demonstrates how the ticket is obtained and how it is stored on the message context.</span></span>  
  
```  
public class MyAdapter : IBTTransport,   
                         IBTTransportConfig,   
                         IBTTransportControl,  
                         IPersistPropertyBag,   
                         IBaseComponent  
{  
...  
     private string m_SSOToken = null;  
  
 // Get a ticket for the sender  
     private void GetSSOTicket(IntPtr token)  
     {  
       bool impersonated = false;  
      WindowsImpersonationContext wic = null;  
  
 if (token != (IntPtr)0)   
 {  
     try   
 {  
         // Impersonate the user using his security  
 // token  
            WindowsIdentity wi =   
 new WindowsIdentity(token);  
            wic = wi.Impersonate();  
            impersonated = true;  
  
         // Get an SSO ticket for the impersonated  
 // user  
            ISSOTicket ssoTicket = new ISSOTicket();  
            m_SSOToken = ssoTicket.IssueTicket(0);  
         }  
         finally   
 {  
           if (impersonated)  
            // Revert the impersonation  
            wic.Undo();  
          }  
}  
}  
...  
  
     private void WriteSSOTicketToContext(  
 IBaseMessage message )  
     {  
         if (m_SSOTicket != null)   
 {  
 // Write the SSO ticket to the message context  
          message.Context.Write(  
 “SSOTicket”,  
 http://schemas.microsoft.com/BizTalk/2003/system-properties,   
 m_SSOToken);  
        }  
      }  
}  
```  
  
## <a name="party-resolution"></a><span data-ttu-id="cdaf9-114">Resolución de entidades</span><span class="sxs-lookup"><span data-stu-id="cdaf9-114">Party Resolution</span></span>  
 <span data-ttu-id="cdaf9-115">La misión del componente de canalización de resolución de entidades consiste en asignar el certificado de remitente o el identificador de seguridad de remitente (SID) a la correspondiente entidad de BizTalk Server configurada.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-115">The Party Resolution pipeline component is responsible for mapping the sender certificate or the sender security identifier (SID) to the corresponding configured BizTalk Server party.</span></span> <span data-ttu-id="cdaf9-116">Adaptadores que tienen esta información a su disposición deben establecer el mensaje del dos sistema propiedades de contexto, **WindowsUser** y **SignatureCertificate**, que será consumido por la resolución de entidades de nivel inferior componente si ha configurado.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-116">Adapters that have this information available to them should set the two system message context properties, **WindowsUser** and **SignatureCertificate**, to be consumed by the downstream party resolution component if configured.</span></span>  
  
 <span data-ttu-id="cdaf9-117">El **WindowsUser** propiedad se rellena con el usuario de dominio del remitente, por ejemplo redmond\myBtsUser.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-117">The **WindowsUser** property is populated with the domain user of the sender, for example redmond\myBtsUser.</span></span> <span data-ttu-id="cdaf9-118">El **SignatureCertificate** propiedad se rellena con la huella digital del certificado de autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-118">The **SignatureCertificate** property is populated with the thumbprint of the client authentication certificate.</span></span>  
  
## <a name="managing-passwords"></a><span data-ttu-id="cdaf9-119">Administrar contraseñas</span><span class="sxs-lookup"><span data-stu-id="cdaf9-119">Managing Passwords</span></span>  
 <span data-ttu-id="cdaf9-120">Si coloca las credenciales directamente en las propiedades de un extremo, el campo de contraseña estará en blanco cuando necesite exportar un archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-120">If you put credentials directly in the properties of an endpoint, the password field will be blanked out when you need to export a binding file.</span></span> <span data-ttu-id="cdaf9-121">Por ello, el usuario deberá volver a escribir la contraseña como administrador.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-121">This will require your user to re-enter the password as an administrator.</span></span> <span data-ttu-id="cdaf9-122">Para evitar este contratiempo, use SSO para las credenciales.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-122">You can avoid this difficulty by using SSO for credentials.</span></span>  
  
 <span data-ttu-id="cdaf9-123">Si el extremo del adaptador tiene un **contraseña** propiedad, tenga en cuenta que el valor real se almacena en texto no cifrado en la base de datos de almacén de configuración de SSO.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-123">If the adapter endpoint has a **Password** property, be aware that the actual value is stored in clear text in the SSO Configure Store database.</span></span> <span data-ttu-id="cdaf9-124">Esto es así a pesar de que en la interfaz de usuario se muestra como "\*".</span><span class="sxs-lookup"><span data-stu-id="cdaf9-124">This is despite the fact that it is displayed in the user interface as "\*".</span></span> <span data-ttu-id="cdaf9-125">Esta propiedad también se transfiere a través de la red y una secuencia de comandos sencilla mediante el ejemplo de BizTalk Server que ExplorerOM podrá leer.</span><span class="sxs-lookup"><span data-stu-id="cdaf9-125">This property is also transferred through the network and a simple script using the BizTalk Server sample ExplorerOM will be able to read it.</span></span>