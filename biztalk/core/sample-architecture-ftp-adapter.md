---
title: 'Arquitectura de ejemplo: Adaptador de FTP de | Documentos de Microsoft'
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
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bed15e06027bec5e73c19cf73548674bc51ce68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269852"
---
# <a name="sample-architecture-ftp-adapter"></a>Arquitectura de ejemplo: Adaptador de FTP de
En este tema se describe la arquitectura de ejemplo cuando se usa el adaptador de FTP para enviar y recibir mensajes.  
  
 La siguiente ilustración muestra los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar el adaptador de FTP.  
  
 **Figura 1: arquitectura de ejemplo que muestra el adaptador FTP**  
  
 ![Ejemplo de arquitectura de adaptador de FTP](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")  
  
 Esta arquitectura de ejemplo contiene los componentes como se describe en las secciones siguientes.  
  
## <a name="perimeter-networkinternet"></a>Red perimetral-Internet  
 Si utiliza el adaptador de FTP, habrá un servidor FTP en la red perimetral de Internet.  
  
> [!NOTE]
>  El servidor FTP también puede estar fuera de su entorno, en la red de un socio u hospedado por un proveedor de software independiente (ISV).  
  
## <a name="perimeter-networkintranet"></a>Red perimetral: intranet  
 Normalmente las compañías utilizan el protocolo FTP para las comunicaciones basadas en Internet y, por tanto, no necesita que ningún servidor de la red perimetral de la intranet admita este escenario.  
  
## <a name="e-business-domain"></a>Dominio de negocio electrónico  
 Los servidores de este domino son:  
  
-   **BizTalk Server (procesamiento, adaptador de FTP y hosts de seguimiento).** Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales. Aquí se encuentran los puertos de BizTalk Server, las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar, procesar y enviar mensajes. Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio. Asimismo, este host contiene instancias del host que ejecuta los adaptadores de recepción y envío FTP.  
  
    > [!NOTE]
    >  A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento. Para obtener más información acerca de cómo configurar BizTalk Server para alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).  
  
-   **Servidor secreto principal.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Servidor SQL Server.** Igual que el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Controlador de dominio.** Igual que el mismo que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Herramientas de administración.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)