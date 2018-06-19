---
title: Compatibilidad con SSO para adaptadores de envío | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45dc2597-0036-4444-8b35-d18621b003d8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d590ada6b8ee80c942714a698d0001c207ac6751
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278436"
---
# <a name="sso-support-for-send-adapters"></a>Compatibilidad de SSO para adaptadores de envío
El inicio de sesión único (SSO) empresarial proporciona servicios para almacenar y transmitir credenciales de usuario cifradas a través de los límites locales, de red y de dominio. Cuando crea un adaptador de transporte, puede aprovechar las API de SSO para controlar las credenciales de usuario que un adaptador de transporte usa para tener acceso a las aplicaciones servidor.  
  
 Suele ser necesario configurar los adaptadores de transporte que no son compatibles con SSO con un conjunto único de credenciales que usen para tener acceso a aplicaciones de servidor. Para muchos sistemas de servidor, es posible que la autenticación de cuenta única no satisfaga todas las exigencias de seguridad. Muchas aplicaciones proporcionan diferentes derechos de acceso en función del usuario que tenga acceso a ellas. SSO permite que los adaptadores elijan de forma dinámica las credenciales que van a usar para el extremo según el usuario que esté intentando tener acceso a él.  
  
## <a name="how-send-adapters-work-with-sso"></a>Cómo funcionan los adaptadores de envío con SSO  
 Enviar adaptadores compatibles con SSO validar y canjear el vale y Obtén las credenciales de usuario del sistema SSO mediante la **ISSOTicket.ValidateAndRedeemTicket** API. Una vez obtenidas las credenciales, el adaptador las usa para autenticar con el extremo de destino.  
  
 El fragmento de código siguiente muestra cómo un adaptador de envío obtiene las credenciales de usuario desde el sistema SSO:  
  
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
  
## <a name="party-resolution"></a>Resolución de entidades  
 La misión del componente de canalización de resolución de entidades consiste en asignar el certificado de remitente o el identificador de seguridad de remitente (SID) a la correspondiente entidad de BizTalk Server configurada. Adaptadores que tienen esta información a su disposición deben establecer el mensaje del dos sistema propiedades de contexto, **WindowsUser** y **SignatureCertificate**, que será consumido por la resolución de entidades de nivel inferior componente si ha configurado.  
  
 El **WindowsUser** propiedad se rellena con el usuario de dominio del remitente, por ejemplo redmond\myBtsUser. El **SignatureCertificate** propiedad se rellena con la huella digital del certificado de autenticación del cliente.  
  
## <a name="managing-passwords"></a>Administración de contraseñas  
 Si coloca las credenciales directamente en las propiedades de un extremo, el campo de contraseña estará en blanco cuando necesite exportar un archivo de enlace. Por ello, el usuario deberá volver a escribir la contraseña como administrador. Para evitar este contratiempo, use SSO para las credenciales.