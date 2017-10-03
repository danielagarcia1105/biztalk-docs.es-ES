---
title: "Propiedades de configuración del adaptador SOAP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, send ports
- SOAP adapters, code samples
- SOAP adapters, properties
- receive locations, adapters
- SOAP adapters, receive locations
- send ports, adapters
ms.assetid: 0d033371-ee31-4e43-a7d3-e0975791d981
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f52fde9d80717d192d3a5b90548ccc01e87d2044
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="soap-adapter-configuration-properties"></a>Propiedades de configuración del adaptador de SOAP
En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para una ubicación de recepción de un adaptador de SOAP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|UseSSO|VT_BOOL|Especificar si se usará el inicio de sesión único.|-Valores válidos son:<br />--1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<UseSSO vt="11">0</UseSSO>  
</CustomProps>  
```  
  
 En la siguiente tabla se enumeran las propiedades de configuración que se pueden definir para un puerto de envío del adaptador de SOAP:  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|Especificar el puerto del servidor proxy para este puerto de envío.|Ninguno|Esta propiedad no necesita un valor a no ser que la propiedad UseProxy esté establecida en -1 (verdadero).<br /><br /> El valor predeterminado es 80.|  
|AuthenticationScheme|VT_BSTR|Especificar el tipo de autenticación que se utilizará con el servidor de destino.|Los valores válidos son:<br /><br /> -Anónimo<br />-Básico<br />-Resumen<br />: NTLM|El valor predeterminado es Anonymous (anónimo).|  
|Nombre de usuario|VT_BSTR|Especificar el nombre de usuario que se utilizará para la autenticación en el servidor de destino.|Longitud mínima: 0<br /><br /> Longitud máxima: 256|Esta propiedad no necesita un valor a no ser que la propiedad AuthenticationScheme esté establecida en Basic (básica) o Digest (implícita) y la propiedad UseSSO esté establecida en 0 (falso).|  
|UseProxy|VT_BOOL|Especificar si el controlador de envío SOAP usa un servidor proxy.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|UseSoap12|VT_BOOL|Especificar que se genere código de proxy que proporcione compatibilidad con el protocolo SOAP 1.2.|Si esta opción no está activada, se generará código de proxy compatible con SOAP 1.1.<br /><br /> Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|UsingOrchestration|VT_BOOL|Especificar si se usará el proxy del servicio Web asociado a la dirección de este puerto de envío.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es -1 (verdadero).|  
|UseSSO|VT_BOOL|Especificar que se use el inicio de sesión único (SSO) empresarial.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es 0 (falso).|  
|ProxyAddress|VT_BSTR|Especificar el nombre del servidor proxy.|Esta propiedad solo es válida si la propiedad UseProxy está establecida en -1 (verdadero).|Ninguno|  
|Contraseña|VT_NULL|Especificar la contraseña que se utilizará para la autenticación con el servidor de destino.|Este valor siempre se establece en NULL cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Esta propiedad no necesita un valor a no ser que la propiedad AuthenticationScheme esté establecida en Basic (básica) o Digest (implícita) y la propiedad UseSSO esté establecida en 0 (falso).|  
|AssemblyPath|VT_BSTR|Especificar la ruta de acceso del ensamblado que contiene el proxy de servicio Web.|Ninguno|Ninguno|  
|TypeName|VT_BSTR|Especificar el nombre de la clase que contiene el método Web que se va a invocar.|Ninguno|Ninguno|  
|MethodName|VT_BSTR|Especificar el método de la clase que se va a invocar.|Ninguno|Ninguno|  
|UseHandlerSetting|VT_BOOL|Especificar si se usará la configuración de proxy predeterminada del controlador de envío SOAP.|Los valores válidos son:<br /><br /> --1 (true)<br />-0 (false)|El valor predeterminado es -1 (verdadero).|  
|ClientCertificate|VT_BSTR|Especificar la huella digital de certificado de cliente que se utilizará para establecer una conexión.|Longitud mínima: 0<br /><br /> Longitud máxima: 59|Ninguno|  
|ProxyPassword|VT_NULL|Especificar la contraseña usada para la autenticación con el servidor proxy.|Este valor siempre se establece en NULL cuando se exporta un archivo de enlace. Este campo se debe rellenar de forma manual con la contraseña antes de importar el archivo de enlace en la configuración de BizTalk Server de destino.|Esta propiedad no necesita un valor si UseProxy está establecida en 0 (falso).|  
|ProxyUsername|VT_BSTR|Especificar el nombre de usuario que se usará para la autenticación en el servidor proxy.|Ninguno|Esta propiedad no necesita un valor a no ser que la propiedad UseProxy esté establecida en -1 (verdadero).|  
  
 En el siguiente código se muestra el formato de la cadena XML que se utiliza para establecer las propiedades:  
  
```  
<CustomProps>  
<ProxyPort vt="3">80</ProxyPort>  
<AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
<Username vt="8">domain\testuser</Username>  
<UseProxy vt="11">-1</UseProxy>  
<UseSoap12 vt="11">-1</UseSoap12>  
<UsingOrchestration vt="11">-1</UsingOrchestration>  
<UseSSO vt="11">0</UseSSO>  
<ProxyAddress vt="8">proxy</ProxyAddress>  
<Password vt="1" />  
<ProxyPort vt="3">80</ProxyPort>  
<AssemblyPath vt="8">C:\Websvc.dll</AssemblyPath>  
<TypeName vt="8">Websvc.svc</TypeName>  
<MethodName vt="8">WebMethod</MethodName>  
<UseHandlerSetting vt="11">0</UseHandlerSetting></  
<ClientCertificate vt="8">23779A5EEA9693A37409021EFCDAB713A3680C34</ClientCertificate>  
<ProxyPassword vt="1" />  
<ProxyUsername vt="8">proxyuser</ProxyUsername>  
</CustomProps>  
```