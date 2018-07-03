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
# <a name="configuring-remote-debugging-for-orchestrations"></a><span data-ttu-id="39cc9-102">Configurar la depuración remota para las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="39cc9-102">Configuring Remote Debugging for Orchestrations</span></span>
<span data-ttu-id="39cc9-103">Puede configurar completamente la depuración remota entre cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="39cc9-103">You can completely configure remote debugging between client and server.</span></span> <span data-ttu-id="39cc9-104">La configuración del cliente se especifica en Microsoft.XLANGs.BizTalk.Client.dll.config. La configuración del servidor se especifica en BTSNTSvc.exe.config. La siguiente es una lista de la configuración predeterminada para cada uno.</span><span class="sxs-lookup"><span data-stu-id="39cc9-104">The client configuration is specified in Microsoft.XLANGs.BizTalk.Client.dll.config. The server configuration is specified in BTSNTSvc.exe.config. The following is a listing of the default configuration for each.</span></span>  
  
## <a name="client-microsoftxlangsbiztalkclientdllconfig"></a><span data-ttu-id="39cc9-105">Cliente (Microsoft.XLANGs.BizTalk.Client.dll.config)</span><span class="sxs-lookup"><span data-stu-id="39cc9-105">Client (Microsoft.XLANGs.BizTalk.Client.dll.config)</span></span>  
  
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
  
## <a name="serverbtsntsvcexeconfig"></a><span data-ttu-id="39cc9-106">Servidor (BTSNTSvc.exe.config)</span><span class="sxs-lookup"><span data-stu-id="39cc9-106">Server(BTSNTSvc.exe.config)</span></span>  
  
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
  
## <a name="configurable-parameters"></a><span data-ttu-id="39cc9-107">Parámetros configurables</span><span class="sxs-lookup"><span data-stu-id="39cc9-107">Configurable Parameters</span></span>  
 <span data-ttu-id="39cc9-108">El parámetro predeterminado asegura la configuración máxima de seguridad.</span><span class="sxs-lookup"><span data-stu-id="39cc9-108">The default ensures maximum security configuration.</span></span> <span data-ttu-id="39cc9-109">Sin embargo, se permite al usuario que cambie estos parámetros predeterminados y los archivos se incluyen en ACL puesto que están en la carpeta de archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="39cc9-109">However it is left to the user to change these defaults and these files are ACL'ed since they are in the program files folder.</span></span>  
  
 <span data-ttu-id="39cc9-110">El elemento \<proveedor / > es opcional y si no proporciona hará que los canales no se autentican mutuamente mediante los receptores personalizados.</span><span class="sxs-lookup"><span data-stu-id="39cc9-110">The element \<provider/> is optional and if not provided will cause the channels not to be mutually authenticated using the custom sinks.</span></span> <span data-ttu-id="39cc9-111">Sin embargo, puede ser arriesgado desactivar esta opción ya que se abrirán los canales.</span><span class="sxs-lookup"><span data-stu-id="39cc9-111">However this is a dangerous option to turn off as it will open up the channels.</span></span> <span data-ttu-id="39cc9-112">Esto puede hacerse para obtener un rendimiento mejor, y cuando no exista riesgo de ataques a la seguridad.</span><span class="sxs-lookup"><span data-stu-id="39cc9-112">This can be done for better performance and when security attacks are not a concern.</span></span>  
  
 <span data-ttu-id="39cc9-113">El elemento de canal puede tener la propiedad rejectRemoteRequests = trae, que habilitará solo las llamadas locales y rechazará solicitudes remotas.</span><span class="sxs-lookup"><span data-stu-id="39cc9-113">The channel element can have property rejectRemoteRequests = true which will enable only local calls and reject remote requests.</span></span>  
  
 <span data-ttu-id="39cc9-114">El atributo securityPackage del \<serverProviders / > elemento puede tener cualquiera de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="39cc9-114">The securityPackage attribute in the \<serverProviders/> element can have any of the following values:</span></span>  
  
- <span data-ttu-id="39cc9-115">negotiate</span><span class="sxs-lookup"><span data-stu-id="39cc9-115">negotiate</span></span>  
  
- <span data-ttu-id="39cc9-116">ntlm</span><span class="sxs-lookup"><span data-stu-id="39cc9-116">ntlm</span></span>  
  
- <span data-ttu-id="39cc9-117">Kerberos</span><span class="sxs-lookup"><span data-stu-id="39cc9-117">Kerberos</span></span>  
  
  <span data-ttu-id="39cc9-118">El atributo authenticationLevel del \<serverProviders / > elemento puede tener cualquiera de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="39cc9-118">The authenticationLevel attribute in the \<serverProviders/> element can have any of the following values:</span></span>  
  
- <span data-ttu-id="39cc9-119">packetPrivacy: los mensajes se cifrarán o descifrarán</span><span class="sxs-lookup"><span data-stu-id="39cc9-119">packetPrivacy  - the messages will be encrypted/decrypted</span></span>  
  
- <span data-ttu-id="39cc9-120">packetIntegrity: los mensajes se firmarán o comprobarán</span><span class="sxs-lookup"><span data-stu-id="39cc9-120">packetIntegrity – the messages will be signed/verified</span></span>  
  
- <span data-ttu-id="39cc9-121">call: los mensajes se enviarán tal cual</span><span class="sxs-lookup"><span data-stu-id="39cc9-121">call  - the messages will be sent as is</span></span>  
  
  <span data-ttu-id="39cc9-122">El atributo ref del \<canal / > elemento se puede cambiar a tcp o http.</span><span class="sxs-lookup"><span data-stu-id="39cc9-122">The ref attribute in the \<channel/> element can be changed to tcp or http.</span></span> <span data-ttu-id="39cc9-123">El puerto y el nombre de atributo en el \<canal / > puede también cambia el elemento para valores explícitos.</span><span class="sxs-lookup"><span data-stu-id="39cc9-123">The port and name attribute in the \<channel/> element can be changed as well to explicit values.</span></span>  
  
  <span data-ttu-id="39cc9-124">Para obtener más información, consulte la Guía del desarrollador de .NET Framework (la sección correspondiente a las propiedades de configuración del formateador y del canal).</span><span class="sxs-lookup"><span data-stu-id="39cc9-124">For more information, see .NET Framework Developer's Guide (Channel and formatter configuration properties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cc9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="39cc9-125">See Also</span></span>  
 [<span data-ttu-id="39cc9-126">Depuración de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="39cc9-126">Debugging Orchestrations</span></span>](../core/debugging-orchestrations.md)