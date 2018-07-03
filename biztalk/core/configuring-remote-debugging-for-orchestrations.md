---
title: Configurar la depuración remota para las orquestaciones | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.XLANGs.BizTalk.Client.dll.config, code sample
- BTSNTSvc.exe.config, code sample
- orchestrations, debugging
- building, debugging
- building, code sample
ms.assetid: 722efaec-d160-48dc-b94b-0733c9904d98
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f5d28c13cb9da4454efcad1a43a4048c8881ea8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967293"
---
# <a name="configuring-remote-debugging-for-orchestrations"></a>Configurar la depuración remota para las orquestaciones
Puede configurar completamente la depuración remota entre cliente y servidor. La configuración del cliente se especifica en Microsoft.XLANGs.BizTalk.Client.dll.config. La configuración del servidor se especifica en BTSNTSvc.exe.config. La siguiente es una lista de la configuración predeterminada para cada uno.  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a>Cliente (Microsoft.XLANGs.BizTalk.Client.dll.config)  
  
```  
<configuration>  
     <system.runtime.remoting>  
  
 <channelSinkProviders>  
       <clientProviders>  
         <provider id="sspi" type="Microsoft.BizTalk.XLANGs.Client.SecurityClientChannelSinkProvider,Microsoft.XLANGs.BizTalk.Client" securityPackage="negotiate" authenticationLevel="packetPrivacy"/>  
       </clientProviders>  
</channelSinkProviders>  
  
<application>  
<channels>  
    <channel ref="tcp" port="0" name="">  
       <clientProviders>  
             <formatter ref="binary"/>  
             <provider ref="sspi" />  
        </clientProviders>  
       <serverProviders>  
             <formatter ref="binary" typeFilterLevel="Full"/>  
       </serverProviders>  
    </channel>  
</channels>  
</application>  
  </system.runtime.remoting>  
</configuration>  
```  
  
## <a name="serverbtsntsvcexeconfig"></a>Servidor (BTSNTSvc.exe.config)  
  
```  
<?xml version="1.0" ?>  
<configuration>  
    <runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
            <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking;Tracking\interop" />  
        </assemblyBinding>  
    </runtime>  
  
    <system.runtime.remoting>  
  
        <channelSinkProviders>  
            <serverProviders>  
                <provider id="sspi" type="Microsoft.BizTalk.XLANGs.BTXEngine.SecurityServerChannelSinkProvider,Microsoft.XLANGs.BizTalk.Engine" securityPackage="ntlm" authenticationLevel="packetPrivacy" />  
            </serverProviders>  
        </channelSinkProviders>  
  
        <application>  
            <channels>  
                <channel ref="tcp" port="0" name="">  
                <serverProviders>  
                    <provider ref="sspi" />  
                        <formatter ref="binary" typeFilterLevel="Full"/>  
                    </serverProviders>  
                </channel>  
            </channels>  
        </application>  
    </system.runtime.remoting>  
  
</configuration>  
```  
  
## <a name="configurable-parameters"></a>Parámetros configurables  
 El parámetro predeterminado asegura la configuración máxima de seguridad. Sin embargo, se permite al usuario que cambie estos parámetros predeterminados y los archivos se incluyen en ACL puesto que están en la carpeta de archivos de programa.  
  
 El elemento \<proveedor / > es opcional y si no proporciona hará que los canales no se autentican mutuamente mediante los receptores personalizados. Sin embargo, puede ser arriesgado desactivar esta opción ya que se abrirán los canales. Esto puede hacerse para obtener un rendimiento mejor, y cuando no exista riesgo de ataques a la seguridad.  
  
 El elemento de canal puede tener la propiedad rejectRemoteRequests = trae, que habilitará solo las llamadas locales y rechazará solicitudes remotas.  
  
 El atributo securityPackage del \<serverProviders / > elemento puede tener cualquiera de los siguientes valores:  
  
- negotiate  
  
- ntlm  
  
- Kerberos  
  
  El atributo authenticationLevel del \<serverProviders / > elemento puede tener cualquiera de los siguientes valores:  
  
- packetPrivacy: los mensajes se cifrarán o descifrarán  
  
- packetIntegrity: los mensajes se firmarán o comprobarán  
  
- call: los mensajes se enviarán tal cual  
  
  El atributo ref del \<canal / > elemento se puede cambiar a tcp o http. El puerto y el nombre de atributo en el \<canal / > puede también cambia el elemento para valores explícitos.  
  
  Para obtener más información, consulte la Guía del desarrollador de .NET Framework (la sección correspondiente a las propiedades de configuración del formateador y del canal).  
  
## <a name="see-also"></a>Vea también  
 [Depuración de orquestaciones](../core/debugging-orchestrations.md)