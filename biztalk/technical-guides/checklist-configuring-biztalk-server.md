---
title: 'Lista de comprobación: Configuración de BizTalk Server | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: adfb5a5e-2a23-4f6c-865f-a3300bf3d01d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11c1348ef4ce34676cd206c08530f66f20730378
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299716"
---
# <a name="checklist-configuring-biztalk-server"></a>Lista de comprobación: Configuración de BizTalk Server
Siga estos pasos al preparar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para su uso en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno de producción.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Configurar hosts de BizTalk e instancias de host.|Separar enviar, recibir, procesar y funcionalidad de seguimiento en varios hosts. Esto proporciona flexibilidad al configurar la carga de trabajo y le permite detener un host sin que afecte a otros hosts. Para obtener más información, consulte [configurar Hosts e instancias de Host](../technical-guides/configuring-hosts-and-host-instances.md).|  
|Asegúrese de cumplir y comprender los límites máximos de prácticos de uso de memoria para una instancia de host de BizTalk.|[Límites máximos de prácticos de uso de memoria de una instancia de Host de BizTalk de 32 bits](../technical-guides/configuring-hosts-and-host-instances.md#BKMK_MemLimit)|  
|Configurar un host de seguimiento dedicado.|Use un host dedicado que no hace nada pero el seguimiento de host. Esto evita que el hospedaje de seguimiento de tener un impacto en el rendimiento de otros artefactos de BizTalk que se ejecuta en el mismo host. También permite detener otros hosts sin interferir con el seguimiento. El host de seguimiento debe ejecutarse en al menos dos equipos que ejecuten [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] (redundancia en caso de uno produce un error). Para obtener más información, consulte [configurar un Host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md).|  
|Configuración de conexiones simultáneas de adaptadores WCF basado en HTTP, SOAP y HTTP|[Aplicar opciones de configuración de IIS](../technical-guides/apply-iis-configuration-settings.md)|  
|Implementar una estrategia de actualización y control de versiones de la aplicación de BizTalk.|-Si necesita admitir orquestaciones de larga ejecución, o que necesitan realizar las implementaciones de aplicaciones de BizTalk sin tiempo de inactividad de aplicación de BizTalk, a continuación, se necesitan para implementar y practicar un sólido,-to-end [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] estrategia de control de versiones para el escenarios de versión diferentes.<br />-Si tiene que admitir orquestaciones de larga ejecución, las implementaciones en paralelo o las actualizaciones de sin tiempo de inactividad, debe implementar una estrategia de empaquetado que incluye la factorización y control de versiones de ensamblado.<br /><br /> Para obtener más información, consulte [actualizar y estrategias de control de versiones para las aplicaciones](../technical-guides/upgrading-and-versioning-strategies-for-applications.md).|  
|Implementaciones de la aplicación de BizTalk Server del script.|Las implementaciones de aplicaciones de BizTalk deben convertirse en script siempre que sea posible. Debe documentar con los pasos detallados todo lo que no es un script. Para obtener más información, vea:<br /><br /> -   [Uso de Scripts para implementar aplicaciones](../technical-guides/using-scripts-to-deploy-applications.md)<br />-   [Administración de aplicaciones](../technical-guides/managing-applications.md)|  
|Predefinir procesos para volver a enviar mensajes y reiniciar los flujos de trabajo.|Establecer y documentar un procedimiento para comprobar si las instancias de servicio suspendidas y tome las medidas oportunas. En la mayoría [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entornos, esto debe realizarse como parte del mantenimiento diario de su [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno. Para obtener más información acerca de cómo realizar las comprobaciones de mantenimiento diario, consulte [lista de comprobación: realizar comprobaciones de mantenimiento diario](../technical-guides/checklist-performing-daily-maintenance-checks.md).|  
|Definir las rutas de escalado de problemas que se pueden encontrar en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno.|-Determine roles y responsabilidades<br />-Definir rutas de acceso y el proceso de escalamiento<br />-Definir procesos de "cortocircuito" y las rutas de acceso cuando sea necesario para escenarios de "situación crítica"<br />-Definir una ruta de acceso de la extensión de proveedor emite, incluido Microsoft, otro software de los proveedores, los proveedores de hardware (por ejemplo, servidores, SAN, conmutadores)|  
|Cumplir ciertas consideraciones al utilizar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un sistema operativo de Windows de 64 bits|[Consideraciones al usar BizTalk Server en un sistema operativo Windows de 64 bits](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)|  
|Cumplir con las prácticas recomendadas para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuración.|[Prácticas recomendadas para la configuración de BizTalk Server](../technical-guides/best-practices-for-biztalk-server-settings.md)|  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Configuración de Hosts e instancias de Host](../technical-guides/configuring-hosts-and-host-instances.md)  
  
-   [Configurar un Host de seguimiento dedicado](../technical-guides/configuring-a-dedicated-tracking-host.md)  
  
-   [Aplicar opciones de configuración de IIS](../technical-guides/apply-iis-configuration-settings.md)  
  
-   [Actualizar y las estrategias de control de versiones de aplicaciones](../technical-guides/upgrading-and-versioning-strategies-for-applications.md)  
  
-   [Uso de Scripts para implementar aplicaciones](../technical-guides/using-scripts-to-deploy-applications.md)  
  
-   [Consideraciones al usar BizTalk Server en un sistema operativo Windows de 64 bits](../technical-guides/considerations-while-using-biztalk-server-on-a-64-bit-windows-operating-system.md)  
  
-   [Prácticas recomendadas para la configuración de BizTalk Server](../technical-guides/best-practices-for-biztalk-server-settings.md)