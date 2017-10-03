---
title: Propiedades de instancia de servicio en los servicios de host | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b317161-83a9-42d5-b24f-48ff1e54b94a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26d29575e282b7e558f223733ff7e7ce562f63ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="host-instance-service-properties-in-services"></a>Propiedades de servicio de instancia de host de los servicios
## <a name="host-instance-service-properties-in-services"></a>Propiedades de servicio de instancia de host de los servicios  
 Cuando se crea una instancia de host de BizTalk, también se crea un servicio en los servicios. En la tabla siguiente se describen las propiedades más comunes.  
  
|Opción|Description|  
|------------|-----------------|  
|General: **tipo de inicio**|Valor predeterminado se establece en **automática** para permitir que la instancia de host se inicie automáticamente cuando se reinicia el equipo. En un entorno de producción, normalmente siempre se establece esta propiedad en **automática**.|  
|Inicio de sesión: **cuenta**|Se define con la cuenta de usuario especificada al configurar BizTalk o al crear una instancia de host nueva. Si BizTalk y SQL Server se encuentran en equipos distintos, la cuenta debe ser una cuenta de dominio. Si BizTalk y SQL Server se encuentran en el mismo equipo, la cuenta puede ser una cuenta de dominio o una cuenta local.|  
|Recuperación: **primer error**|Valor predeterminado se establece en **reiniciar el servicio**. Si la instancia de host se detiene inesperadamente la primera vez, esta configuración intentará reiniciarla.<br /><br /> Si la instancia de host se inicia correctamente y, a continuación, se detiene, la **segundo error** se aplica la propiedad.<br /><br /> Si la instancia de host no se inicia, la **segundo error** no se aplicará la propiedad. No se volverá a intentar reiniciar. La instancia de host permanecerá parada.|  
|Recuperación: **segundo error**|Valor predeterminado se establece en **reiniciar el servicio**. Si la instancia de host se detiene inesperadamente la segunda vez, esta configuración intentará reiniciarla.<br /><br /> Si la instancia de host se inicia correctamente y, a continuación, se detiene, la **siguientes errores** se aplica la propiedad.<br /><br /> Si la instancia de host no se inicia, la **siguientes errores** no se aplicará la propiedad. No se volverá a intentar reiniciar. La instancia de host permanecerá parada.|  
|Recuperación: **siguientes errores**|Valor predeterminado se establece en **reiniciar el servicio**. Si la instancia de host se detiene inesperadamente la tercera vez, esta configuración intentará reiniciarla.<br /><br /> Si la instancia de host se inicia correctamente y, a continuación, se detiene, la **siguientes errores** propiedad continuarán aplicarse.<br /><br /> Si la instancia de host no se inicia, la **siguientes errores** no se aplicará la propiedad. No se volverá a intentar reiniciar. La instancia de host permanecerá parada.|  
|Recuperación: **reiniciar servicio después de**|El valor predeterminado es un minuto. Si es necesario, se puede aumentar.|  
|Dependencias|**Todos los** los componentes enumerados deben iniciarse antes de que se iniciará la instancia de host de BizTalk. Esto incluye el inicio de sesión único empresarial. Si usa Windows Server 2008, consulte el artículo siguiente de KB:<br /><br /> [942284](http://support.microsoft.com/kb/942284) no se puede iniciar el servicio de BizTalk A como se esperaba al reiniciar un equipo que ejecuta Windows Vista o Windows Server 2008|  
  
 **Tenga en cuenta** propiedades de instancias de host de BizTalk el en los servicios también se almacenan en HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\BTSSvc$*Nombredehostbiztalk* clave del registro.  
  
### <a name="recovery"></a>Recuperación  
 La capacidad de recuperación de los servicios no proporciona intentos de reinicio de servicio indefinidos en caso de error al iniciar el servicio de instancia de host. Al modificar las propiedades de recuperación, se puede mejorar el tiempo de actividad de una instancia de host de BizTalk. Estos son algunos de los escenarios más comunes que provocarían una interrupción de la instancia de host de BizTalk:  
  
-   Pérdida de conectividad de red con SQL Server  
  
-   Excepción de memoria insuficiente  
  
-   Infracción de acceso  
  
 **Escenarios potenciales**  
  
-   SQL Server deja de responder inesperadamente. En esta situación, el **primer error** se aplicará la propiedad. Con el valor predeterminado **primer error** y **reiniciar el servicio después** configuración, intenta reiniciar una sola se realiza después de un minuto. Si, después de un minuto, SQL Server sigue sin responder, no se volverá a intentar reiniciar. La instancia de host permanecerá parada.  
  
-   SQL Server está en clúster y se produce una conmutación por error. La conmutación por error dura más de 5 minutos. En este escenario, el valor predeterminado **primer error** y **reiniciar el servicio después** configuración intentará reiniciar una sola vez después de un minuto. No se podrá reiniciar porque SQL Server sigue sin conexión. Por lo tanto, no se volverá a intentar reiniciar. La instancia de host permanecerá parada.  
  
 **Recomendaciones**  
  
-   Al detener SQL Server o en caso de conmutación por error de clúster de SQL, detenga las instancias de host de BizTalk manualmente. Cuando SQL Server vuelva a estar en línea, reinicie las instancias de host.  
  
-   Si es algo habitual para una conmutación por error de clúster SQL tardará más de 1 minuto, aumente la **reiniciar el servicio después** valor de tiempo que tarde el clúster de SQL a estar en línea.  
  
-   Cuando SQL Server se mantiene por un administrador que no son de BizTalk, considere la posibilidad de aumentar la **reiniciar el servicio después** valor. Los administradores que no son de BizTalk tienden a detener e iniciar SQL Server sin considerar el impacto sobre BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Administrar hosts de BizTalk e instancias de host](../core/managing-biztalk-hosts-and-host-instances.md)