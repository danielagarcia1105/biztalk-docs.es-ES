---
title: 'Arquitectura de ejemplo: Los adaptadores SOAP y HTTP | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- SOAP adapters, security
- Web Publishing
- security, examples
- security, architecture
- SOAP adapters, architecture examples
- examples, architecture
- architecture, security
- HTTP adapters, architecture examples
- reverse proxy rules
- ISA Server implementation
- HTTP adapters, security
ms.assetid: 935197d0-5108-4970-b237-3c6d5b40c5e9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae8be185084a9a838876e3d50b605a63c161b66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269732"
---
# <a name="sample-architecture-http-and-soap-adapters"></a>Arquitectura de ejemplo: Los adaptadores SOAP y HTTP
En esta sección se describe la arquitectura de ejemplo cuando se usan los adaptadores de HTTP y SOAP para enviar y recibir mensajes.  
  
 La siguiente ilustración muestra los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar los adaptadores de HTTP y SOAP.  
  
 **Figura 1: arquitectura de ejemplo que muestra los adaptadores de HTTP y SOAP**  
  
 ![Ejemplo de arquitectura de adaptador de HTTP o SOAP](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")  
  
 Esta arquitectura de ejemplo contiene los componentes que se analizan en las secciones siguientes.  
  
## <a name="perimeter-networkinternet"></a>Red perimetral-Internet  
 Si se usan los adaptadores de HTTP y SOAP, se recomienda emplear reglas de proxy inverso (la implementación de servidor TMG se denomina Publicación en Web) para retransmitir el mensaje del firewall conectado a Internet (Firewall 1) al firewall que protege el dominio de negocio electrónico (Firewall 2) y de éste al servidor BizTalk Server que ejecuta el host aislado. Para obtener más información acerca de las reglas de publicación en Web, vea el sitio Web de Microsoft en [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).  
  
> [!NOTE]
>  Si utiliza un proxy inverso, no necesita servidores Web en la red perimetral.  
  
## <a name="perimeter-networkintranet"></a>Red perimetral: intranet  
 Normalmente las compañías utilizan los protocolos HTTP y SOAP para las comunicaciones basadas en Internet y, por tanto, no es necesario que ningún servidor de la red perimetral de la intranet admita este escenario. Si en la intranet hay una aplicación interna que está integrada en BizTalk Server mediante los protocolos HTTP o SOAP, debe seguir las recomendaciones de la red perimetral de Internet.  
  
## <a name="e-business-domain"></a>Dominio de negocio electrónico  
 Este dominio contiene toda la infraestructura y aplicaciones que utiliza la implementación de BizTalk Server. Los servidores de este domino son:  
  
-   **BizTalk Server (procesamiento y hosts de seguimiento).** Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales. Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio.  
  
    > [!NOTE]
    >  A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.  
  
-   **BizTalk Server (hosts aislados para adaptadores de SOAP y HTTP).** Este servidor contiene una instalación del tiempo de ejecución de BizTalk Server y sólo tiene instancias de los hosts que contienen los adaptadores de HTTP y SOAP. Estos hosts se ejecutan en un servidor independiente, ya que para ejecutar los adaptadores es necesario instalar los Servicios de Internet Information Server (IIS) en el equipo.  
  
    > [!NOTE]
    >  A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de los adaptadores de HTTP y SOAP. Al hacerlo, deberá configurar además el equilibrio de carga de red (NBL). Para obtener más información acerca de cómo configurar BizTalk Server para alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).  
  
-   **Servidor secreto principal.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Servidor SQL Server.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Controlador de dominio.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Herramientas de administración.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)