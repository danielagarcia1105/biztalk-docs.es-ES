---
title: Único inicio de sesión de soporte técnico para el adaptador de SOAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, SOAP adapters
- SOAP adapters, SharePoint Portal Server
- SOAP adapters, SSO
- SharePoint Portal server
ms.assetid: c7bf755c-c37d-4b19-9817-a7f42e1e9656
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95673e0f8d7f8a49ba0ad6d5ba6760a6db4b524
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966709"
---
# <a name="single-sign-on-support-for-the-soap-adapter"></a>Compatibilidad de inicio de sesión único para el adaptador de SOAP
Puede usar la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para configurar el inicio de sesión único (SSO) empresarial para su uso con la ubicación de recepción o el puerto de envío de SOAP. En este tema se describe el funcionamiento de SSO con el adaptador de SOAP.  
  
 **Compatibilidad de inicio de sesión único SOAP de ubicaciones de recepción**  
  
 Las ubicaciones de recepción de SOAP admiten dos versiones de SSO: inicio de sesión único (SSO) empresarial de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e inicio de sesión único (SSO) de Microsoft SharePoint Portal Server. Ejecute el Asistente para publicación de servicios Web de BizTalk para habilitar la compatibilidad con inicio de sesión único (SSO) de SharePoint Portal Server. Para obtener más información acerca de cómo habilitar SSO de SharePoint Portal Server, vea [publicar servicios Web](../core/publishing-web-services.md). Active el inicio de sesión único (SSO) empresarial utilizando las páginas de propiedades de la ubicación de recepción de SOAP. Para obtener más información acerca de cómo habilitar el inicio de sesión único empresarial para ubicación de recepción de SOAP, vea [cómo configurar una ubicación de recepción de SOAP](../core/how-to-configure-a-soap-receive-location.md).  
  
 **Las ubicaciones de recepción de soporte técnico de inicio de sesión único empresarial para SOAP**  
  
 Internet Information Server (IIS) recibe una solicitud SOAP de un cliente Web y, posteriormente, procede a autenticar al usuario y pasa el identificador de seguridad al adaptador de SOAP. Si el método de autenticación de IIS es Autenticación de texto implícita, Autenticación básica o Autenticación de Windows integrada, el adaptador de SOAP llama al almacén de credenciales de SSO para obtener un vale cifrado basado en el usuario autenticado. Este vale se almacena como el **SSOTicket** propiedad en la propiedad de contexto del mensaje.  
  
 En un escenario de paso, el motor de mensajería de BizTalk dirige el mensaje a la base de datos de cuadros de mensajes. Cuando un adaptador de envío recibe el mensaje de la base de datos de cuadros de mensajes, llama al método RedeemTicket, con el vale cifrado y el nombre de la aplicación, a fin de recuperar del almacén de SSO las credenciales de seguridad de la aplicación. El adaptador de envío utiliza entonces las credenciales externas para conectarse a la aplicación y procesar la solicitud. Para obtener más información sobre las aplicaciones afiliadas, vea [aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md).  
  
 En escenarios en los que una orquestación llama al adaptador de envío, el motor de mensajería de BizTalk envía el mensaje a la base de datos de cuadro de mensajes. La orquestación debe asegurarse de que tanto el **SSOTicket** propiedad de contexto y la **Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID** son propiedad de contexto del mensaje que contiene el vale mantiene. Cuando el adaptador recibe el mensaje de la base de datos de cuadro de mensajes, el adaptador llama al método RedeemTicket con el vale cifrado para recuperar las credenciales de servidor del almacén de SSO. El usuario que diseñe la orquestación deberá copiar específicamente esta propiedad en el mensaje.  
  
 **Compatibilidad con inicio de sesión único de SharePoint Portal Server SOAP de ubicaciones de recepción**  
  
 Cuando se integra con SharePoint Portal, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solo admite el uso del inicio de sesión único (SSO) de Microsoft SharePoint Portal Server a través del adaptador de SOAP. SharePoint Portal Server crea vales de SSO y los envía a BizTalk Server en un encabezado SOAP de la solicitud SOAP. Cuando el adaptador de SOAP recibe una solicitud que contiene un vale de SSO, el vale se almacena como el **SSOTicket** propiedad en la propiedad de contexto del mensaje. Esta misma propiedad contendrá un vale de SSO empresarial. Cada mensaje de BizTalk solo puede tener asociado un vale de SSO.  
  
 En los escenarios de paso y de orquestación, el tratamiento de los vales de SSO recibidos de SharePoint Portal Server será el mismo que si el vale lo hubiese creado el adaptador de SOAP mediante SSO empresarial. Cuando un adaptador de envío recibe un mensaje, llama a la **RedeemTicket** método con el cifrado de vale por SharePoint Portal Server generado. No es necesario notificar al adaptador de envío que existen vales de SSO distintos. El **RedeemTicket** método determinará qué sistema de SSO generó el vale y lo canjeará en el lugar adecuado.  
  
 **Uso combinado de Enterprise SSO de SharePoint Portal Server y SSO**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite el uso simultáneo de ambos sistemas SSO. La interfaz API podrá distinguir los vales generados por cada SSO, y procederá a canjearlos en la base de datos de SSO que corresponda. Si utiliza ambos sistemas SSO al mismo tiempo, las siguientes reglas determinan qué vale de SSO de recepción SOAP promueve la ubicación a la **SSOTicket** propiedad de contexto:  
  
- Si no se habilita ningún sistema de SSO, no se promocionará el vale.  
  
- Cuando el sistema de SSO empresarial está habilitado, pero el SSO de SharePoint Portal Server no lo está, se recupera y promociona el vale de SSO empresarial.  
  
- Cuando el SSO de SharePoint Portal Server está habilitado, pero el SSO empresarial no lo está, se promociona el vale de SSO de SharePoint Portal Server existente.  
  
- Si se ha habilitado el SSO empresarial y el SSO de SharePoint Portal Server:  
  
  -   Si se recibe el vale de SSO de SharePoint Portal Server, se promociona dicho vale.  
  
  -   Si no se recibe el vale de SSO de SharePoint Portal Server, se recupera y promociona el vale de SSO empresarial.  
  
  **Compatibilidad de inicio de sesión único para el adaptador de envío SOAP**  
  
  Si está habilitado el inicio de sesión único, cuando un puerto de envío SOAP recibe un mensaje con el **Secure** propiedad (**SSOTicket**), llama al servidor SSO para validar y canjear el vale para una aplicación afiliada. La aplicación de administración, los administradores afiliados o los administradores de SSO de la aplicación afiliada pueden llamar a SSO para canjear un vale. SSO se encarga entonces de descifrar el vale y de obtener las credenciales de servidor. Los escenarios de paso a través y la orquestación son los mismos para el puerto de envío SOAP, como se describe en la sección "Enterprise SSO soporte técnico para SOAP ubicaciones de recepción" del tema [único inicio de sesión de soporte técnico para el adaptador de SOAP](../core/single-sign-on-support-for-the-soap-adapter.md).  
  
  De manera predeterminada, el puerto de envío de SOAP no habilita el SSO. Para obtener más información acerca de cómo habilitar el inicio de sesión único para el puerto de envío SOAP, vea [cómo configurar un puerto de envío SOAP](../core/how-to-configure-a-soap-send-port.md).