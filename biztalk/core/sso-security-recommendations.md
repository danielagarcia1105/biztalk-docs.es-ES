---
title: Recomendaciones de seguridad SSO | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- Kerberos protocol, SSO
- deploying, SSO
- user accounts, SSO
- deploying, security
- SQL Server, SSO
- security, SSO
- SSO, Kerberos protocol
- SSO, auditing
- best practices, deploying
- SSO, Windows groups
- SSO, best practices
- SSO, perimeter network
- Windows groups, SSO
- SSO, SQL Server access
- best practices, security
- Master Secret server, clustering
- perimeter networks
- auditing [SSO]
- SSO, security
- SSO, user accounts
- Master Secret server, best practices
ms.assetid: 7ae922b4-fd48-41f4-aaab-419a5e22c753
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a86e669e603eaabf142ce446b8d7204a6cc0091
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279844"
---
# <a name="sso-security-recommendations"></a>Recomendaciones de seguridad SSO
Con el sistema SSO (Inicio de sesión único), los usuarios se pueden conectar a diferentes sistemas con un solo conjunto de credenciales. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]aprovecha el sistema SSO como almacén de información confidencial. Aunque [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] se instala automáticamente al instalar el tiempo de ejecución de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], también puede instalar el inicio de sesión único empresarial como componente autónomo, independiente del entorno [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información acerca de Enterprise Single Sign-On, vea [mediante SSO](../core/using-sso.md). Se recomienda seguir estas instrucciones para proteger e implementar los servicios y recursos de inicio de sesión único (SSO) en su entorno.  
  
## <a name="general-deployment-recommendations-for-sso"></a>Recomendaciones generales para implementar SSO  
  
-   Debe haber un único servidor secreto principal y una única base de datos de SSO en todo el entorno, incluso si tiene varios grupos BizTalk en el entorno. Debe configurar estos dos servidores antes de configurar otros servidores BizTalk y SSO.  
  
-   Debe tener un servidor de hora en el entorno para garantizar que todos los servidores SSO estén sincronizados. Si los relojes de los servidores SSO no están sincronizados, se podría poner en peligro la seguridad del entorno.  
  
-   Suponiendo que haya un solo servidor secreto principal en todo el entorno, se recomienda usar una configuración de clúster activo-pasivo para el servidor secreto principal. Para obtener más información acerca de los clústeres del servidor secreto principal, consulte [cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md).  
  
-   El servidor secreto principal contiene la clave de cifrado que usa el sistema SSO para cifrar la información de la base de datos de SSO. Se recomienda no instalar ni configurar otros productos o servicios en este equipo.  
  
    > [!NOTE]
    >  El equipo donde instale y configure el servidor secreto principal no tiene que ser un servidor.  
  
-   El servidor secreto principal debe tener acceso a un medio extraíble o a la carpeta del sistema de archivos NTFS para poder realizar copias de seguridad y restaurar el secreto principal. Si usa un medio extraíble, asegúrese de tomar las medidas pertinentes para protegerlo. Si realiza una copia de seguridad del secreto principal en un sistema de archivos NTFS, asegúrese de proteger el archivo y la carpeta. Sólo el administrador de SSO debería tener acceso a este archivo.  
  
-   Debe realizar una copia de seguridad del secreto principal en cuanto lo genera el servidor secreto principal, con el fin de poder recuperar los datos de la base de datos de SSO en el caso de que haya problemas con el servidor secreto principal. Para obtener más información sobre la copia de seguridad del secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).  
  
-   Realice una copia de seguridad del secreto actual o genere un secreto nuevo con regularidad, por ejemplo, uno al mes. Sin el secreto, no puede recuperar la información de la base de datos de SSO. Para obtener más información acerca de la copia de seguridad y restaurar el secreto principal, consulte [administrar el secreto principal](../core/managing-the-master-secret.md).  
  
## <a name="security-recommendations-for-sso-groups-and-accounts"></a>Recomendaciones de seguridad para grupos y cuentas de SSO  
  
-   Se recomienda utilizar grupos de Windows y no cuentas de un solo usuario, especialmente para el administrador de SSO y los grupos de administradores afiliados de SSO. Estos grupos deben tener al menos dos cuentas de usuario como miembros del grupo en todo momento.  
  
-   Las cuentas de servicio de tiempo de ejecución de SSO y las cuentas de usuario de administrador de SSO deben ser diferentes, incluso si son miembros del mismo grupo de administradores de SSO. Los usuarios administradores de SSO que realicen tareas administrativas como, por ejemplo, generar y crear copias de seguridad del secreto, deben ser administradores de Windows, mientras que las cuentas de servicio de tiempo de ejecución de SSO no tienen por qué ser administradores de Windows.  
  
    > [!IMPORTANT]
    >  Los derechos de usuario del administrador de Windows no reemplazan los derechos de usuario del administrador de SSO. Para realizar cualquier tarea de administración de SSO, debe ser miembro del grupo de administradores de SSO, incluso si ya es administrador de Windows.  
  
-   Si utiliza la característica de vales de SSO, debe usar cuentas de dominio que reconozcan los equipos del dominio de procesamiento (donde están los servidores de SSO).  
  
-   Se recomienda usar una cuenta de servicio única para el servicio SSO que corresponda al servidor secreto principal.  
  
-   La cuenta de administrador de SSO es una cuenta con amplios privilegios en el sistema SSO y, a su vez, es la cuenta de administrador del servidor SQL que tiene la base de datos de SSO. Debe tener cuentas dedicadas para administradores de SSO y no debe usar estas cuentas para otros fines. Debe limitar la pertenencia al grupo de administradores de SSO sólo a aquellas cuentas responsables de ejecutar y mantener el sistema SSO.  
  
-   Debe agregar manualmente el grupo de administradores de BizTalk al grupo de administradores afiliados de SSO, de manera que los administradores de BizTalk puedan aprovechar el sistema SSO para guardar los datos de configuración de los adaptadores de la base de datos de SSO. Sólo los administradores de BizTalk que administran adaptadores deben ser miembros del grupo de administradores afiliados de SSO. No es necesario que los administradores de BizTalk sean administradores de SSO.  
  
## <a name="security-recommendations-for-an-sso-deployment"></a>Recomendaciones de seguridad para una implementación de SSO  
  
-   Si la red admite la autenticación de Kerberos, debería registrar todos los servidores SSO. Si usa la autenticación de Kerberos entre el servidor secreto principal y la base de datos de SSO, debe configurar nombres principales de servicio (SPN) en el servidor SQL donde se encuentra la base de datos de SSO. Para obtener más información acerca de cómo configurar nombres principales de servicio, vea el sitio Web de descarga de Microsoft en [http://go.microsoft.com/fwlink/?LinkId=195797](http://go.microsoft.com/fwlink/?LinkId=195797).  
  
-   Si ejecuta [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] y el servidor secreto principal está en un dominio diferente que los demás servidores de SSO y la base de datos de SSO, debe deshabilitar la seguridad RPC [como se usa para la autenticación DTC (Coordinador de transacciones de datos) entre equipos] en el servidor secreto principal, en los servidores de SSO (equipos del dominio de procesamiento) y en la base de datos de SSO. La seguridad RPC es una característica de DTC en [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] y [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Al deshabilitar la seguridad RPC, el nivel de seguridad de autenticación de DTC para llamadas a RPC vuelve al que está disponible en Microsoft Windows Server 2003.  
  
-   Los administradores de SSO deberían supervisar con regularidad el registro de sucesos del servidor secreto principal y los sucesos de auditoria de SSO del servidor de SSO.  
  
-   Además de los firewall, se recomienda usar el protocolo de seguridad de Internet (IPSec) o la Capa de sockets seguros (SSL) entre todos los servidores de SSO y la base de datos de SSO. Para obtener más información acerca de SSL, vea el sitio Web de soporte técnico de Microsoft Help y [http://go.microsoft.com/fwlink/?LinkId=195798](http://go.microsoft.com/fwlink/?LinkId=195798). Para obtener más información sobre el uso de SSL entre todos los servidores SSO y la base de datos SSO, vea [cómo habilitar SSL para SSO](../core/how-to-enable-ssl-for-sso.md).  
  
## <a name="perimeter-network"></a>Red perimetral  
 Si ejecuta los Servicios de Internet Information Server (IIS) e inicio de sesión único empresarial, siga estas recomendaciones:  
  
-   Si IIS está en una red perimetral (también conocida como zona desmilitarizada, DMZ, y subred filtrada), proporcione otro servidor IIS detrás del servidor de seguridad para conectarse al sistema SSO.  
  
-   No abra el puerto de llamadas a procedimiento remoto (RPC) en IIS.  
  
## <a name="sql-server-access"></a>Obtener acceso a SQL Server  
 Todos los servidores de SSO tienen acceso a la base de datos de SSO de SQL Server. Para obtener más información acerca de cómo seguras bases de datos de SQL Server, vea [http://go.microsoft.com/fwlink/?LinkId=33175](http://go.microsoft.com/fwlink/?LinkId=33175).  
  
 Se recomienda usar Capa de sockets seguros (SSL) y/o el protocolo de seguridad de Internet (IPSec) para proteger la transmisión de datos entre los servidores de SSO y la base de datos de SSO. Para obtener más información sobre el uso de SSL, consulte [http://go.microsoft.com/fwlink/?LinkId=195798](http://go.microsoft.com/fwlink/?LinkId=195798).  
  
 Para habilitar SSL sólo para la conexión entre el servidor de SSO y la base de datos de SSO, puede establecer la funcionalidad SSL en todos los servidores de SSO con la utilidad ssoconfigility. Esta opción habilita SSO para usar siempre SSL cuando se obtiene acceso a la base de datos de SSO. Para obtener más información, consulte [cómo habilitar SSL para SSO](../core/how-to-enable-ssl-for-sso.md).  
  
## <a name="strong-passwords"></a>Contraseñas seguras  
 Es muy importante que use contraseñas seguras para todas las cuentas, especialmente aquellas que sean miembros del grupo de administradores de SSO, porque estos usuarios tienen control sobre todo el sistema SSO.  
  
## <a name="sso-administrator-accounts"></a>Cuentas de administrador de SSO  
 Se recomienda usar cuentas de servicio diferentes para servicios SSO que se ejecuten en equipos diferentes. No debería usar la cuenta de administrador de SSO que realiza operaciones de administrador como generar y crear copias de seguridad del secreto para el servicio SSO. Si bien las cuentas de servicio SSO no deberían ser administradores locales en ese equipo, el administrador de SSO que realiza operaciones de administración debe ser un administrador local en el equipo para algunas operaciones.  
  
## <a name="master-secret-server"></a>Servidor secreto principal  
 Se recomienda encarecidamente proteger y bloquear el servidor secreto principal. No debe usar este servidor como servidor de procesamiento. El único propósito de este servidor debe ser contener el secreto principal. Debe garantizar la seguridad física de este equipo y sólo los administradores de SSO deberían tener acceso a este equipo.  
  
## <a name="kerberos"></a>Kerberos  
 SSO admite Kerberos y se recomienda configurar Kerberos para SSO. Para configurar Kerberos con SSO, debe registrar un nombre principal de servicio (SPN) para el servicio SSO. De forma predeterminada, cuando se configura Kerberos, SSO utiliza ese nombre SPN para autenticar los componentes que usan el servicio SSO. Se recomienda configurar la autenticación de Kerberos entre los subservicios administrativos de SSO y el servidor de SSO. También puede usar la autenticación de Kerberos entre los servidores de SSO y entre éstos y el servidor SQL donde se encuentra la base de datos de SSO.  
  
 Para configurar y comprobar Kerberos, use las utilidades setspn y kerbtray. Para obtener más información acerca de estas utilidades, consulte [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).  
  
## <a name="delegation"></a>Delegación  
 Cuando se usa [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], se puede usar delegación restringida, pero se recomienda no usar delegación para realizar tareas de administrador de inicio de sesión único. De forma similar, se recomienda no delegar tareas adicionales ni derechos de usuario en el administrador de inicio de sesión único.  
  
## <a name="auditing"></a>Auditoría  
 La auditoría es un mecanismo crítico para mantener un seguimiento de la información en el entorno. El inicio de sesión único (SSO) empresarial audita todas las operaciones realizadas en la base de datos de SSO. SSO utiliza registros de sucesos y de auditoría de la propia base de datos. SSO proporciona dos niveles de auditoría para los servidores de inicio de sesión único:  
  
-   Los niveles de auditoría positivos auditan las operaciones que se han realizado correctamente  
  
-   Los niveles de auditoría negativos auditan las operaciones que no se realizan correctamente  
  
 Los administradores de SSO pueden establecer niveles de auditoría positivos y negativos que se ajusten a sus directivas corporativas.  
  
 Puede establecer auditorías positivas y negativas en uno de los niveles siguientes:  
  
 0 = Ninguno. Este nivel no emite mensajes de auditoría  
  
 1 = Bajo  
  
 2 = Medio  
  
 3 = Alto. Este nivel emite todos los mensajes de auditoría posibles  
  
 El valor predeterminado para la auditoría positiva es 0 (ninguno), y el valor predeterminado para la auditoría negativa es 1 (bajo). Puede cambiar estos valores en función del nivel de auditoría que desee para su sistema SSO.  
  
> [!IMPORTANT]
>  La auditoría de inicio de sesión único empresarial emite mensajes generados por el servicio de inicio de sesión único. Esto no es una auditoría de seguridad y el sistema SSO no guarda la información en el registro de seguridad del registro de sucesos. El sistema SSO guarda los mensajes de auditoría de SSO directamente en el registro de sucesos de aplicación.  
  
### <a name="database-level-auditing"></a>Auditoría de la base de datos  
 Para la auditoría de la base de datos, el sistema SSO realiza un seguimiento de las operaciones realizadas en la base de datos de SSO en las tablas de auditoría de la base de datos. El tamaño de estas tablas de auditoría se define en el nivel de sistema SSO. Puede auditar aplicaciones afiliadas eliminadas, asignaciones eliminadas y búsquedas de credenciales. De manera predeterminada, el tamaño de auditoría se establece en 1.000 entradas. Los administradores de SSO pueden cambiar este tamaño para satisfacer sus directivas corporativas.  
  
## <a name="using-sso-accounts"></a>Usar cuentas de SSO  
 Esta sección contiene prácticas recomendadas para usar grupos de dominio y locales, y cuentas individuales en el sistema de inicio de sesión único (SSO) empresarial.  
  
### <a name="domain-windows-groups-and-accounts"></a>Grupos y cuentas de dominio de Windows  
 Cuando se trabaja con grupos de dominio de Windows, se aplican las siguientes recomendaciones:  
  
-   Use grupos y cuentas de dominio.  
  
-   Al usar [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], se puede configurar la cuenta de servicio ENTSSO para que se ejecute en la cuenta de servicio de red. No obstante, esto no resulta recomendable por razones de seguridad, puesto que será preciso otorgar privilegios de administrador de SSO a la cuenta de servicio de red. En lugar de ello, se recomienda utilizar una única cuenta de servicio de dominio para la cuenta de servicio ENTSSO.  
  
-   Use un grupo de dominio para los administradores de SSO. No debe especificar una cuenta de dominio individual como administrador de SSO, puesto que no puede cambiar esta cuenta de una cuenta individual a otra individual.  
  
-   Aunque puede especificar una cuenta de dominio individual como el administrador afiliado de SSO, debe usar un grupo de dominio.  
  
-   Si bien puede especificar una cuenta de dominio individual como administrador afiliado de SSO, debe usar un grupo de dominio.  
  
-   Debe usar grupos de dominio para la cuenta de usuarios de aplicación. La cuenta de usuarios de aplicaciones de SSO no admite una cuenta individual.  
  
-   Se pueden especificar varias cuentas para cada una de estas cuentas de acceso de SSO.  
  
## <a name="see-also"></a>Vea también  
 [Puertos de los servidores de inicio de sesión único de Enterprise](../core/ports-for-the-enterprise-single-sign-on-servers.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)