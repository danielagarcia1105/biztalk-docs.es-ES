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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e3c992f47ad46b4a9d5ee095ad650f6cc492179
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22276668"
---
# <a name="sso-support-for-receive-adapters"></a>Compatibilidad de SSO para adaptadores de recepción
El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales, de red y de dominio. Los escritores del adaptador de transporte pueden aprovechar las API de SSO para controlar las credenciales de usuario que un adaptador de transporte usa para tener acceso a las aplicaciones de servidor.  
  
 Suele ser necesario configurar los adaptadores de transporte que no son compatibles con SSO con un conjunto único de credenciales que usen para tener acceso a aplicaciones de servidor. Para muchos sistemas de servidor, es posible que la autenticación de cuenta única no satisfaga todas las exigencias de seguridad. Muchas aplicaciones proporcionan diferentes derechos de acceso en función del usuario que tenga acceso a ellas. SSO permite que los adaptadores elijan de forma dinámica las credenciales que van a usar para el extremo según el usuario que esté intentando tener acceso a él.  
  
## <a name="how-receive-adapters-work-with-sso"></a>Cómo funcionan los adaptadores de recepción con SSO  
 Los adaptadores de recepción compatibles con SSO realizan los pasos siguientes después de recibir un mensaje y antes de publicarlo en BizTalk Server:  
  
1.  El adaptador suplanta al remitente y obtiene el vale de SSO en nombre del remitente con el **ISSOTicket.IssueTicket** API.  
  
2.  Después de obtener correctamente un vale de SSO, el adaptador lo almacena en la propiedad de contexto del mensaje “SSOTicket” en el espacio de nombres del sistema.  
  
 El fragmento de código siguiente muestra cómo se obtiene el vale y cómo se almacena en el contexto del mensaje.  
  
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
  
## <a name="party-resolution"></a>Resolución de entidades  
 La misión del componente de canalización de resolución de entidades consiste en asignar el certificado de remitente o el identificador de seguridad de remitente (SID) a la correspondiente entidad de BizTalk Server configurada. Adaptadores que tienen esta información a su disposición deben establecer el mensaje del dos sistema propiedades de contexto, **WindowsUser** y **SignatureCertificate**, que será consumido por la resolución de entidades de nivel inferior componente si ha configurado.  
  
 El **WindowsUser** propiedad se rellena con el usuario de dominio del remitente, por ejemplo redmond\myBtsUser. El **SignatureCertificate** propiedad se rellena con la huella digital del certificado de autenticación del cliente.  
  
## <a name="managing-passwords"></a>Administrar contraseñas  
 Si coloca las credenciales directamente en las propiedades de un extremo, el campo de contraseña estará en blanco cuando necesite exportar un archivo de enlace. Por ello, el usuario deberá volver a escribir la contraseña como administrador. Para evitar este contratiempo, use SSO para las credenciales.  
  
 Si el extremo del adaptador tiene un **contraseña** propiedad, tenga en cuenta que el valor real se almacena en texto no cifrado en la base de datos de almacén de configuración de SSO. Esto es así a pesar de que en la interfaz de usuario se muestra como "*". Esta propiedad también se transfiere a través de la red y una secuencia de comandos sencilla mediante el ejemplo de BizTalk Server que ExplorerOM podrá leer.