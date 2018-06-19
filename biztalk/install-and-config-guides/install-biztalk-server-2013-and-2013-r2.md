---
title: Instalar BizTalk Server 2013 y 2013 R2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b4665ea-6f2c-477f-98ec-1cebef05ad4a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e04bbce8870e4f0e8c0edb278511f2a6791d62d8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25976370"
---
# <a name="install-biztalk-server-2013-and-2013-r2"></a>Instalar BizTalk Server 2013 y 2013 R2
Aquí se enumeran los pasos necesarios para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="before-you-get-started"></a>Antes de comenzar

-   **Nombres de cuenta**: use los nombres de cuenta predeterminados siempre que sea posible. El programa de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] especifica de forma automática las cuentas predeterminadas. Si hay varios grupos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el dominio, cambie los nombres de cuenta para evitar conflictos. Si cambia los nombres, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sólo admite \< *nombre de dominio NetBIOS*\>\\<*usuario* \> de servicio cuentas y grupos de Windows.  
  
-   **Nombres de cuenta con Servicio web de administración de BAM**: [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no admite el uso de cuentas integradas ni cuentas sin contraseña para el usuario del Servicio web de administración de BAM. El servicio web accede a la base de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y estas cuentas pueden suponer una amenaza para la seguridad.  
  
    > [!NOTE]
    >  La configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con estos tipos de cuenta puede funcionar, pero el Servicio web de administración de BAM da error. Se pueden usar cuentas integradas o cuentas sin contraseña para el grupo de aplicaciones de BAM.  
  
-   **Visor de ensamblados de BizTalk**: no se admite en una plataforma de 64 bits.  
  
-   **Instalar y desinstalar**: la desinstalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere la eliminación manual de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si instala [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como desarrollador o evaluador, use una máquina virtual. Si tiene que reinstalarlo, puede revertir fácilmente la máquina virtual sin tener que desinstalar ni eliminar las bases de datos.  
  
-   **Equipos de 32 y 64 bits**: hay algunas diferencias a la hora de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo de 32 bits o de 64 bits. El proceso de instalación y configuración cubre equipos de 32 y 64 bits. Las posibles diferencias se indican.  
  
-   **Grupos de trabajo**: se admiten la instalación y la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el entorno de grupo de trabajo de un único equipo. Las características y componentes de SQL Server y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se instalan y configuran en el mismo equipo.  
  
-   **Terminal Server**: no se puede instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con Terminal Server en modo de aplicación. Consulte [KB 832027](http://support.microsoft.com/kb/832027).  
  
-   **Portal de BAM**: si el portal de BAM está configurado en un sitio web que usan aplicaciones que ejecutan .NET Framework 2.0, debe crear un nuevo sitio web para el portal BAM:  
  
     [Crear un sitio web de IIS 7](http://technet.microsoft.com/library/cc772350\(WS.10\).aspx)  
  
     [Crear un sitio web de IIS 8](http://technet.microsoft.com/library/hh831515.aspx)  
  
     Después de crear el nuevo sitio web:  
  
    1.  Abra **Configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**.  
  
    2.  Configure el portal de BAM y seleccione el nuevo sitio web de la lista **Sitio web del portal de BAM**.  
  
-   **Añadidos de la comunidad**: Lea:  
  
     [Proactividad en BizTalk Server](http://msdn.microsoft.com/library/dn393929\(v=bts.10\).aspx)  
  
     [BizTalk Server 2013 R2: Instalación y configuración: consideraciones importantes antes de configurar el servidor (parte 1)](http://sandroaspbiztalkblog.wordpress.com/2015/01/04/biztalk-server-2013-r2-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)  
  
##  <a name="BKMK_Install"></a> Instalar BizTalk Server  
  
1.  Cierre todos los programas abiertos. Ejecute el instalador de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] como administrador.  
  
2.  En **Inicio**, seleccione **Install Microsoft BizTalk Server** (Instalar Microsoft BizTalk Server).  
  
3.  En **Información sobre el usuario**, escriba el nombre de usuario, la organización y la clave de producto y, después, seleccione **Siguiente**.  
  
4.  En **Contrato de licencia**, acepte el contrato de licencia y seleccione **Siguiente**.  
  
5.  En **Programa para la mejora de la experiencia del usuario**, elija su preferencia de participación y seleccione **Siguiente**.  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] participa en el Programa para la mejora de la experiencia del usuario. Con esto, proporciona comentarios útiles para Microsoft en relación con la funcionalidad de creación de informes sobre el uso de características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Los datos que se recopilan son anónimos y no se pueden usar para identificarle. Microsoft recopila estadísticas de uso de las funciones como parte de este programa. Al participar en el programa, ayuda a mejorar la confiabilidad y el rendimiento de las distintas características de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información sobre este programa y su directiva de privacidad, consulte [Programa para la mejora de la experiencia del usuario de Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=188553).  
  
6.  En **Instalación de componentes**, revise los componentes disponibles y seleccione los que quiera instalar:  

    |Característica|Descripción|  
    |-------------|-----------------|  
    |**Documentación**|Documentación principal, tutoriales, referencia de la interfaz de usuario (Ayuda de F1), referencia para programadores e instrucciones de uso para las utilidades y los ejemplos de SDK.|  
    |**Tiempo de ejecución del servidor**|Los servicios de tiempo de ejecución esenciales de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
    |**Tiempo de ejecución de EDI y AS2 de BizTalk**|Los servicios en tiempo de ejecución proporcionan compatibilidad nativa con la funcionalidad de mensajería de transporte de datos AS2 (Applicability Statement 2) y el intercambio de datos EDI (intercambio electrónico de datos). **Nota**: Puede seleccionar esta opción solo si ha seleccionado la característica **Tiempo de ejecución del servidor**.|  
    |**Tiempo de ejecución del adaptador de Windows Communication Foundation (WCF)**|Adaptadores que permiten a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] comunicarse con aplicaciones basadas en WCF. **Nota**: Puede seleccionar esta opción solo si ha seleccionado la característica **Tiempo de ejecución del servidor**.|  
    |**Componentes de portal**|Los componentes de portal son un conjunto de características usadas por los analistas empresariales para comunicarse, colaborar y tomar decisiones usando los datos empresariales.|  
    |**Supervisión de la actividad económica**|También conocido como BAM, es un conjunto de características que proporciona a los usuarios empresariales una vista en tiempo real de sus procesos empresariales heterogéneos, lo que les permite tomar decisiones empresariales importantes. **Nota:** Puede seleccionar esta opción solo si ha seleccionado la característica **Componentes de portal**.|  
    |**Herramientas administrativas y supervisión**|Componentes necesarios para administrar y supervisar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tanto en el PC local como en el servidor remoto.|  
    |**Herramientas de administración de Windows Communication Foundation (WCF)**|Al seleccionar esta característica, se instalan los servicios administrativos de componentes WCF. **Nota:** Puede seleccionar esta opción solo si ha seleccionado la característica **Herramientas administrativas y supervisión**.|  
    |**SDK y herramientas de programadores**|Muestras y utilidades que permiten la rápida creación de soluciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Incluye documentación complementaria y ejemplos de SDK, diseñadores de asignaciones y esquemas, además de plantillas de proyectos de Visual Studio. **Importante:** Debe instalar este componente si va a realizar cualquier trabajo de desarrollo. Las extensiones de Visual Studio que usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no funcionarán si el componente **SDK y las herramientas de programadores** no están instalados.|  
    |***Software adicional***||  
    |**Módulo de administración de inicio de sesión único empresarial (SSO)**|La interfaz de administración de aplicaciones afiliadas de SSO y sus asignaciones.|  
    |**Servidor secreto maestro de inicio de sesión único empresarial**|El servidor SSO que almacena el secreto maestro. Todos los demás servidores SSO en el sistema obtienen el secreto maestro de este servidor. El servidor secreto maestro es obligatorio en un entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
    |**Componentes de reglas de negocios**|Se usan para componer directivas que usará el motor de reglas de negocios.|  
    |**MQSeries Agent**|Permite la comunicación entre el adaptador de BizTalk para MQSeries y MQSeries Server para Windows.|  
    |**Servicio web del adaptador de Windows SharePoint Services**|**Obsoleto**. Mediante un servicio web de IIS instalado en el equipo [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)], el adaptador de [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] procesa los documentos entrantes y salientes a través de Microsoft SharePoint.<br /><br /> **Recomendación**: **No** lo instale. De forma predeterminada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el modelo de objetos del cliente de SharePoint (CSOM) redistribuible instalado automáticamente en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], tal y como se describe en [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).|  
    |**Proveedor de alertas de BAM**|Configura Alertas BAM.<br /><br /> Cuando use alertas de BAM con [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] o [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] SP1, debe configurar la característica Correo electrónico de base de datos. No se puede usar SQL Server Notification Services.|  
    |**Cliente de BAM**|Software de cliente que permite a los usuarios de la empresa trabajar con BAM.|  
    |**Eventos de BAM**|Interceptores de Windows Workflow Foundation y Windows Communication Foundation. También incluye la API de eventos de BAM, que envía eventos a la base de datos de BAM desde aplicaciones personalizadas.|  
    |**Componente de generación de proyecto**|Herramienta que permite generar soluciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sin usar Visual Studio.|  

7. Acepte la ubicación de instalación predeterminada o seleccione **Examinar** para especificar otra ubicación donde instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Seleccione **Siguiente**.  
  
8.  Si falta un componente que es un requisito previo, como ADOMD.NET, el programa de instalación puede instalar los requisitos previos redistribuibles. Puede elegir entre lo siguiente:  
  
    -   Seleccionar **Instalar automáticamente los requisitos previos redistribuibles desde Internet**  
    
         O BIEN  
  
    -   Seleccionar **Instalar automáticamente los requisitos previos redistribuibles desde un archivo .cab** si ha descargado el archivo CAB. Si selecciona esta opción, busque la ubicación del archivo CAB.  
  
9.  En **Resumen**, compruebe que los componentes son correctos. Para habilitar el inicio de sesión automático después de reiniciar el sistema, seleccione **Establecer** y escriba la información de inicio de sesión. El inicio de sesión automático solo se habilita para reinicios durante la instalación y se deshabilita una vez finalizada la instalación.  
  
10. Seleccione **Instalar** para iniciar el proceso de instalación.  
  
11. En **Microsoft Update Setup** (Configuración de Microsoft Update), elija su preferencia y seleccione **Siguiente**.  
  
12. En la pantalla **Se ha completado la instalación**, desactive la casilla **Iniciar configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]** y seleccione **Finalizar**.  
  
## <a name="additional"></a>Notas  
  
-   Cuando instaló SQL Server, el programa de instalación de SQL Server concedió derechos de administrador del sistema a la cuenta que había iniciado sesión. Puesto que estos derechos también son necesarios para instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe realizar una de las acciones siguientes:  
  
    -   Use la misma cuenta que usó al instalar SQL Server.  
  
    -   Conceda derechos de administrador del sistema a la cuenta que ha iniciado sesión.  
  
-   Después de descargar el archivo EXE autoextraíble de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se abre la guía de instalación. El archivo Setup.exe para [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se encuentra en la misma ubicación que la guía de instalación.  
  
-   En lugar de instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un equipo físico, puede configurar una máquina virtual de [!INCLUDE[winazure](../includes/winazure-md.md)] con una imagen de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Consulte [Configurar BizTalk Server en una máquina virtual de Azure](http://msdn.microsoft.com/library/azure/jj248689.aspx).  
  
-   Para obtener instrucciones sobre cómo instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde el símbolo del sistema, consulte [Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md).  
  
 
## <a name="see-also"></a>Ver también  
   
 [Apéndice A: Instalación silenciosa](../install-and-config-guides/appendix-a-silent-installation.md)   
 [Apéndice B: Instalar el adaptador de Microsoft SharePoint](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)   
 [Apéndice C: Archivos CAB redistribuibles](../install-and-config-guides/appendix-c-redistributable-cab-files.md)   
 [Apéndice D: Crear el servidor SMTP](../install-and-config-guides/appendix-d-create-the-smtp-server.md)