---
title: Propiedades de configuración del adaptador HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, properties
- receive locations, adapters
- HTTP adapters, code sample
- HTTP adapters, send ports
- HTTP adapters, receive locations
- send ports, adapters
ms.assetid: 3d4e9d88-ea40-4478-a0cf-77057fadd3b2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f08106c698d50e95c36b8325cc3d92aa0debb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258660"
---
# <a name="http-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de HTTP
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción de un adaptador de HTTP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|ReturnCorrelationHandle|VT_BOOL|Especificar que, si la recepción es correcta, la ubicación de recepción envíe el token de correlación del mensaje enviado en la respuesta HTTP al cliente.|Esta propiedad sólo es válida para las ubicaciones de recepción unidireccionales.<br /><br /> Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|Ninguno|  
|ResponseContentType|VT_BSTR|Especificar el tipo de contenido de los mensajes de respuesta HTTP que la ubicación de recepción envía a los clientes.|Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|El valor predeterminado es texto/xml.|  
|SuspendFailedRequests|VT_BOOL|Especificar si se deben suspender o no las solicitudes HTTP que dan error en el procesamiento de entrada.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor de 0 (falso) indica que se descarte la solicitud con errores y se envíe un código de estado de error (401 o 500) al cliente.<br /><br /> El valor de -1 (verdadero) indica que se suspendan las solicitudes con errores y se envíe un código de estado "Aceptado" (200) al cliente para puertos de recepción unidireccionales o un código de estado "Error" (500) al cliente para puertos de recepción bidireccionales.<br /><br /> El valor predeterminado es 0 (falso).|  
|UseSSO|VT_BOOL|Especificar que se use el inicio de sesión único (SSO) empresarial.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|Bucle invertido|VT_BOOL|Especificar que el mensaje de solicitud recibido en esta ubicación se enrute a un puerto de envío o se devuelva a esta ubicación de recepción para enviarlo como respuesta.|Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
<ResponseContentType vt="8">text/xml</ResponseContentType>  
<SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
<UseSSO vt="11">-1</UseSSO>  
<LoopBack vt="11">-1</LoopBack>  
</CustomProps></  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de HTTP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|Especificar el puerto del servidor proxy para este puerto de envío.|Los valores válidos son de 0 a 65535.|Esta propiedad no necesita un valor si UseProxy está establecida en 0 (falso).<br /><br /> El valor predeterminado es 80.|  
|RequestTimeout|VT_I4|Especificar el tiempo de espera en segundos para la transmisión HTTP/HTTPS.|Los valores válidos son de 0 a MAX_LONG.|Si el adaptador de HTTP no recibe respuesta en este tiempo, el servicio registra el error y vuelve a enviar el mensaje según lo establecido en la infraestructura de reintentos.<br /><br /> Si se establece en cero (0), el motor de mensajería de BizTalk calcula el tiempo de espera en función del tamaño del mensaje de solicitud. Si no proporciona ningún valor, se usa el valor del controlador.|  
|Certificado|VT_BSTR|Especificar la huella digital del certificado de cliente que se utilizará para establecer una conexión de Capa de sockets seguros (SSL).|Longitud mínima: 0<br /><br /> Longitud máxima: 59|El valor predeterminado está vacío.|  
|AuthenticationScheme|VT_BSTR|Especificar el tipo de autenticación que se utilizará con el servidor de destino.|Los valores válidos son:<br /><br /> -Anónimo<br />-Básico<br />-Resumen<br />-Kerberos|El valor predeterminado es Anonymous (anónimo).|  
|Nombre de usuario|VT_BSTR|Especificar el nombre de usuario que se utilizará para la autenticación en el servidor de destino.|Esta propiedad necesita un valor si se usa AuthenticationScheme establecida en Basic (básica) o Digest (implícita) y no se utiliza el Inicio de sesión único (SSO) empresarial.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|Ninguno|  
|EnableChunkedEncoding|VT_BOOL|Especificar el uso de la codificación fragmentada.|La codificación fragmentada se deshabilita implícitamente si el controlador de envío HTTP se configura como Utilizar proxy.<br /><br /> Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|Si esta opción está habilitada, el adaptador HTTP utilizará la codificación fragmentada HTTP con el tamaño máximo de fragmento de 8Kb.<br /><br /> El valor predeterminado es 0 (falso).|  
|UseProxy|VT_BOOL|Especificar si el controlador de envío HTTP usa un servidor proxy.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|ProxyName|VT_BSTR|Especificar la dirección del servidor proxy para este puerto de envío.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Esta propiedad no necesita un valor si UseProxy está establecida en 0 (falso).|  
|UseSSO|VT_BOOL|Especificar si se utiliza el inicio de sesión único (SSO) para recuperar credenciales de cliente para la autenticación con el servidor de destino.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|Contraseña|VT_NULL|Especificar la contraseña que se utilizará para la autenticación con el servidor de destino.|Esta propiedad necesita un valor si se usa AuthenticationScheme establecida en Basic (básica) o Digest (implícita) y no se utiliza el Inicio de sesión único (SSO) empresarial.<br /><br /> Este valor siempre se establece en NULL cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|Establezca el tipo para esta propiedad en VT_BSTR (vt="8") antes de importar el archivo de enlace si proporciona un valor para este campo.|  
|MaxRedirects|VT_I4|Especificar el número máximo de redirecciones permitidas para el mensaje que se está enviando.|Los valores válidos son de 0 a 10.|El valor predeterminado es 5.|  
|ContentType|VT_BSTR|Especificar el tipo de contenido de los mensajes de solicitud.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Si no se proporciona ningún valor, se utiliza el valor del controlador.|  
|ProxyPassword|VT_NULL|Especificar la contraseña de usuario para la autenticación con el servidor proxy.|Este valor siempre se establece en NULL cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256|Esta propiedad no necesita un valor si UseProxy está establecida en 0 (falso).|  
|ProxyUsername|VT_BSTR|Especificar el nombre de usuario para la autenticación con el servidor proxy.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Esta propiedad no necesita un valor si UseProxy está establecida en 0 (falso).|  
|UseHandlerSetting|VT_BOOL|Especificar que la configuración del puerto de envío debe utilizar la configuración del servidor proxy indicada para el controlador de envío HTTP.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es -1 (verdadero).|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<ProxyPort vt="3">80</ProxyPort>  
<RequestTimeout vt="3">60</RequestTimeout>  
<Certificate vt="8">A7 6D F9 06 5E FC 97 66 75 59 B5 D6 67 0C 84 DC 64 F5 BF B9</Certificate>  
<AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
<Username vt="8">authenticateduser</Username>  
<EnableChunkedEncoding vt="11">-1</EnableChunkedEncoding>  
<UseProxy vt="11">-1</UseProxy>  
<ProxyName vt="8">proxyserver</ProxyName>  
<UseSSO vt="11">0</UseSSO>  
<Password vt="1" />  
<MaxRedirects vt="3">5</MaxRedirects>  
<ContentType vt="8">text/xml</ContentType>  
<ProxyPassword vt="1" />  
<ProxyUsername vt="8">proxyuser</ProxyUsername>  
<UseHandlerSetting vt="11">0</UseHandlerSetting>  
</CustomProps>  
```