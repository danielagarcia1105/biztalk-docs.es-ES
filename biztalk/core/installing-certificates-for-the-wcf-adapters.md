---
title: Instalación de certificados para los adaptadores de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tools, Certificates Management Console
- certificates, installing [WCF adapters]
- certificates, Certificates Management Console
- certificates, WCF adapters
- WCF adapters, send locations
- receive locations, WCF adapters
- send locations, WCF adapters
- WCF adapters, receive locations
- WCF adapters, certificates
ms.assetid: 04dc065f-a6e8-4359-8696-2a3de24d531d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 654e5300c253bbf4cede2113c9282b6a2f02862c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258108"
---
# <a name="installing-certificates-for-the-wcf-adapters"></a>Instalar certificados para los adaptadores de WCF
Los adaptadores de WCF pueden hacer uso de certificados digitales de infraestructura de clave pública (PKI) a efectos de cifrado y descifrado de mensajes, firma y comprobación de mensajes (sin repudio), así como para la autenticación de cliente. En este tema se describen varias opciones de configuración y de escenarios de uso de certificación para la utilización de certificados digitales con adaptadores de WCF.  
  
## <a name="certificate-usage-scenarios-for-the-wcf-receive-locations"></a>Escenarios de uso de certificado para ubicaciones de recepción WCF  
 La siguiente tabla muestra cómo instalar los certificados para las ubicaciones de recepción WCF.  
  
|Uso de certificado|Contexto de usuario|Ubicación del almacén de certificados|Tipo de certificado|Cuándo instalar los certificados|  
|-----------------------|------------------|--------------------------------|----------------------|--------------------------------------|  
|Descifrado y firma que dependen de la configuración de seguridad de la ubicación de recepción|Cuenta usada por la instancia de host asociada al controlador de recepción|Inicie sesión en cada equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se las ubicaciones de recepción como cada cuenta de servicio de la instancia de host e importe el certificado de servicio en la **usuario actual \ Personal** almacenar.|Certificado privado propio|Especificar el valor de la **huella digital de certificado de servicio** propiedad en las siguientes configuraciones:<br /><br /> -El **modo de seguridad** ubicación de recepción de la propiedad de WCF-BasicHttp se establece en **mensaje**.<br />-El **tipo de credencial de cliente de transporte** ubicación de recepción de la propiedad de WCF-BasicHttp se establece en **certificado** para el **TransportCredentialOnly** modo de seguridad.<br />-El **tipo de credencial de cliente de mensaje** ubicación de recepción de la propiedad de WCF-WSHttp se establece en **ninguno**, **certificado**, o **nombre de usuario** para el **mensaje** modo de seguridad.<br />-El **tipo de credencial de cliente de transporte** ubicación de recepción de la propiedad de WCF-NetTcp se establece en **ninguno** o **certificado** para el **transporte**modo de seguridad.<br />-El **tipo de credencial de cliente de mensaje** ubicación de recepción de la propiedad de WCF-NetTcp se establece en **ninguno**, **nombre de usuario**, o **certificado** para el **mensaje** modo de seguridad.<br />-El **tipo de credencial de cliente de mensaje** ubicación de recepción de la propiedad de WCF-NetTcp se establece en **Windows**, **nombre de usuario**, o **certificado**para el **TransportWithMessageCredential** modo de seguridad.<br />-El **modo de seguridad** propiedad de WCF-NetMsmq se establece en **mensaje** o **ambos**.|  
|Autenticación de cliente|N/D|Inicie sesión en los equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que alojarán las ubicaciones de recepción como Administradores e importe la cadena de certificados de CA para los certificados X.509 de cliente en el almacén del certificado Entidades emisoras raíz de confianza del equipo para que se puedan autenticar los clientes en esta ubicación de recepción.|La cadena de certificados de CA para los certificados X.509 de cliente|Instale la cadena de certificados de CA para los certificados X.509 de cliente en el almacén de certificado Entidades emisoras raíz de confianza en las siguientes configuraciones:<br /><br /> -El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** ubicación de recepción de la propiedad de WCF-BasicHttp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** ubicación de recepción de la propiedad de WCF-WSHttp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** ubicación de recepción de la propiedad de WCF-NetTcp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** o **MsmqAuthenticationMode** ubicación de recepción de la propiedad de WCF-NetMsmq se establece en **certificado**.|  
  
> [!NOTE]
>  Dado que el uso de adaptadores de recepción de WCF estándar la [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960) modo para validar los certificados de cliente, debe instalar la cadena de certificados de entidad emisora de certificados para los certificados de cliente X.509. Puede usar WCF-Custom o los adaptadores de WCF-CustomIsolated para cange este comportamiento predeterminado.  
  
> [!NOTE]
>  Para los adaptadores de recepción WCF aislados, debe hacer coincidir la cuenta de usuario entre una instancia de host aislado y el grupo de aplicaciones correspondientes. Para obtener más información acerca de los hosts aislados de BizTalk, consulte [habilitar servicios Web](../core/enabling-web-services.md).  
  
> [!NOTE]
>  Para el WCF-Custom y WCF-CustomIsolated ubicaciones de recepción, el contexto de usuario, ubicación del almacén de certificados, y el tipo de certificado para los certificados a instalar varía según la **serviceCredentials** y  **clientCredentials** valores del elemento de comportamiento.  
  
> [!NOTE]
>  Si la ubicación de recepción utiliza el elemento de certificado para el **identidad de extremo** propiedad, también tendrá que instalar el certificado para la identidad del servicio publicado en el almacén de certificados especificado en el  **Identidad del extremo** propiedad.  
  
> [!NOTE]
>  En lugar de iniciar sesión en el equipo mediante una cuenta de administrador o una cuenta de servicio de instancia de host, puede usar como alternativa el comando Ejecutar como con cuentas aplicables para realizar la misma acción.  
  
## <a name="certificate-usage-scenarios-for-the-wcf-send-ports"></a>Escenarios de uso de certificado para puertos de recepción WCF  
 La siguiente tabla muestra cómo instalar los certificados para los puertos de recepción WCF.  
  
|Uso de certificado|Contexto de usuario|Ubicación del almacén de certificados|Tipo de certificado|Cuándo instalar los certificados|  
|-----------------------|------------------|--------------------------------|----------------------|--------------------------------------|  
|Autenticación de cliente|Cuenta usada por la instancia de host asociada al puerto de envío|Inicie sesión en cada equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se los puertos de envío como cada cuenta de servicio de la instancia de host e importe el certificado de cliente en el **usuario actual \ Personal** almacenar.|Certificado privado propio|Especificar el valor de la **huella digital de certificado de cliente** propiedad en las siguientes configuraciones:<br /><br /> -El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** propiedad del puerto de envío WCF-BasicHttp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** propiedad del puerto de envío WCF-WSHttp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** propiedad del puerto de envío WCF-NetTcp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** o **MsmqAuthenticationMode** propiedad del puerto de envío WCF-NetMsmq se establece en **certificado**.|  
|La autenticación de servicios, comprobación de firma y cifrado que dependen de la configuración de seguridad del puerto de envío.|N/D|Inicie sesión en cada equipo que ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que se los puertos de envío como administradores e importe el certificado del servicio para el **equipo Local \ otras personas (AddressBook)** almacenar. Deberá instalar también la cadena de certificados de CA para certificados de servicio en el almacén de certificados Entidades emisoras de certificados raíz de confianza del equipo.|: Certificado público de servicio<br />-La cadena de certificados de entidad emisora de certificados del certificado de servicio|Especificar el valor de la **huella digital de certificado de servicio** propiedad en las siguientes configuraciones:<br /><br /> -El **tipo de credencial de cliente de mensaje** o **tipo de credencial de cliente de transporte** propiedad del puerto de envío WCF-BasicHttp se establece en **certificado**.<br />-El **tipo de credencial de cliente de mensaje** propiedad del puerto de envío WCF-WSHttp se establece en **ninguno**, **nombre de usuario**, o **certificado** cuando el **Negociar credencial de servicio** opción está desactivada.<br />-El **modo de seguridad** de envío WCF-NetMsmq puerto se establece en **mensaje** o **ambos**.|  
|La autenticación de servicios, comprobación de firma y cifrado que dependen de la configuración de seguridad del puerto de envío.|N/D|Inicie sesión en los equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que alojarán el puerto de envío como Administradores e importe la cadena de certificados de CA para los certificados X.509 de cliente en el almacén del certificado Entidades emisoras raíz de confianza del equipo para que el servicio se puedan autenticar en esta ubicación de recepción.|La cadena de certificados de CA para el certificado de servicio|Si no especifica explícitamente el certificado del servicio para el **huella digital de certificado de servicio** propiedad, instale certificados de la cadena de certificados de entidad emisora de certificados para el servicio X.509 para las entidades de certificación raíz de confianza almacén de certificados en las siguientes configuraciones:<br /><br /> -El **modo de seguridad** de envío WCF-BasicHttp puerto se establece en **transporte** o **TransportWithMessageCredential**.<br />-El **modo de seguridad** de envío WCF-WSHttp puerto se establece en **transporte** o **TransportWithMessageCredential**.<br />-El **modo de seguridad** de envío WCF-NetTcp puerto se establece en **TransportWithMessageCredential**.<br />-El **tipo de credencial de cliente de transporte** propiedad del puerto de envío WCF-NetTcp se establece en **ninguno** o **certificado**.<br />-El **tipo de credencial de cliente de mensaje** propiedad del puerto de envío WCF-NetTcp se establece en **ninguno**, **nombre de usuario**, o **certificado**.|  
  
> [!NOTE]
>  Dado que el uso de adaptadores de envío de WCF estándar la [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960) modo para validar los certificados de servicio, debe instalar la cadena de certificados de entidad emisora de certificados para los certificados X.509 de servicio. Puede usar los adaptadores de WCF-Custom o de WCF-CustomIsolated para cambiar este comportamiento predeterminado.  
  
> [!NOTE]
>  Para el WCF-Custom y WCF-CustomIsolated envían puertos y la ubicación del almacén de certificados, el contexto de usuario y el tipo de certificado para los certificados a instalar varía según la **serviceCredentials** y  **clientCredentials** valores del elemento de comportamiento.  
  
> [!NOTE]
>  Si el puerto de envío utiliza el elemento de certificado para el **identidad de extremo** propiedad, también tendrá que instalar el certificado para la identidad del servicio esperado en el almacén de certificados especificado en el **extremo Identidad** propiedad.  
  
> [!NOTE]
>  En lugar de iniciar sesión en el equipo mediante una cuenta de administrador o una cuenta de servicio de instancia de host, puede usar como alternativa el comando Ejecutar como con cuentas aplicables para realizar la misma acción.  
  
## <a name="displaying-the-certificates-management-console"></a>Mostrar la consola de administración de certificados  
 Para mostrar la interfaz de consola de administración de certificados para Equipo local y Usuario actual, realice los siguientes pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **MMC**y haga clic en **Aceptar** para abrir la consola de administración de Microsoft.  
  
2.  En el **archivo** menú, haga clic en **agregar o quitar complemento** para mostrar la **agregar o quitar complemento** cuadro de diálogo.  
  
3.  Haga clic en **agregar** para mostrar la **Add Standalone Snap-in** cuadro de diálogo.  
  
4.  Seleccione **certificados** en la lista de complementos y, a continuación, haga clic en **agregar**.  
  
5.  Seleccione **cuenta de equipo**, haga clic en **siguiente**y, a continuación, haga clic en **finalizar**. Esto agregará la interfaz de la consola de administración de certificados para Equipo local.  
  
6.  Asegúrese de que **certificados** sigue seleccionado en la lista de complementos y, a continuación, haga clic en **agregar** nuevo.  
  
7.  Seleccione **mi cuenta de usuario**y, a continuación, haga clic en **finalizar**. Esto agregará la interfaz de la consola de administración de certificados para Usuario actual.  
  
    > [!NOTE]
    >  Esto muestra la consola de administración de certificados para la cuenta en la que ha iniciado sesión actualmente. Si es necesario importar certificados en el almacén Personal para una cuenta de servicio, primero debe iniciar sesión con las credenciales de la cuenta de servicio.  
  
8.  Haga clic en **cerrar** en el **Standalone Snap-in** cuadro de diálogo.  
  
9. Haga clic en **Aceptar** en el **agregar o quitar complemento** cuadro de diálogo.