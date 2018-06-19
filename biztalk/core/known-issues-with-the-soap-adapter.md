---
title: Problemas conocidos con el adaptador de SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 671510c6901fc399580ab73018e67eadc86f7212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262852"
---
# <a name="known-issues-with-the-soap-adapter"></a>Problemas conocidos del adaptador de SOAP
Esta sección contiene información que puede servir de ayuda para evitar errores.  
  
## <a name="known-issues"></a>Problemas conocidos  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a>Se produce un rendimiento muy bajo del adaptador de SOAP o éste genera errores de carga  
  
##### <a name="problem"></a>Problema  
 Se produce un rendimiento muy bajo del adaptador de SOAP o éste genera errores de carga  
  
##### <a name="cause"></a>Causa  
 Este problema se debe a que las opciones de configuración predeterminadas para el adaptador de SOAP o los componentes de dependencia que afectan al adaptador de SOAP no se optimizan para el rendimiento de la carga.  
  
##### <a name="resolution"></a>Solución  
 Para resolver este problema, modifique las opciones de configuración del adaptador de SOAP o de los componentes de dependencia descritos en el tema [parámetros de configuración que afectan al rendimiento del adaptador](../core/configuration-parameters-that-affect-adapter-performance.md).  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a>Los componentes de canalización del codificador y del descodificador de MIME/SMIME no pueden codificar ni descodificar los datos procesados por el adaptador de SOAP  
  
##### <a name="problem"></a>Problema  
 Los componentes de canalización del codificador y del descodificador de MIME/SMIME no pueden codificar ni descodificar los datos procesados por el adaptador de SOAP  
  
##### <a name="cause"></a>Causa  
 Este problema se produce porque el adaptador de SOAP ensambla y desensambla los mensajes SOAP en la fase de adaptador del proceso.  
  
##### <a name="resolution"></a>Solución  
 Para solucionar este problema, use la opción Utilizar SSL para garantizar la comunicación segura para codificar mensajes procesados por el adaptador de SOAP. En el lado de envío, use la **huella digital del certificado de cliente** propiedad en la página de propiedades del adaptador SOAP para lograr esto. En el caso de la recepción, debe configurar el directorio virtual que aloja los servicios Web de BizTalk para las comunicaciones seguras de SSL.  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a>El AppDomain predeterminado que aloja el adaptador de SOAP se descarga, lo que causa un bloqueo del proceso de host.  
  
##### <a name="problem"></a>Problema  
 El proceso que aloja el adaptador de SOAP se bloquea, lo que hace que el resto de servicios Web del proceso se bloqueen. Esto puede ocasionar el siguiente error:  
  
 Se produjo un error al ejecutar la canalización: "Desconocido" origen: "desconocido"recibir puerto: TwoWayLatencyLoopBack_RxPort"URI:" / /twowaylatencyrxsoap/twowaylatencyws.asmx "razón: intentado tener acceso a un dominio de aplicación descargado.  
  
##### <a name="cause"></a>Causa  
 El adaptador de SOAP se ejecuta en el espacio de proceso de IIS. Si existe más de un servicio Web en el AppPool de IIS, todos los servicios Web terminan teniendo su propio AppDomain.  
  
 De forma predeterminada, todos los objetos de motor de mensajería se crean en el primer AppDomain (es decir,. el AppDomain que corresponde al primer servicio Web). Si por alguna razón el primer servicio Web está inactivo durante un período de tiempo prologado, IIS descarga el primer AppDomain. Cuando esto ocurre, todos los servicios del proceso de alojamiento dejan de poder usarse.  
  
##### <a name="resolution"></a>Solución  
 Para impedir que AppDomain se descargue, siga el procedimiento siguiente:  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server** y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En **consola de administración de BizTalk Server**, expandir **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **deconfiguracióndeplataforma**y, a continuación, haga clic en **Hosts**.  
  
3.  En la lista de Hosts, haga clic en el host necesario y, a continuación, haga clic en **configuración**.  
  
4.  En el **panel de configuración de BizTalk**, comprobar **dominio de aplicación predeterminado para adaptador aislado** en **General** ficha.  
  
 Al hacerlo, los objetos del motor de mensajería de BizTalk se crean en el AppDomain predeterminado en vez de en los suyos propios. Como el AppDomain predeterminado no se descarga nunca, el problema deja de producirse.  
  
#### <a name="the-soap-adapter-fails-to-register"></a>Se produce un error al registrar el adaptador de SOAP  
  
##### <a name="problem"></a>Problema  
 Cuando BizTalk Server intenta registrar el adaptador de SOAP (o HTTP), puede producirse el siguiente error:  
  
 "El motor de mensajería no pudo registrar un adaptador "SOAP". Detalles: "registro de varios tipos de adaptador dentro del mismo proceso no es un escenario admitido. Los adaptadores de recepción HTTP y SOAP, por ejemplo, no pueden coexistir en el mismo proceso".  
  
 O bien  
  
 "El motor de mensajería no pudo registrar un adaptador "HTTP". Detalles: "registro de varios tipos de adaptador dentro del mismo proceso no es un escenario admitido.  Los adaptadores de recepción HTTP y SOAP, por ejemplo, no pueden coexistir en el mismo proceso".  
  
##### <a name="cause"></a>Causa  
 Cuando se ejecuta [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, los adaptadores SOAP y HTTP no se pueden ejecutar en el mismo espacio de proceso o grupo de aplicaciones.  
  
##### <a name="resolution"></a>Solución  
 Si una instalación requiere que se usen adaptadores de SOAP y HTTP en el mismo servidor Web, deberán crearse grupos de aplicaciones separados para cada adaptador.  Una vez creados, los directorios virtuales de cada adaptador se asignan a un grupo de aplicaciones diferente.  
  
> [!NOTE]
>  Este problema no se produce en Windows XP ya que en estos sistemas operativos, los adaptadores SOAP y HTTP se ejecutan en espacios de proceso diferentes en IIS 5.x.  El adaptador de SOAP se ejecuta como una aplicación ASP.NET en el proceso aspnet_wp.exe.  El adaptador de HTTP se ejecuta en el espacio de proceso dedicado de dllhost.exe.  Por lo tanto, ambos adaptadores están aislados el uno del otro, lo que les permite ejecutarse en el mismo servidor Web simultáneamente.  
  
## <a name="see-also"></a>Vea también  
 [Solucionar problemas del adaptador SOAP](../core/troubleshooting-the-soap-adapter.md)