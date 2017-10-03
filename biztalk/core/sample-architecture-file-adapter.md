---
title: 'Arquitectura de ejemplo: Adaptador de archivo de | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11884786f743ece21a8009ea339a251b107420c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-file-adapter"></a>Arquitectura de ejemplo: Adaptador de archivo de
En este tema se describe la arquitectura de ejemplo cuando se usa el adaptador de archivo para enviar y recibir mensajes.  
  
## <a name="file-adapter-components"></a>Componentes del adaptador de archivo  
 En la siguiente ilustración se muestran los componentes de la arquitectura de ejemplo de BizTalk Server al utilizar el adaptador de archivo.  
  
> [!NOTE]
>  Esta arquitectura de ejemplo se aplica también cuando se utiliza el adaptador de EDI.  
  
 **Figura 1: arquitectura de ejemplo que muestra el adaptador de archivo**  
  
 ![Ejemplo de arquitectura de adaptador de archivo](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")  
  
 Esta arquitectura de ejemplo contiene los componentes descritos en las secciones siguientes.  
  
## <a name="perimeter-network-internet"></a>Red perimetral-Internet  
 Normalmente las compañías utilizan el protocolo de archivo para las comunicaciones basadas en intranet y, por tanto, no es necesario que ningún servidor de la red perimetral de Internet admita este escenario.  
  
## <a name="perimeter-network-intranet"></a>Red perimetral-intranet  
 Cuando se utiliza el adaptador de archivo, hay un servidor de archivos en la red perimetral de la intranet. Este es el servidor en el que los socios descargan mensajes, y en el que el adaptador de recepción de archivos de BizTalk los recoge.  
  
## <a name="e-business-domain"></a>Dominio de negocio electrónico  
 Los servidores de este domino son:  
  
-   **BizTalk Server (procesamiento, adaptador de archivo y hosts de seguimiento).** Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server, así como instancias de los hosts que contienen las orquestaciones de BizTalk, las canalizaciones, el motor de reglas de negocios y otros procesos empresariales. Aquí se encuentran los puertos de BizTalk Server, las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar, procesar y enviar mensajes. Este servidor también tiene una instancia de host de un host que admite el seguimiento de supervisión de estado y datos de supervisión de negocio. Asimismo, este host contiene instancias del host que ejecuta los adaptadores de recepción y envío de archivos.  
  
    > [!NOTE]
    >  A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento. Para obtener más información acerca de cómo configurar BizTalk Server para alta disponibilidad, vea [planeamiento para alta disponibilidad](../core/planning-for-high-availability3.md).  
  
-   **Servidor secreto principal.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Servidor SQL Server.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Controlador de dominio.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
-   **Herramientas de administración.** Igual que en el [arquitectura de ejemplo: servidor BizTalk Server Base](../core/sample-architecture-base-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)