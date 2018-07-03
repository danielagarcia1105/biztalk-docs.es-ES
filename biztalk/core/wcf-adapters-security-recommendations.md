---
title: Recomendaciones de seguridad de los adaptadores de WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, security
- security, WCF adapters
ms.assetid: bbaaca56-9ad5-4122-a8e9-6e975d308230
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f871c68277c487efcc7400a3ae54db749090148e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993453"
---
# <a name="wcf-adapters-security-recommendations"></a>Recomendaciones de seguridad de los adaptadores de WCF
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa los adaptadores de WCF para publicar (recibir) y consumir (enviar) servicios WCF. Se recomienda seguir estas directrices para proteger e implementar los adaptadores de WCF en el entorno.  
  
 Para obtener más información acerca de los adaptadores WCF, vea [adaptadores de WCF](../core/wcf-adapters.md). Para obtener más información acerca de los servicios WCF, vea [utilizando los servicios de WCF](../core/using-wcf-services.md)s.  
  
## <a name="security-recommendations-for-all-wcf-adapters"></a>Recomendaciones de seguridad para todos los adaptadores de WCF  
  
-   Puede utilizar el inicio de sesión único (SSO) empresarial en aquellas situaciones en que tenga que asignar el contenido de un usuario cliente a las credenciales de un sistema de servidor.  
  
-   No todos los servicios deben publicar metadatos. Mantener deshabilitada la publicación de metadatos reduce la superficie de ataque del servicio y disminuye el riesgo de que se produzca una divulgación involuntaria de la información. Para obtener más información acerca de los problemas de seguridad relativos a los metadatos, vea "Security Considerations with Metadata" en [ http://go.microsoft.com/fwlink/?LinkId=196671 ](http://go.microsoft.com/fwlink/?LinkId=196671).  
  
-   No todas las combinaciones de enlaces de extremo de metadatos y de enlaces de extremo de servicios son válidas. En algunos casos, las configuraciones de enlace de un extremo de metadatos deben coincidir con las configuraciones de enlace de su extremo de servicio. Por ejemplo, cuando los metadatos se sirven desde la misma ubicación que la ubicación de destino, el extremo de los metadatos no se puede configurar con un modo de seguridad que requiera transporte HTTP si la ubicación de recepción usa un modo de seguridad que se basa en HTTPS.  
  
    > [!NOTE]
    >  Al publicar metadatos a través del transporte HTTP para un extremo de servicio con la misma ubicación pero que requieren un modo de seguridad que se basa en el transporte HTTPS, en el archivo Web.config que genera el Asistente para publicación de WCF de BizTalk, debe establecer ambos el **httpsGetEnabled** y **httpGetEnabled** atributos a **true**.  
  
-   Los adaptadores de WCF aprovechan las características de seguridad de Windows Communication Foundation (WCF) para comunicarse. Es importante entender las capacidades y limitaciones de WCF en lo que respecta a la seguridad. Para obtener más información acerca de las características de seguridad de WCF, vea "Seguridad de Windows Communication Foundation" en [ http://go.microsoft.com/fwlink/?LinkId=87806 ](http://go.microsoft.com/fwlink/?LinkId=87806).  
  
## <a name="security-recommendations-for-the-isolated-wcf-adapters"></a>Recomendaciones de seguridad para los adaptadores de WCF aislados  
  
- Para obtener recomendaciones de seguridad para publicar servicios Web, consulte [habilitar los servicios Web](../core/enabling-web-services.md).  
  
- Los adaptadores de WCF aislados, como los adaptadores de WCF-CustomIsolated, WCF-BasicHttp y WCF-WSHttp, aprovechan el Protocolo de transferencia de hipertexto (HTTP) para enviar y recibir mensajes desde y hacia [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por lo tanto, debe seguir las recomendaciones de seguridad para proteger los servicios de Internet Information Server (IIS).  
  
- Al crear un grupo de aplicaciones para una ubicación de recepción WCF aislada, deberá configurarlo de modo que se ejecute en una cuenta que sea miembro del grupo de [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] del host aislado que ejecute el adaptador de recepción WCF, y del grupo de procesos de trabajo de Servicios de Internet Information Server (grupo IIS_WPG). A continuación, deberá configurar la instancia de host del adaptador de recepción WCF para que utilice esta cuenta. Si cambia la cuenta del grupo IIS_WPG, deberá asegurarse de actualizar también la instancia de host para que se ejecute en la nueva cuenta.  
  
## <a name="security-recommendations-for-the-wcf-custom-adapter"></a>Recomendaciones de seguridad para el adaptador de WCF-Custom  
  
-   Si utiliza el controlador de modo de núcleo HTTP (HTTP.sys) como una ubicación de recepción WCF-Custom el **httpsTransport** elemento de enlace para las comunicaciones de Secure Sockets Layer (SSL), la ubicación de recepción debe tener un certificado registrado para cada socket (combinación de puerto y dirección IP). Utilice la herramienta HttpCfg.exe para enlazar un certificado SSL con un puerto en el equipo. Para obtener más información, consulte "Cómo a: configurar un puerto con un certificado SSL" en [ http://go.microsoft.com/fwlink/?LinkId=86384 ](http://go.microsoft.com/fwlink/?LinkId=86384).  
  
## <a name="security-recommendations-for-the-wcf-netmsmq-adapter"></a>Recomendaciones de seguridad para el adaptador de WCF-NetMsmq  
  
-   Para usar el adaptador WCF-NetMsmq, tendrá que configurar la configuración de seguridad MSMQ para el adaptador WCF-NetMsmq en la misma manera que para el [netMsmqBinding](http://go.microsoft.com/fwlink/?LinkId=87813). Para obtener más información acerca de cómo configurar los parámetros de seguridad MSMQ para el **netMsmqBinding**, vea "Troubleshooting Queued Messaging" en [ http://go.microsoft.com/fwlink/?LinkId=87816 ](http://go.microsoft.com/fwlink/?LinkId=87816).  
  
## <a name="wcf-adapters-use-the-chaintrust-mode-to-validate-certificates"></a>Los adaptadores de WCF usan el modo ChainTrust para validar certificados.  
  
-   Dado que el uso de adaptadores de recepción WCF estándar la [ChainTrust](http://go.microsoft.com/fwlink/?LinkId=88960) modo para validar los certificados de cliente y servicio, debe instalar la cadena de certificados de entidad emisora de certificados para validar los certificados X.509. Puede usar el adaptador de WCF-Custom o de WCF-CustomIsolated para cambiar este comportamiento predeterminado.  
  
## <a name="security-auditing-for-the-wcf-adapters"></a>Auditoría de seguridad de los adaptadores de WCF  
  
- Los adaptadores de WCF no utilizan las características de auditoría de seguridad de WCF de forma predeterminada. Hay diversos modos de habilitar las características de auditoría de seguridad de WCF para los adaptadores de WCF. Para obtener más información acerca de las características de auditoría de seguridad WCF, vea "Auditing Security Events" en [ http://go.microsoft.com/fwlink/?LinkId=88975 ](http://go.microsoft.com/fwlink/?LinkId=88975).  
  
- Para usar la seguridad WCF características de auditoría con el adaptador de recepción WCF-Custom, puede configurar el **ServiceSecurityAuditBehavior** para las ubicaciones de recepción.  
  
- Para los adaptadores de WCF de tipo En curso, puede habilitar los contadores de rendimiento a través del archivo BTSNTSvc.exe.config. Para los adaptadores WCF aislados, puede habilitar el seguimiento de WCF modificando el archivo Web.config que el Asistente para publicación de servicio WCF de BizTalk crea en la carpeta de aplicación Web. Para modificar los archivos BTSNtSvc.exe.config o Web.config, abra el archivo de configuración y, a continuación, configure el seguimiento de WCF, como se indica en el ejemplo de configuración siguiente:  
  
  > [!NOTE]
  >  El archivo BTSNTSvc.exe.config siempre está ubicado en el mismo directorio que el archivo BTSNTSvc.exe, que normalmente es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].  
  > 
  > [!NOTE]
  >  Después de modificar el archivo BTSNTSvc.exe.config, debe reiniciar las instancias de host que ejecutan las ubicaciones de recepción WCF de tipo En curso.  
  
  ```  
  <configuration>  
      <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="ServiceBehaviorConfiguration">  
              <serviceSecurityAudit  
                        auditLogLocation="Application"  
                        suppressAuditFailure="true"  
                        serviceAuthorizationAuditLevel="SuccessOrFailure"  
  messageAuthenticationAuditLevel="SuccessOrFailure" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
        <services>  
          <service name="Microsoft.BizTalk.Adapter.Wcf.Runtime.BizTalkServiceInstance" behaviorConfiguration="ServiceBehaviorConfiguration">  
          </service>  
        </services>        
      </system.serviceModel>  
  </configuration>  
  ```  
  
- También se puede usar un contador de rendimiento relacionado con la seguridad, como las llamadas de seguridad no autorizadas, para supervisar los adaptadores de WCF. Para obtener más información sobre cómo habilitar los contadores de rendimiento de WCF, vea [contadores de rendimiento de los adaptadores de WCF](../core/wcf-adapters-performance-counters.md).  
  
## <a name="see-also"></a>Vea también  
 [Planear la seguridad](../core/planning-for-security.md)