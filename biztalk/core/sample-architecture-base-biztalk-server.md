---
title: 'Arquitectura de ejemplo: Servidor BizTalk Server Base | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- IPSec
- BizTalk Server, examples
- security, examples
- security, architecture
- IPSec, about IPSec
- BizTalk Server, architecture
- architecture, security
ms.assetid: 7ccc1ef3-670f-423f-b6ca-3d56b9bbeabf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea815c0165f58c28cea8ce7cae35fd6ed7437323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271196"
---
# <a name="sample-architecture-base-biztalk-server"></a>Arquitectura de ejemplo: servidor BizTalk Server base
En este tema, se analiza la arquitectura de ejemplo básica. y se describen los componentes de una implementación de BizTalk Server que son independientes de los adaptadores. Se recomienda que todas las implementaciones de BizTalk Server cuenten, como mínimo, con estos componentes.  
  
 La siguiente ilustración muestra los componentes de la arquitectura de ejemplo básica de BizTalk Server. Estos componentes aparecen en todas las arquitecturas de BizTalk Server específicas de adaptadores que se analizarán en otras secciones.  
  
 **Componentes de la arquitectura de Base de la figura 1**  
  
 ![Componentes de la arquitectura de base](../core/media/tdi-sec-refarch.gif "TDI_Sec_RefArch_")  
  
 Esta arquitectura de ejemplo contiene los elementos que se analizan en las secciones siguientes.  
  
## <a name="perimeter-networkinternet"></a>Red perimetral: Internet  
  
-   La red perimetral (también denominada DMZ, zona desmilitarizada y subred protegida) contiene servidores que proporcionan servicios relacionados con Internet. En este dominio no hay servidores de BizTalk, ubicaciones de recepción de BizTalk ni servidores de inicio de sesión único empresarial.  
  
## <a name="perimeter-networkintranet"></a>Red perimetral: intranet  
 La red perimetral contiene servidores que proporcionan servicios relacionados con la intranet. Proporciona un nivel de seguridad adicional entre la intranet (por ejemplo, una red corporativa) y los servidores que ejecutan la aplicación. Como la red perimetral de Internet, la red perimetral de la intranet no contiene servidores de BizTalk Server, ubicaciones de recepción de BizTalk ni servidores de inicio de sesión único (SSO).  
  
## <a name="e-business-domain"></a>Dominio de negocio electrónico  
 Este dominio contiene toda la infraestructura y aplicaciones que utiliza la implementación de BizTalk Server. Los servidores de este domino son:  
  
-   **Servidor BizTalk Server.** Este servidor tiene una instalación del tiempo de ejecución de BizTalk Server e instancias de varios hosts de BizTalk. El número de servidores de BizTalk del entorno depende del tipo de hosts que ejecuten y de las necesidades de rendimiento. A medida que aumenten sus necesidades de rendimiento, puede agregar más servidores de BizTalk Server al entorno para alojar instancias de los hosts de procesamiento.  
  
-   **Servidor secreto principal.** Este es el servidor secreto principal de inicio de sesión único (SSO). Contiene el secreto principal (clave de cifrado) que utiliza el sistema SSO para cifrar los datos en la base de datos SSO.  
  
-   **Servidor SQL Server.** Este servidor contiene las bases de datos de BizTalk Server.  
  
    > [!IMPORTANT]
    >  Para la protección de conmutación por error, es recomendable agrupar las bases de datos de BizTalk en clústeres. Para obtener más información acerca de los clústeres de conmutación por error de Microsoft SQL Server, vea el sitio Web de Microsoft MSDN en [http://go.microsoft.com/fwlink/?LinkID=190216](http://go.microsoft.com/fwlink/?LinkID=190216).  
  
    > [!NOTE]
    >  Según sus necesidades de rendimiento, puede que tenga que separar las bases de datos de BizTalk en varios equipos que ejecuten SQL Server.  
  
-   **Controlador de dominio.** Este servidor aloja el dominio de negocio electrónico de Active Directory. Contiene información acerca de todos los grupos y cuentas individuales que necesitan tener acceso a BizTalk Server.  
  
-   **Herramientas de administración.** Uno de los servidores de este dominio contiene las herramientas administrativas siguientes: la consola de administración de BizTalk y la utilidad de administración de inicio de sesión único (SSO) empresarial.  
  
## <a name="firewalls-and-domains"></a>Servidores de seguridad y dominios  
 En la Figura 1, el servidor Forefront Threat Management Gateway (TMG) 2010 actúa como firewall de software para proteger y contener cada uno de estos dominios. Asimismo, el dominio de negocio electrónico tiene su propio controlador de dominio y no confía en ningún otro dominio. Para obtener más información acerca de cómo configurar un firewall para dominios y confianzas, consulte el sitio Web de soporte técnico y Microsoft Help en [http://go.microsoft.com/fwlink/?LinkId=25230](http://go.microsoft.com/fwlink/?LinkId=25230).  
  
 En esta arquitectura de ejemplo hay dos servidores de seguridad:  
  
-   **Firewall 1.** Este servidor de seguridad tiene tres interfaces de red: enruta el tráfico procedente de Internet, la intranet y las redes perimetrales.  
  
-   **Servidor de seguridad 2.** Este servidor es de base dual: enruta el tráfico procedente de las redes perimetrales (Internet e intranet) y el dominio de negocio electrónico.  
  
 Los equipos de las redes perimetrales no son miembros de ningún dominio y no se comunican entre sí.  
  
## <a name="ipsec"></a>IPsec  
 Se recomienda utilizar seguridad de Protocolo de Internet (IPSec) para proteger la comunicación entre todos los servidores del dominio de negocio electrónico. Las reglas de IPsec son los siguientes:  
  
-   Permitir el tráfico autenticado entre BizTalk Server y el controlador de dominio.  
  
-   Permitir el tráfico autenticado entre BizTalk Server y el servidor de herramientas de administración.  
  
-   Permitir el tráfico autenticado entre BizTalk Server y el servidor secreto principal.  
  
-   Permitir el tráfico autenticado entre BizTalk Server y SQL Server.  
  
-   Permitir el tráfico autenticado entre el servidor secreto principal y el controlador de dominio.  
  
-   Permitir el tráfico autenticado entre el servidor secreto principal y BizTalk Server (hosts de seguimiento, en proceso, de procesamiento y aislados).  
  
-   Permitir el tráfico autenticado entre el servidor secreto principal y el servidor SQL Server (bases de datos SSO).  
  
-   Permitir el tráfico autenticado entre el controlador de dominio y todos los servidores del dominio.  
  
-   Permitir el tráfico autenticado entre el servidor de herramientas administrativas y todos los servidores del dominio.  
  
 Si en el dominio hay otras aplicaciones que no necesitan obtener acceso al servidor BizTalk Server, SQL Server, el servidor secreto principal ni al servidor de herramientas administrativas, bloquee el tráfico entre esas aplicaciones y los servidores correspondientes.  
  
## <a name="see-also"></a>Vea también  
 [Planear la seguridad](../core/planning-for-security.md)   
 [Arquitecturas de ejemplo para pequeñas y medianas empresas](../core/sample-architectures-for-small-medium-sized-companies.md)   
 [Escenarios de ejemplo para el análisis de modelo de amenaza](../core/sample-scenarios-for-threat-model-analysis.md)