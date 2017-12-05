---
title: "Configuración del motor de orquestación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestration engine, examples
- orchestration engine, code sample
- orchestration engine, dehydration
- orchestration engine, configuring
ms.assetid: d4f253c3-317d-4b52-bf54-81d50f03eeb3
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5d2fae252d1b99f1a6393dc2f2ebbd45ed70a2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="orchestration-engine-configuration"></a>Configuración del motor de orquestación
El motor de orquestación utiliza un archivo XML denominado BTSNTSvc.exe.config para determinar determinados comportamientos. Por ejemplo, las propiedades de deshidratación y los valores predeterminados están configurados como XML en el archivo BTSNTSvc.exe.config y se leen cuando se inician todas las instancias de host que contienen una orquestación. Para obtener más información, consulte [orquestación deshidratación y rehidratación](../core/orchestration-dehydration-and-rehydration.md).  
  
 Un servicio lee esta información de configuración una vez que se ha iniciado. No se recogerá ningún cambio realizado a menos que se detenga y se reinicie el servicio.  
  
 Consulte los ejemplos que se muestran a continuación para los diferentes nodos y los posibles valores.  
  
## <a name="example-all-validations-on"></a>Ejemplo: todas las validaciones activadas  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section   
                     name="xlangs"  
                     type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <xlangs>  
              <Configuration>  
                     <Debugging   
                            ValidateAssemblies="true"  
                            ValidateSchemas="true"  
                            ValidateCorrelations="true"  
                            ExtendedLogging="true"  
                     />  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="example-assembly-validation-only"></a>Ejemplo: solo la validación de ensamblado  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section   
                     name="xlangs"  
                     type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess"  
              />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <xlangs>  
              <Configuration>  
                     <Debugging   
                            ValidateAssemblies="true"  
                            ExtendedLogging="false"  
                     />  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="example-remote-debugging-enabled"></a>Ejemplo: depuración remota habilitada  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
  
       <system.runtime.remoting>  
              <customErrors mode="on"/>  
              <channelSinkProviders>  
                     <serverProviders>  
                            <provider id="sspi"  
                                    type="Microsoft.BizTalk.XLANGs.BTXEngine.SecurityServerChannelSinkProvider,Microsoft.XLANGs.BizTalk.Engine" securityPackage="negotiate" authenticationLevel="packetPrivacy" />  
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
  
## <a name="example-appdomain-configuration"></a>Ejemplo: Configuración de dominio de aplicación  
 Los ensamblados se asignan a dominios con nombres utilizando reglas de asignación (consulte más detalles abajo). Si no se especifica ninguna regla para algunos ensamblados, estos se asignarán a un dominio ad hoc. El número de dichos ensamblados asignados por dominio ad hoc viene determinado por el valor de AssembliesPerDomain.  
  
```  
<?xml version="1.0" ?>  
<configuration>  
    <configSections>  
        <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
    </configSections>  
    <runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
            <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
        </assemblyBinding>  
    </runtime>  
    <xlangs>  
        <Configuration>  
            <!--   
                <!--   
AppDomain configuration.  
                Assemblies are assigned to named domains using assignment rules (see more below). If no rule is specified for some assembly, the assembly will be assigned to an ad hoc domain. The number of such assigned assemblies per ad hoc domain is determined by the value of AssembliesPerDomain.  
            -->-->   
            <AppDomains AssembliesPerDomain="10">  
                <!--   
                    <!--   
In this section the user may specify defualt configuration for any app domain created that does not have a named configuration associated with it (see AppDomainSpecs below)  
                    SecondsEmptyBeforeShutdown is the number of seconds that an app domain is empty (that is, it does not contain any orchestrations) before being unloaded. Specify -1 to signal that an app domain should never unload, even when empty.  
                    Similarly, SecondsIdleBeforeShutdown is the number of seconds that an app domain is idle (that is, it contains only dehydratable orchestrations) before being unloaded. Specify -1 to signal that an app domain should never unload when idle but not empty. When an idle but non-empty domain is shut down, all of the contained instances are dehydrated first.  
                -->  
                -->   
<DefaultSpec SecondsIdleBeforeShutdown="1200" SecondsEmptyBeforeShutdown="1800">  
                    <!--   
                        <!--   
BaseSetup is a serialized System.AppDomainSetup object. This is passed as-is to  
                        AppDomain.CreateAppDomain() and can be used to influence assembly search path etc.  
                    -->  
                    -->   
<BaseSetup>  
                        <ApplicationBase>c:\myAppBase</ApplicationBase>_0</ApplicationBase>   
                        <ConfigurationFile>c:\myAppBase\myConfig.config</ConfigurationFile>_0</ConfigurationFile>   
                    <DynamicBase>DynamicBase_0</DynamicBase>   
<DisallowPublisherPolicy>true</DisallowPublisherPolicy>   
<ApplicationName>ApplicationName_0</ApplicationName>   
<PrivateBinPath>PrivateBinPath_0</PrivateBinPath>   
<PrivateBinPathProbe>PrivateBinPathProbe_0</PrivateBinPathProbe>   
<ShadowCopyDirectories>ShadowCopyDirectories_0</ShadowCopyDirectories>   
<ShadowCopyFiles>ShadowCopyFiles_0</ShadowCopyFiles>   
<CachePath>CachePath_0</CachePath>   
<LicenseFile>LicenseFile_0</LicenseFile>   
<LoaderOptimization>NotSpecified</LoaderOptimization>   
</BaseSetup>  
                </DefaultSpec>  
                <!--   
                    - <!--   
In this section the user may specify named configurations for specific app domains, identified by their "friendly name". The format of any app-domain spec is identical to that of the default app-domain spec.  
                -->-->   
                <AppDomainSpecs>  
                    <AppDomainSpec Name="MyDomain1" SecondsIdleBeforeShutdown="-1" SecondsEmptyBeforeShutdown="12000">  
                        <BaseSetup>  
                            <PrivateBinPath>c:\PathForAppDomain1</PrivateBinPath>  
                        <PrivateBinPath>PrivateBinPath_0</PrivateBinPath>   
<PrivateBinPathProbe>PrivateBinPathProbe_0</PrivateBinPathProbe>   
</BaseSetup>  
                    </AppDomainSpec>  
                    <AppDomainSpec Name="MyFrequentlyUnloadingDomainMyTrashyDomain" SecondsIdleBeforeShutdown="60" SecondsEmptyBeforeShutdown="60" />   
                </AppDomainSpecs>  
                <!--   
                    <!--   
The PatternAssignmentRules and ExactAssignmentRules control assignment of assemblies to app domains.  
                    When a message arrives, the name of its corresponding orchestration's assembly is determined. Then, the assembly is assigned an app domain name. The rules guide this assignment. Exact rules are consulted first, in their order of definition, and then the pattern rules. The first match is used.  
                    If no match is found, the assembly will be assigned to an ad-hoc domain. The configuration and number of assemblies per ad-hoc domain is controlled by the AssembliesPerDomain attribute and the DefaultSpec section.  
                -->  
               -->   
- <ExactAssignmentRules>  
                    <!--   
                        <!--   
An exact assembly rule specifies a strong assembly name and an app domain name. If the strong assembly name equals the rule's assembly name, it is assigned to the corresponding app domain.  
                    -->-->   
                    <ExactAssignmentRule AssemblyName="BTSAssembly1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=9c7731c5584592ad"  
                       AssemblyName_0" AppDomainName="MyDomain1" />AppDomainName_1" />   
                    <ExactAssignmentRule AssemblyName="BTSAssembly2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=9c7731c5584592ad"AssemblyName_0" AppDomainName="AppDomainName_1" />   
                        AppDomainName="MyFrequentlyUnloadingDomain " />  
                <ExactAssignmentRule AssemblyName="AssemblyName_0" AppDomainName="AppDomainName_1" />   
</ExactAssignmentRules>  
                <PatternAssignmentRules>  
                    <!--   
                        <!--   
A pattern assignment rule specifies a regular expression and an app domain name. If the strong assembly name matches the expression, it is assigned to the corresponding app domain. This allows version independent assignment, assignment by public key token, or assignment by the custom assembly key.  
                    -->-->   
                    <!--  
                        assign all assemblies with name BTSAssembly3, regardless of version and public key,  
                        to the MyDomain1 app domain   
                    -->  
                    <PatternAssignmentRule AssemblyNamePattern=" BTSAssembly3, Version=\d.\d.\d.\d, Culture=neutral, PublicKeyToken=.{16}"AssemblyNamePattern_0" AppDomainName=" MyDomain1" />  
                <PatternAssignmentRule AssemblyNamePattern="AssemblyNamePattern_0" AppDomainName="AppDomainName_1" />   
<PatternAssignmentRule AssemblyNamePattern="AssemblyNamePattern_0" AppDomainName="AppDomainName_1" />   
</PatternAssignmentRules>  
            </AppDomains>  
        </Configuration>  
    </xlangs>  
</configuration>  
```  
  
## <a name="modifying-other-sections-of-the-btsntsvcexeconfig-file"></a>Modificar otras secciones del archivo BTSNTSvc.exe.config  
 Para obtener información acerca de cómo modificar los valores de deshidratación en BTSNTSvc.exe.config, consulte [propiedades de deshidratación predeterminado](../core/dehydration-default-properties.md).  
  
 El archivo de configuración BTSNTSvc.exe contiene otras secciones documentadas en la referencia general de .NET Framework. Para obtener más información acerca de la modificación de estas secciones, consulte el **esquema de archivo de configuración** de la referencia General de .NET Framework en [http://go.microsoft.com/FWLink/?LinkID=52964](http://go.microsoft.com/FWLink/?LinkID=52964).  
  
 Además de información de configuración específica de BizTalk, el archivo BTSNTSvc.exe.config también es donde los componentes de aplicación .NET que se ejecutan en el contexto de una orquestación, adaptador o canalización obtienen la información de configuración en tiempo de ejecución mediante el estándar de .NET  **\<appSettings\>**  etiqueta en el  **\<configuración\>**  etiqueta. Dado que BizTalk ya proporciona un mecanismo para adaptadores personalizados y componentes de canalización obtener información de configuración, la  **\<appSettings\>**  etiqueta en el archivo BTSNTSvc.exe.config haría normalmente utilizar componentes .NET personalizados llamados desde una orquestación. Por ejemplo:  
  
```  
<appSettings>  
     <add key="configParamName" value="configParamValue" />  
</appSettings>  
```  
  
## <a name="throttling-messages-per-orchestration"></a>Limitar mensajes por orquestación  
 Esta propiedad, que se especifica en el archivo btsntsvc.exe.config, evitará que una orquestación consuma demasiada memoria. Para ello, limitará el número de mensajes pendientes que puede tener. Continuarán todos los mensajes se entreguen en el cuadro de mensajes; Sin embargo, los mensajes en cola no se entregará a la orquestación hasta que ésta procese algunos de sus mensajes pendientes.  
  
 Para especificar esta propiedad en el archivo btsntsvc.exe.config (ubicado en el directorio raíz de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]), agregue el siguiente parámetro en el nodo Aplicación:  
  
```  
<configuration>  
            <application>  
                        <Throttling PauseAt="100" ResumeAt="50" />  
            </application>  
</configuration>  
```  
  
 En este ejemplo, cuando la orquestación alcanza los 100 mensajes pendientes, el cuadro de mensajes dejará de enviar más mensajes. Cuando el número de la orquestación de mensajes pendientes desciende a 50, especificará que el cuadro de mensajes puede reanudar el envío de mensajes. Puede especificar otros valores.  
  
 También debe habilitar esta característica, por host, en la base de datos. Para habilitar la limitación de mensajes para un host, debe editar la tabla dbo.Applications de la base de datos BizTalkMsgBoxDb. Para cada host que desea habilitar la limitación de mensajes por orquestación, establezca la marca fAttributes bit en 1. Sólo los hosts con fAttribute se en 1 le permitirá la limitación de mensajes por orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Depurar orquestaciones](../core/debugging-orchestrations.md)   
 [Lenguaje XLANG-s](../core/xlang-s-language.md)