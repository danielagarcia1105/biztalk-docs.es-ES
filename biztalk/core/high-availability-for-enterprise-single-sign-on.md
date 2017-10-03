---
title: "Alta disponibilidad para el inicio de sesión único empresarial | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-02-29
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, availability
- high availability, SSO
- Master Secret server, high availability
- SSO, high availability
ms.assetid: 6c631b5c-7147-4cc0-b58a-6749e83df9d3
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 023eaa82b11353347040dea13fc126f6044db3bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="high-availability-for-enterprise-single-sign-on"></a>Alta disponibilidad del inicio de sesión único (SSO) empresarial
Aunque no utilice la funcionalidad de inicio de sesión único (SSO) empresarial para asignar credenciales e inicios de sesión únicos, SSO es una parte fundamental de la infraestructura global de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ya que BizTalk Server utiliza SSO para proteger la información de las ubicaciones de recepción.  
  
 Debe configurar el primer equipo en el que instale el servicio SSO como servidor secreto principal. El servidor secreto principal es el servidor SSO que almacena el secreto (clave de cifrado) principal. El secreto principal es la clave de cifrado que utiliza el sistema SSO para cifrar y descifrar los datos que almacena en la base de datos de SSO.  
  
 Si un servidor SSO deja de funcionar y hay otros equipos BizTalk Server (y, por consiguiente, servidores SSO) que están ejecutando la misma instancia de host, los demás servidores SSO siguen funcionando. Esto significa que el servidor secreto principal sigue funcionando correctamente y, por tanto, el procesamiento de BizTalk Server continúa.  
  
 Si se produce un error en el servidor secreto principal, todas las operaciones en tiempo de ejecución que se estaban ejecutando antes de que se produjese el error, incluido el descifrado de credenciales, continuarán con normalidad. No obstante, no se pueden cifrar nuevas credenciales. Por tanto, el entorno de BizTalk Server depende de la disponibilidad del servidor secreto principal, como se muestra en la ilustración siguiente.  
  
 ![Puntos de error](../core/media/tdi-highava-pointsfailure-mss.gif "TDI_HighAva_PointsFailure_MSS")  
  
> [!NOTE]
>  Si deja de estar disponible el servidor secreto principal, las instancias de host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] seguirán realizando operaciones en tiempo de ejecución usando la copia almacenada en caché de memoria del secreto maestro hasta que:  
>   
>  -   Se reinician las instancias de host.  
> -   Se reinicia el servicio SSO en el equipo que ejecuta instancias de host de BizTalk.  
> -   Cambia el secreto principal de SSO.  
>   
>  Si se reinicia el servicio SSO en los equipos [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o cambia el secreto principal SSO, la copia en caché del secreto maestro se libera de la memoria y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] debe poder contactar con el servidor de secreto principal con el fin de obtener otra copia del secreto principal. Si el servidor secreto principal no está disponible entonces, fallará cualquier operación administrativa que requiera obtener acceso al servidor secreto principal con fines de cifrado.  
  
## <a name="making-the-master-secret-server-available"></a>Hacer que el servidor secreto principal esté disponible  
 Para la disponibilidad del sistema SSO y, por tanto, del entorno de BizTalk Server, es fundamental crear una copia de seguridad del secreto principal inmediatamente después de generarlo. Si se pierde, se perderán también los datos que cifró el sistema SSO utilizando ese secreto principal. Para obtener más información sobre la copia de seguridad del secreto principal, consulte [cómo volver la seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).  
  
 Puede hacer que el servidor secreto principal esté disponible de dos maneras:  
  
-   **Disponible, pero no una alta disponibilidad.** todos los servidores SSO tienen el secreto principal almacenado en la memoria caché y las operaciones en tiempo de ejecución continuarán incluso si se produce un error en el servidor secreto principal. Sin embargo, no podrá cambiar la configuración de los puertos ni la configuración de SSO. El motor de tiempo de ejecución de BizTalk Server seguirá funcionando sin problemas, pero no podrá realizar ningún cambio de diseño.  
  
     Aunque esta configuración no ofrezca una alta disponibilidad, puede ser satisfactoria para la mayoría de los escenarios y es coherente con la escala de las operaciones de recepción, envío y procesamiento de host.  
  
-   **Alta disponibilidad.** para proporcionar redundancia al servidor secreto principal, utilice la Organización por clústeres de Windows en un clúster de servidores secretos principales diferente o configure el servidor secreto principal en un clúster de base de datos existente. Los servicios que proporciona el servidor secreto principal no consumen muchos recursos y, normalmente, no afectan a la funcionalidad de la base de datos ni al rendimiento si se instalan en un clúster de base de datos. La siguiente ilustración muestra cómo aportar alta disponibilidad al servidor secreto principal.  
  
     ![Servidor secreto principal de alta disponibilidad](../core/media/tdi-highava-msscluster.gif "TDI_HighAva_MSSCluster")  
  
     Aunque esta configuración tenga una alta disponibilidad, requiere recursos de hardware adicionales. Para obtener más información acerca de las opciones de instalación de alta disponibilidad para SSO, vea [opciones de instalación de SSO de alta disponibilidad](../core/high-availability-sso-installation-options.md). Esta sección incluye información detallada acerca de la configuración del servicio secreto principal de SSO como recurso de clúster de alta disponibilidad en un clúster de Windows Server.  
  
    > [!NOTE]
    >  Para reducir los recursos de hardware en una solución de alta disponibilidad, puede agregar el servidor secreto principal como recurso de clúster al clúster de SQL Server. No es necesario adquirir más licencias de servidor BizTalk Server para instalar el servicio SSO en otro equipo.  
  
## <a name="see-also"></a>Vea también  
 [Agrupación en clústeres las bases de datos de servidor BizTalk Server](../core/clustering-the-biztalk-server-databases1.md)   
 [Crear un entorno de alta disponibilidad de servidor de BizTalk Server](../core/creating-a-highly-available-biztalk-server-environment.md)   
 [Cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md)