---
title: ¿Qué son los adaptadores de WCF? | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18ca8535-3386-4018-8b5b-d32bdb9ebf70
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41c942c7c2ef870b2a61c519e79fb8a124059f03
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="what-are-the-wcf-adapters"></a>¿Qué son los adaptadores de WCF?
Hay dos adaptadores de Windows Communication Foundation (WCF), un adaptador de recepción y un adaptador de envío. Utilice el adaptador de recepción WCF para recibir solicitudes de Servicio WCF. El adaptador de recepción WCF recibe una solicitud, crea un objeto de mensaje de BizTalk y promociona las propiedades asociadas al contexto de mensaje. Puede utilizar el adaptador de envío WCF para llamar a un Servicio WCF. El adaptador de envío WCF llama a los servicios WCF a través de los contratos sin tipo.  
  
> [!NOTE]
>  Si los adaptadores de WCF no son compatibles con la utilización de los servicios Web de estilo Llamada a procedimiento remoto (RPC) debido a que las partes de mensaje en los servicios Web de estilo RPC se refieren a los tipos de mensajes en vez de a los elementos de mensaje en los que los adaptadores de WCF utilizan elementos para las partes de mensaje. Le recomendamos que agregue los servicios Web de estilo RPC a través del asistente Agregar referencia Web para utilizar los servicios Web en los proyectos de BizTalk.  
  
## <a name="web-services-standards-support"></a>Compatibilidad con los estándares de los servicios Web  
 Los adaptadores de WCF proporcionan compatibilidad con los estándares WS-*, por ejemplo, WS-Addressing, WS-Security y WS-AtomicTransaction. WS-ReliableMessaging no es compatible con esta versión de los adaptadores de WCF. Para obtener una lista de especificaciones admitidas por WCF, vea [ http://go.microsoft.com/fwlink/?LinkId=88314 ](http://go.microsoft.com/fwlink/?LinkId=88314).  
  
### <a name="ws-addressing"></a>WS-Addressing  
 Los adaptadores de WCF se basan en la compatibilidad de estándares WS-Addressing que proporciona WCF. En los adaptadores de WCF, están disponibles las siguientes características:  
  
-   Configuración de la dirección de extremos de puerto de envío obtenido a través de la solicitud de intercambio de metadatos.  
  
-   Configuración de los encabezados de dirección para la dirección de extremos de puerto de envío.  
  
-   Configuración de los encabezados de dirección para el extremo expuesto en la ubicación de recepción de BizTalk.  
  
### <a name="ws-security"></a>WS-Security  
 Los adaptadores de WCF se basan en la compatibilidad de estándares de seguridad que proporciona WCF. Los siguientes estándares son compatibles con los adaptadores de WCF:  
  
-   Seguridad de servicios Web: Seguridad de mensajes SOAP (WS-Security) 1.0 y 1.1  
  
-   Lenguaje de conversación segura de servicios Web (WS-SecureConversation)  
  
-   Lenguaje de confianza de servicios Web (WS-Trust)  
  
-   Perfil de token de certificado X.509 de seguridad de servicios Web  
  
-   Perfil 1.0 de token de nombre de usuario de seguridad de servicios Web  
  
-   Perfil 1.0 de token de Kerberos de seguridad de servicios Web  
  
#### <a name="service-authentication-types"></a>Tipos de autenticación de servicio  
 Son compatibles los siguientes tipos de autenticación de servicios WCF:  
  
-   None  
  
-   Windows  
  
-   Certificado  
  
#### <a name="client-authentication-types"></a>Tipos de autenticación de cliente  
 Son compatibles los siguientes tipos de autenticaciones de cliente WCF:  
  
-   Anónimo  
  
-   UserName  
  
-   Windows  
  
-   Certificado  
  
#### <a name="security-modes"></a>Modos de seguridad  
 Se admiten los siguientes modos de seguridad:  
  
-   Transporte  
  
-   de mensaje  
  
-   Mixed (autenticación de nivel de mensaje y seguridad de nivel de transporte)  
  
### <a name="ws-atomictransaction"></a>WS-AtomicTransaction  
 Los adaptadores de WCF-WsHttp, WCF-NetTcp y WCF-NetMsmq son compatibles con el protocolo WS-AtomicTransaction. Esta compatibilidad permite los siguientes escenarios:  
  
-   Envío transaccional de mensajes en la base de datos de cuadro de mensajes.   
  
-   Transmisión transaccional de mensajes del cuadro de mensajes a un destino transaccional.  
  
> [!NOTE]
>  El ámbito transaccional está limitado por el cuadro de mensajes. Por ejemplo, una orquestación de BizTalk no puede participar en una transacción de cliente. Del mismo modo, un extremo de destino no puede participar en una transacción que inicia una orquestación de BizTalk.  
  
#### <a name="transactional-submission"></a>Envío transaccional  
 Para los adaptadores de WCF-WsHttp y WCF-NetTcp, está habilitado el envío transaccional a BizTalk Server seleccionando la **Habilitar transacciones** casilla de verificación en el cuadro de diálogo de propiedades de transporte de recepción ubicación. Para el adaptador de WCF-NetMsmq, el **transaccional** casilla está activada de forma predeterminada. Si las colas de mensaje de las que está extrayendo los mensajes no están marcadas como transaccionales, necesitará quitar esta casilla de verificación o, en caso contrario, recibirá un mensaje de error.  
  
 Si se habilita la funcionalidad de transacciones, se envían los mensajes a la base de datos de cuadro de mensajes mediante las transacciones de los clientes. Si un cliente intenta enviar los mensajes fuera del ámbito transaccional, el adaptador devolverá una excepción al cliente. Sin embargo, no se suspenderán los mensajes. Si se deshabilita la funcionalidad de transacciones, se envían los mensajes a la base de datos de cuadro de mensajes sin usar las transacciones de los clientes. Si un cliente intenta enviar los mensajes dentro del ámbito transaccional, el adaptador devolverá una excepción al cliente y no se suspenderán los mensajes.  
  
#### <a name="transactions-and-receive-location-type"></a>Transacciones y tipo de ubicación de recepción  
 El envío transaccional sólo está disponible para las ubicaciones de recepción unidireccionales. Si un cliente intenta enviar los mensajes en un ámbito transaccional para una ubicación de recepción bidireccional, se devolverá una excepción al cliente y no se suspenderán los mensajes.  
  
#### <a name="transactional-transmission"></a>Transmisión transaccional  
 Para los adaptadores de WCF-WsHttp y WCF-NetTcp, se habilita la transmisión transaccional de BizTalk Server seleccionando la **Habilitar transacciones** casilla de verificación en el cuadro de diálogo de propiedades de transporte de envío puerto. Para el adaptador de WCF-NetMsmq, el **transaccional** casilla está activada de forma predeterminada. Si las colas de mensaje a las que está enviando los mensajes no están marcadas como transaccionales, necesitará quitar esta casilla de verificación o, en caso contrario, recibirá un mensaje de error.  
  
 Si se habilita la funcionalidad de transacciones, se transmiten y eliminan los mensajes de la base de datos de cuadro de mensajes en la transacción. Si el servicio de destino ha realizado una tarea después de recibir el mensaje y éste no se elimina del cuadro de mensajes, se anulará la transacción y se desharán todas las tareas de transacción del servicio. Si se deshabilita la funcionalidad de transacciones, se transmiten y eliminan los mensajes de la base de datos de cuadro de mensajes sin utilizar las transacciones.  
  
## <a name="single-sign-on-support"></a>Compatibilidad con el Inicio de sesión único (SSO)  
 Puede suplantar y adquirir el vale Inicio de sesión único (SSO) empresarial para utilizar SSO con adaptadores de WCF. Para obtener más información sobre cómo usar SSO con adaptadores de WCF, vea [compatibilidad de inicio de sesión único para los adaptadores de WCF](../core/single-sign-on-support-for-the-wcf-adapters.md).  
  
 La siguiente tabla resume los escenarios que no son compatibles cuando se usa la compatibilidad SSO con los adaptadores de recepción WCF.  
  
|Modo de seguridad|Credencial|  
|-------------------|----------------|  
|None|None|  
|Transporte|None|  
|de mensaje|None|  
|TransportWithMessageCredentials|None|  
|TransportCredentialOnly|None|  
  
## <a name="wcf-extensibility"></a>Extensibilidad de WCF  
 Puede extender la funcionalidad de WCF mediante el desarrollo de las siguientes extensiones y la utilización de éstas con los adaptadores de WCF-Custom y WCF-CustomIsolated:  
  
-   Enlaces personalizados  
  
-   Elementos de enlace personalizados  
  
### <a name="custom-bindings"></a>Enlaces personalizados  
 Los enlaces personalizados se desarrollan mediante el empaquetado de los elementos de enlace individuales en un contenedor que expone un subconjunto de las propiedades de configuración para un escenario de uso correspondiente. Necesita registrar la extensión de enlace mediante la instalación del ensamblado en la caché de ensamblados global (GAC) y, a continuación, agregar el elemento de extensión al archivo de configuración del equipo. Para usar los enlaces personalizados, necesita configurar los enlaces en cada servidor en el grupo de BizTalk. Después de que se instale el enlace, será visible para los adaptadores de WCF-Custom y WCF-CustomIsolated. Los adaptadores de WCF-Custom yWCF-CustomIsolated obtendrán las propiedades de configuración de enlace mediante la reflexión de los elementos de configuración de enlace.  
  
### <a name="custom-binding-elements"></a>Elementos de enlace personalizados  
 Los elementos de enlace personalizados se desarrollan mediante la adición o modificación de algunos componentes de canal de transporte. Por ejemplo, un componente de descompresión personalizado se empaqueta como elemento de enlace o un transporte UDP se representa como un elemento de enlace. Estos elementos de enlace pueden usarse en los adaptadores de WCF. Puede definir una pila de canal que utilice el elemento de enlace personalizado junto con otros elementos de enlace personalizados o estándares. Necesita registrar el elemento de enlace mediante la instalación del ensamblado en la GAC y, a continuación, agregar el elemento de extensión al archivo de configuración del equipo. Para usar los enlaces personalizados, necesita configurar los enlaces en cada servidor en el grupo de BizTalk. Para usar los elementos de enlace personalizado, puede seleccionar la **CustomBinding** tipo de enlace y, a continuación, agregar, modificar o reorganizar los elementos de enlace en el orden que desee.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Adaptador de recepción de WCF](../core/wcf-receive-adapter.md)  
  
-   [Adaptador de envío de WCF](../core/wcf-send-adapter.md)  
  
## <a name="see-also"></a>Vea también  
-  [Adaptadores de WCF](../core/wcf-adapters.md)   
-  **Referencia de contrato de servicio de adaptadores WCF** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]