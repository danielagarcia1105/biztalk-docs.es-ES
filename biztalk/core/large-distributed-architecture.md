---
title: Arquitectura distribuida de gran tamaño | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- data, domains
- corporate domains
- networks
- domain types, service
- domain types, processing
- screened subnet
- service domains
- domain types, corporate
- domain types, data
- perimeter networks
- processing domains
- demilitarized zone
- architecture, large distributions
ms.assetid: 3cfc07c4-0b1d-489b-9a29-55187fde0539
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81479c445ac901b35b821a136bc2add26f65926f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981021"
---
# <a name="large-distributed-architecture"></a>Arquitectura distribuida grande
Para obtener información completa sobre la arquitectura del sistema para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación, consulte [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).  
  
 La arquitectura que se presenta en esta sección ha sido concebida para un entorno de producción. No incluye un entorno de desarrollo o de pruebas ni recomendaciones para una red de administración del entorno. Para obtener más información sobre la configuración de un desarrollo en un entorno de prueba y de una prueba en un entorno de producción de almacenamiento provisional, consulte [implementar aplicaciones de BizTalk](../core/deploying-biztalk-applications.md).  
  
 En la ilustración siguiente se muestra una arquitectura de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] altamente distribuida que tiene en cuenta la defensa en profundidad.  
  
 ![Arquitectura distribuida de gran tamaño](../core/media/06c5ae00-17aa-42f5-88d1-487bf7720183.gif "06c5ae00-17aa-42f5-88d1-487bf7720183")  
Arquitectura distribuida segura de BizTalk Server  
  
 Esta arquitectura contiene los cinco dominios siguientes:  
  
 **Red perimetral.** La red perimetral (también denominada DMZ, zona desmilitarizada y subred protegida) contiene servidores que proporcionan servicios relacionados con Internet a una empresa. Este dominio puede contener servidores en los que se encuentran las ubicaciones físicas en las que los transportes que se comunican con Internet envían mensajes al servidor [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y los reciben de éste. En este dominio no hay servidores de BizTalk, ubicaciones de recepción de BizTalk ni servidores de inicio de sesión único empresarial. Si se usa el adaptador de HTTP o SOAP, se pueden emplear reglas de proxy inversas (la implementación del servidor Forefront Threat Management Gateway (TMG) 2010 se denomina Publicación en Web) para retransmitir el mensaje del firewall conectado a Internet (FW4) al firewall que protege el dominio de interfaces de servicio (FW3). Para obtener más información sobre las reglas de publicación en Web, consulte el sitio Web de Microsoft en [ http://go.microsoft.com/fwlink/?LinkID=205340 ](http://go.microsoft.com/fwlink/?LinkID=205340) (<http://go.microsoft.com/fwlink/?LinkID=205340>).  
  
 En la ilustración anterior, los servidores de la red perimetral representan servidores que se encuentran en un dominio externo al entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Por consiguiente, es posible que algunos de estos servidores se encuentren en ubicaciones remotas. Por ejemplo, el servidor de protocolo de transferencia de archivos (FTP) podría ser en una ubicación remota; el servidor de Protocolo Simple de transferencia de correo (SMTP) podría ser el servidor de correo electrónico corporativo, un proveedor de servicios Internet (ISP) server o un servidor SMTP remoto.  
  
 **Dominio de Interfaces de servicio.** Este es el domino en el que se inicia el procesamiento del mensaje. Este dominio contiene los servidores que tienen los controladores de envío y recepción de BizTalk. Aquí se encuentran los puertos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], las ubicaciones de recepción, las canalizaciones, las asignaciones, los esquemas y los ensamblados para recibir, enrutar y enviar mensajes. El número de servidores de BizTalk de este dominio depende del número de hosts e instancias de host que requieren las necesidades de rendimiento de la organización.  
  
 **Dominio de servicios.** Este dominio contiene los servicios en los que confían los servidores del dominio de procesamiento y que necesitan procesar los mensajes correctamente pero requieren una capa de defensa adicional para protegerse de los ataques procedentes de la red perimetral, como por ejemplo los servidores de procesamiento que tienen las orquestaciones de BizTalk, las canalizaciones, servicios de inicio de sesión único (SSO) empresarial, el motor de reglas de negocios y otros procesos empresariales.  
  
 Este dominio contiene además los servicios a los que debe tener acceso el domino corporativo pero que siguen necesitando protección contra amenazas externas. Uno de los servidores en este dominio contiene las herramientas administrativas: consola de administración de BizTalk y la utilidad de administración de inicio de sesión único (SSO) empresarial. Asimismo, este dominio contiene el servidor secreto principal de SSO, en el que se encuentra la clave secreta principal (clave de cifrado) que utiliza el sistema SSO para cifrar y descifrar los datos de la base de datos de SSO. Uno de los servidores de este dominio tiene una instancia de un host que admite el seguimiento de la información empresarial y de supervisión de estado.  
  
> [!NOTE]
>  En los sistemas de inicio de sesión único (SSO) empresarial, puede que algunos de los servidores de procesamiento solo contengan el servicio de SSO sin componentes de BizTalk Server. Para obtener más información, consulte [alta disponibilidad para Enterprise Single Sign-On](../core/high-availability-for-enterprise-single-sign-on.md).  
  
 **Dominio de datos.** El dominio de datos es el que está más alejado de Internet, ya que contiene las bases de datos de SQL Server en las que se almacenan los datos empresariales y de los procesos más importantes, y no confía en ningún otro dominio. Aunque cada una de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede encontrarse en un servidor distinto que ejecute SQL Server, se recomienda combinar las bases de datos en función del tipo de procesamiento que realizan principalmente (de lectura, de escritura o ambos).  
  
- Un servidor SQL Server para cada base de datos de cuadro de mensajes. Puede agregar más bases de datos de cuadro de mensajes para equilibrar la carga. Estas bases de datos son de lectura o escritura intensiva.  
  
- Un servidor SQL Server para la base de datos de SSO. BizTalk Server realiza principalmente operaciones de lectura en esta base de datos. Esta base de datos contiene datos confidenciales y necesita los permisos de acceso más restrictivos.  
  
- Un servidor de SQL Server para la administración de BizTalk y las bases de datos de motor de reglas de negocios. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] principalmente operaciones de lectura en estas bases de datos. Este servidor contiene también la base de datos de seguimiento, que es de escritura intensiva.  
  
- Un servidor SQL Server para la base de datos de seguimiento de servidor de análisis.  
  
- Un servidor SQL Server para la base de datos de Microsoft Operations Manager (MOM).  
  
- Un servidor SQL Server para el sistema de destino de trasvase de registros.  
  
> [!IMPORTANT]
>  Para la protección de conmutación por error, se recomienda que cada base de datos de BizTalk del clúster. Para obtener más información acerca de la agrupación en clústeres de conmutación por error de SQL Server, vea el sitio Web de Microsoft MSDN en [ http://go.microsoft.com/fwlink/?LinkId=131016 ](http://go.microsoft.com/fwlink/?LinkId=131016).  
  
> [!NOTE]
>  Para obtener más información sobre el sistema de destino del trasvase de registros, vea [copia de seguridad y restaurar las bases de datos de BizTalk Server](../core/backing-up-and-restoring-the-biztalk-server-databases.md).  
  
 En la ilustración anterior, el servidor Forefront Threat Management Gateway (TMG) 2010 actúa como firewall de software para proteger y contener cada uno de estos dominios. Además, cada dominio tiene su propio controlador de dominio; la confianza se establece desde el dominio que contiene los servidores esenciales (el dominio de datos) hacia los servidores que se comunican con el exterior (dominio corporativo y red perimetral), y los servidores sólo tienen acceso a los servicios de los demás dominios con los que necesitan conectarse. Hay un firewall que restringe el tráfico dirigido al dominio de datos procedente de los dominios de servicios y de interfaces de servicio (FW1). De un modo parecido, hay un firewall (FW2) que restringe el tráfico dirigido al dominio de servicios procedente de los dominios de interfaces de servicio y operaciones.  
  
 **Dominio corporativo.** Este es el dominio de intranet y contiene todos los equipos de escritorio de la compañía o departamento, y todos los servidores que ofrecen servicios a los trabajadores de información dentro de la organización. Dentro de este dominio, hay dos contenedores lógicos distintos:  
  
- **Servicios de la intranet.** En este contenedor se encuentran los servidores que reciben y envían mensajes de socios internos para los adaptadores SQL y de archivo. Aunque esto es una intranet, se diferencia de una red corporativa en que en ésta la mayoría de los usuarios tienen cuentas y servicios. De un modo parecido a la red perimetral que aparece en la ilustración, algunos de los servidores de este contenedor pueden encontrarse en una ubicación diferente. Por ejemplo, la ubicación (carpeta) de envío y recepción del adaptador de archivo puede ubicarse en cualquier capa exterior al dominio de interfaces de servicio, mientras que el servidor que ejecuta SQL Server para el adaptador SQL puede ubicarse en el domino de interfaces de servicio.  
  
- **Operaciones.** Este contenedor tiene clientes de servicios de Terminal Server que los profesionales de TI utilizan para supervisar, mantener y administrar de modo remoto el rendimiento y el estado de todos los servidores del entorno. Con los servicios de Terminal Server, los profesionales de TI pueden conectarse al servidor de administración del dominio de servicios y realizar desde éste las tareas administrativas de todos los servidores del entorno.  
  
  Aunque pueda haber equipos de desarrollo dentro del dominio corporativo, la configuración de dichos equipos excede el contenido de este documento.  
  
  Para obtener más información acerca de la arquitectura de BizTalk Server, incluidos los servicios de trabajadores de información, consulte [grandes arquitectura distribuida con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md).  
  
  La confianza entre los dominios funciona del siguiente modo:  
  
- El dominio de datos no confía en ningún otro dominio.  
  
- El dominio de interfaces de servicio confía en el dominio de datos.  
  
- El dominio de servicios confía en el dominio de datos.  
  
- El dominio corporativo confía en los dominios de servicios.  
  
  Para obtener más información acerca de cómo configurar un firewall para dominios y confianzas, consulte el sitio Web de soporte técnico y de Microsoft Help en [ http://go.microsoft.com/fwlink/?LinkId=25230 ](http://go.microsoft.com/fwlink/?LinkId=25230).  
  
  Aunque la ilustración anterior se centra en la seguridad, también puede ampliar la arquitectura con Equilibrio de carga de red (NLB) y Servicios de Cluster Server para disponer de mayor disponibilidad y rendimiento.  
  
  Para obtener más información sobre la alta disponibilidad, consulte [planificación de alta disponibilidad](../core/planning-for-high-availability3.md).  
  
  Para obtener más información sobre el rendimiento, consulte [planear el rendimiento sostenido](../core/planning-for-sustained-performance.md).  
  
  La siguiente tabla resume el tipo de servidores que se pueden configurar con Equilibrio de carga de red (NLB) según el contrato de nivel de servicios (SLA) que necesita obtener:  
  
|Nombre|Tipo|Dominio|  
|----------|----------|------------|  
|HTTP (Rec)|Internet Information Services|Red perimetral|  
|Controlador de recepción (aislado)|Internet Information Services|Dominio de interfaces de servicio|  
|Portal de BAM|Internet Information Services|Dominio de interfaces de servicio|  
  
 La siguiente tabla resume el tipo de servidores que se pueden agrupar según el contrato de nivel de servicios (SLA) que necesita obtener:  
  
|Nombre|Tipo|Dominio|  
|----------|----------|------------|  
|Exchange (envío)|Exchange 2000 Server SP2|Red perimetral|  
|Controlador de recepción (host en curso) para adaptadores de FTP y POP3|BizTalk Server|Dominio de interfaces de servicio<br /><br /> Dominio corporativo|  
|Servidor secreto principal|BizTalk Server|Dominio de servicios|  
|Todos los servidores SQL Server|SQL Server|Dominio de datos|  
  
 Para obtener más información acerca de la arquitectura de BizTalk Server, incluidos los servicios de trabajadores de información, consulte [grandes arquitectura distribuida con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Arquitecturas de ejemplo de BizTalk Server](../core/sample-biztalk-server-architectures.md)   
 [Arquitectura reducida](../core/scaled-down-architecture.md)