---
title: "Solo el inicio de sesión de soporte técnico para los adaptadores de WCF | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF adapters, Single Sign-On
- Single Sign-On, WCF adapters
ms.assetid: 70a33d87-50bd-41de-9084-68dd66b0dbf9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 712aa01190762d6c6f74604a5f48c19fe42531d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-support-for-the-wcf-adapters"></a>Compatibilidad del inicio de sesión único (SSO) con los adaptadores de WCF
Puede configurar Inicio de sesión único empresarial (SSO) para usarlo con una ubicación de recepción WCF o un puerto de envío mediante la consola de administración de BizTalk. En este tema se describe el funcionamiento de SSO con los adaptadores de WCF.  
  
 En un entorno empresarial, donde el usuario interactúa con varios sistemas y aplicaciones, es muy posible que el entorno no mantenga el contexto de usuario en varios procesos, productos y equipos. Este contexto de usuario es crucial para proporcionar funciones de inicio de sesión único (SSO), como es necesario para comprobar quién inició la solicitud original. Para solucionar este problema, el inicio de sesión único (SSO) proporciona un vale de SSO (no un vale Kerberos) que las aplicaciones pueden utilizar para obtener las credenciales que se corresponden con el usuario que realizó la solicitud original.  
  
 Cuando un adaptador de recepción recibe un mensaje, el adaptador puede solicitar un vale de SSO de un servidor SSO. Este vale cifrado contiene la identidad [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] del usuario que ha realizado la solicitud y un período de tiempo de espera. Después de adquirirlo, se agrega como propiedad al mensaje entrante. Cuando un adaptador de envío transmite un mensaje, el adaptador se pone en contacto con un servidor de SSO con el vale de SSO emitido y un nombre de aplicación afiliada para el que el adaptador está intentando recuperar una credencial. El servidor de SSO busca la credencial de usuario para la aplicación afiliada de destino y devuelve la credencial al adaptador de envío, que la usa para enviar un mensaje autenticado de forma adecuada a la aplicación afiliada.  
  
## <a name="single-sign-on-support-for-the-wcf-receive-locations"></a>Compatibilidad del Inicio de sesión único (SSO) con las ubicaciones de recepción WCF  
 La configuración de seguridad aplicada, combinada con el tipo de adaptador de WCF usado para una ubicación de recepción, decide si el adaptador de recepción WCF puede emitir vales SSO. Para que el adaptador de recepción WCF envíe un token SSO, los clientes de WCF deben enviar una credencial que el adaptador pueda suplantar. La suplantación es la capacidad de una aplicación de servidor para tomar la identidad del cliente. La credencial se debe asignar a una cuenta de usuario de [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] válida para una correcta suplantación.  
  
> [!NOTE]
>  En el caso de la configuración de seguridad y de los adaptadores de WCF que no solicitan a los clientes el envío de credenciales para la suplantación, puede emitir vales SSO con cualquier tipo de credenciales que los clientes envíen en un componente de canalización de recepción personalizado. Para obtener más información acerca de cómo controlar los vales SSO en componentes de canalización de recepción, consulte el componente de canalización de ejemplo, InPipelineComp, incluido en [inventario de archivos para la solución orientada a servicios](../core/file-inventory-for-the-service-oriented-solution.md).  
  
 **Ubicación de recepción de compatibilidad de inicio de sesión único para WCF-BasicHttp**  
  
 El adaptador de recepción WCF-BasicHttp puede emitir un vale de SSO desde el servidor de SSO sólo en las configuraciones de seguridad que se muestran en la siguiente tabla.  
  
> [!NOTE]
>  Para obtener más información acerca de cómo asignar un certificado a un [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] usuario de la cuenta, consulte "Asignación de certificados a cuentas de usuario" en [http://go.microsoft.com/fwlink/?LinkId=87478](http://go.microsoft.com/fwlink/?LinkId=87478).  
  
|Modo de seguridad|Tipo de credenciales de cliente de transporte|Tipo de credenciales de cliente de mensajes|  
|-------------------|--------------------------------------|------------------------------------|  
|Transporte|Básico|N/D|  
|Transporte|Resumen|N/D|  
|Transporte|Ntlm|N/D|  
|Transporte|Windows|N/D|  
|Transporte|Certificado|N/D|  
|de mensaje|N/D|UserName|  
|de mensaje|N/D|Certificado|  
|TransportWithMessageCredential|N/D|Certificado|  
|TransportWithMessageCredential|N/D|UserName|  
|TransportCredentialOnly|Básico|N/D|  
|TransportCredentialOnly|Resumen|N/D|  
|TransportCredentialOnly|Ntlm|N/D|  
|TransportCredentialOnly|Windows|N/D|  
|TransportCredentialOnly|Certificado|N/D|  
  
 **Ubicación de recepción de compatibilidad de inicio de sesión único de WCF-WSHttp**  
  
 El adaptador de recepción WCF-WSHttp puede emitir un vale de SSO desde el servidor de SSO sólo en las configuraciones de seguridad que se muestran en la siguiente tabla.  
  
|Modo de seguridad|Tipo de credenciales de cliente de transporte|Tipo de credenciales de cliente de mensajes|  
|-------------------|--------------------------------------|------------------------------------|  
|Transporte|Básico|N/D|  
|Transporte|Resumen|N/D|  
|Transporte|Ntlm|N/D|  
|Transporte|Windows|N/D|  
|Transporte|Certificado|N/D|  
|de mensaje|N/D|UserName|  
|de mensaje|N/D|Windows|  
|de mensaje|N/D|Certificado|  
|TransportWithMessageCredential|N/D|Windows|  
|TransportWithMessageCredential|N/D|Certificado|  
|TransportWithMessageCredential|N/D|UserName|  
  
 **Ubicación de recepción de compatibilidad de inicio de sesión único de WCF-NetTcp**  
  
 El adaptador de recepción WCF-NetTcp puede emitir un vale de SSO desde el servidor de SSO sólo en las configuraciones de seguridad que se muestran en la siguiente tabla.  
  
|Modo de seguridad|Tipo de credenciales de cliente de transporte|Tipo de credenciales de cliente de mensajes|  
|-------------------|--------------------------------------|------------------------------------|  
|Transporte|Windows|N/D|  
|Transporte|Certificado|N/D|  
|de mensaje|N/D|Certificado|  
|de mensaje|N/D|Windows|  
|de mensaje|N/D|UserName|  
|TransportWithMessageCredential|N/D|Certificado|  
|TransportWithMessageCredential|N/D|Windows|  
|TransportWithMessageCredential|N/D|UserName|  
  
 S**única de inicio de sesión de soporte técnico para la ubicación de recepción de WCF-NetNamedPipe**  
  
 El adaptador de recepción WCF-NetNamedPipe puede emitir un vale de SSO desde el servidor de SSO sólo en las configuraciones de seguridad que se muestran en la siguiente tabla.  
  
|Modo de seguridad|Tipo de credenciales de cliente de transporte|Tipo de credenciales de cliente de mensajes|  
|-------------------|--------------------------------------|------------------------------------|  
|Transporte|N/D|N/D|  
  
 **Ubicación de recepción de compatibilidad de inicio de sesión único para WCF-Custom y WCF-CustomIsolated**  
  
 Para que las ubicaciones de recepción WCF-Custom y WCF-CustomIsolated emitan vales de SSO, la configuración de seguridad usada en las ubicaciones de recepción requiere que los clientes de WCF envíen las credenciales que se pueden suplantar mediante Windows Communication Foundation. WCF admite la suplantación de distintos tipos de credenciales de clientes. Para obtener más información acerca de los tipos de credenciales que WCF admite para la suplantación, vea "Delegación y suplantación con WCF" en [http://go.microsoft.com/fwlink/?LinkId=87476](http://go.microsoft.com/fwlink/?LinkId=87476).  
  
## <a name="single-sign-on-support-for-the-wcf-send-ports"></a>Compatibilidad del inicio de sesión único (SSO) con los puertos de envío WCF  
 En el caso de los puertos de envío WCF, puede especificar el nombre de una aplicación afiliada que se va a usar para SSO sólo en la configuración de seguridad mostrada en la siguiente tabla.  
  
|Modo de seguridad|Tipo de credenciales de cliente de transporte|Tipo de credenciales de cliente de mensajes|  
|-------------------|--------------------------------------|------------------------------------|  
|Transporte|Resumen|N/D|  
|Transporte|Básico|N/D|  
|de mensaje|N/D|UserName|  
  
> [!NOTE]
>  Para un WCF puerto de envío para validar y canjear un vale de SSO correctamente, el **SSOTicket** y **OriginatorSID** propiedades de contexto deben estar disponibles en el que se envíe un mensaje. Una ubicación de recepción con inicio de sesión único puede promocionar estas propiedades desde una cuenta de [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] del remitente.  
  
## <a name="see-also"></a>Vea también  
 [Enterprise Single Sign-On](../core/enterprise-single-sign-on2.md)