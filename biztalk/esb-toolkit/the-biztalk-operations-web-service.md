---
title: Servicio Web de las operaciones de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af38815f-f643-4598-9148-6499071d12e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d09fb2cdcca83e8a9f2e4e7704178d40a915065
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22296916"
---
# <a name="the-biztalk-operations-web-service"></a>El servicio Web de las operaciones de BizTalk
El servicio Web de Microsoft BizTalk Operations expone información sobre los objetos y los mensajes en BizTalk Server. El nombre de servicio es **ESB.BizTalkOperationsService**, y el servicio expone una amplia variedad de métodos que devuelven elementos como una lista de hosts, orquestaciones, las aplicaciones y el estado de la aplicación de BizTalk.  
  
 Los métodos siguientes están disponibles:  
  
-   **Aplicaciones**. Este método no toma ningún parámetro y devuelve el nombre y la descripción de todas las aplicaciones instaladas de BizTalk como una colección de **BTApplication** objetos.  
  
-   **ApplicationStatus**. Este método toma como parámetro el nombre de la aplicación y devuelve información acerca de la aplicación de BizTalk especificada como un **BTSysStatus** instancia. Esta información incluye las orquestaciones, puertos de envío, ubicaciones de recepción y detalles del host.  
  
-   **GetLiveMessageBody**. Este método toma como parámetros de un identificador de mensaje y un identificador de instancia y devuelve el cuerpo del mensaje, desde el entorno activo como un **BTMsgBody** instancia.  
  
-   **GetMessageInstances**. Este método toma como parámetro, el tipo de mensaje y devuelve todos los mensajes coincidentes como una colección de **BTMsgInstance** objetos.  
  
-   **GetOrchestrationInstances**. Este método toma como parámetros el nombre de una orquestación y devuelve una colección de **BTOrchestrationInstance** objetos que contienen detalles de las orquestaciones coincidentes.  
  
-   **GetTrackedMessageBody**. Este método toma como parámetro un GUID del mensaje y devuelve el cuerpo del mensaje, como un **BTMsgBody** instancia después de que se procesa en BizTalk.  
  
-   **Hosts**. Este método toma como parámetro el nombre de un host, y devuelve información sobre la instancia de host especificado como una colección de **BTHost** instancias. Use una cadena vacía para el parámetro de nombre de host para devolver información sobre todas las instancias de host.  
  
-   **MessageFlowTree**. Este método toma como parámetro un identificador de instancia y devuelve los detalles de flujo de mensajes para ese mensaje como una **RouteTreeNode** instancia.  
  
-   **Orquestaciones**. Este método toma como parámetro el nombre de una orquestación y devuelve toda la información de esa orquestación como un **BTSysStatus** instancia. Use una cadena vacía para el parámetro de nombre de la orquestación para devolver información sobre todas las orquestaciones.  
  
-   **ReceiveLocations**. Este método toma como parámetro el nombre de una ubicación de recepción, y devuelve toda la información para la coincidencia de ubicaciones como un **BTSysStatus** instancia. Use una cadena vacía para el parámetro de nombre de ubicaciones de recepción para devolver información sobre todas las ubicaciones.  
  
-   **ReceiveLocationsByDescription**. Este método toma como parámetro, la descripción de una ubicación de recepción, y devuelve toda la información para la coincidencia de ubicaciones como un **BTSysStatus** instancia. Use una cadena vacía para el parámetro description para devolver información sobre todas las ubicaciones.  
  
-   **PuertosEnvío**. Este método toma como parámetro el nombre de un puerto de envío, y devuelve toda la información para la coincidencia de puertos como una **BTSysStatus** instancia. Use una cadena vacía para el parámetro de nombre de puerto de envío para devolver información acerca de todos los puertos.  
  
-   **SendPortsByDescription**. Este método toma como parámetro, la descripción de un puerto de envío, y devuelve toda la información para la coincidencia de puertos como una **BTSysStatus** instancia. Utilice una cadena vacía para el parámetro description para devolver información acerca de todos los puertos.  
  
-   **StatusChanged**. Este método toma como parámetro una marca de tiempo y devuelve los detalles de objetos de BizTalk (por ejemplo, puertos, los hosts y las orquestaciones) modificados desde la marca de tiempo especificado como un **BTSysStatus** instancia.  
  
-   **SystemStatus**. Este método no toma ningún parámetro y devuelve información detallada sobre el estado de sistema de BizTalk como un **BTSysStatus** instancia.  
  
-   **UpdateReceiveLocationDescription**. Este método actualiza la descripción de una ubicación de recepción especificada utilizando los valores de parámetros que contienen el nombre de la aplicación, el nombre de puerto de recepción, el nombre de la ubicación de recepción y la descripción de la ubicación de recepción. Devuelve una cadena que indica el resultado de la operación. Tenga en cuenta que la aplicación de cliente de prueba lee esta información mediante el archivo App.config.  
  
-   **UpdateSendPortDescription**. Este método actualiza la descripción de un puerto de envío especificado con valores de parámetros que contienen el nombre del puerto de envío y la descripción del puerto de envío. Devuelve una cadena que indica el resultado de la operación. Tenga en cuenta que la aplicación de cliente de prueba lee esta información mediante el archivo App.config.  
  
## <a name="configuring-the-biztalk-operations-web-service"></a>Configurar el servicio Web de las operaciones de BizTalk  
 El servicio Web de las operaciones de BizTalk o se comunica directamente con las bases de datos de administración de BizTalk Server mediante Instrumental de administración de Windows (WMI) o utiliza las operaciones de BizTalk y la API del explorador para obtener la información que necesita. Por lo tanto, debe asegurarse de que su sistema cumple las siguientes condiciones y que configure la configuración de permisos de seguridad siguientes:  
  
-   Establecer el **allowOverride** atributo en el archivo Web.config de nivel de equipo para **false** para asegurarse de que los desarrolladores no pueden cambiar el nivel de confianza de sus aplicaciones.  
  
-   De forma predeterminada, el servicio Web de las operaciones de BizTalk no está configurado para que requiera Secure Sockets Layer (SSL) a los que tienen acceso los clientes. Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el equipo que ejecuta SQL Server que hospeda la base de datos de BizTalkMgmtDb mediante IPSec de nivel de red y permisos de lista (ACL) de control de acceso de nivel de archivo adecuado.  
  
-   Los usuarios tener acceso al servicio Web de las operaciones de BizTalk deben ser miembros del grupo de administradores de BizTalk Server de forma predeterminada para algunos métodos y miembros del grupo de usuarios de la aplicación de BizTalk predeterminado para los otros métodos.  
  
-   Debe asegurarse de que el servicio Web de las operaciones de BizTalk reside en un directorio virtual de IIS denominado ESB.BizTalkOperationsService que tenga deshabilitado el acceso anónimo.  
  
-   Los usuarios deben tener **seleccione** permiso en SQL Server para varias tablas que se encuentra en la base de datos de BizTalkMgmtDb y la base de datos BizTalkMsgBoxDb. Use SQL Server Management Studio para establecer los permisos siguientes:  
  
    -   En la base de datos BizTalkMgmtDb, configurar el rol de base de datos BTS_ADMIN_USERS con **seleccione** permiso en las tablas siguientes:  
  
        -   adm_Server2HostMapping  
  
        -   adm_Server  
  
        -   adm_hostInstance  
  
    -   En la base de datos BizTalkMsgBoxDb, configurar el rol de base de datos BTS_ADMIN_USER con **seleccione** permiso en la tabla ProcessHeartbeats.  
  
 En SQL Server Management Studio, puede configurar los permisos necesarios. Para ello, expanda **seguridad** en la vista de árbol del panel izquierdo del explorador de objetos, expanda **Roles**, expanda **DatabaseRoles**, seleccione el rol BTS_ADMIN_USERS y, a continuación, edite la propiedades de este rol, tal y como se muestra en la figura 1.  
  
 ![SQL Server Management Studio](../esb-toolkit/media/ch4-sqlservermgmtstudio.gif "SQLServerMgmtStudio Ch4")  
  
 **Figura 1**  
  
 **Editar permisos para el rol de base de datos BTS_ADMIN_USERS en Microsoft SQL Server Management Studio**  
  
> [!NOTE]
>  Debe configurar este servicio para usar seguridad integrada de Windows y ejecutar en la cuenta de servicio de red integrada. También debe habilitar la autenticación Kerberos en el servidor Web de IIS para que envía el encabezado **Negotiate, NTLM** al cliente. Para obtener más información, consulte [cómo configurar IIS para que admita el protocolo Kerberos y el protocolo NTLM para la autenticación de red](http://go.microsoft.com/fwlink/?LinkId=186430)([http://go.microsoft.com/fwlink/?LinkId=186430](http://go.microsoft.com/fwlink/?LinkId=186430)).  
>   
>  De forma predeterminada, el servicio Web de las operaciones de BizTalk no está configurado para requerir SSL cuando tiene acceso a los clientes. Debe configurar el servicio para que requiere SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de IIS y el servidor que hospeda el servicio UDDI mediante IPSec de nivel de red y los permisos adecuados de ACL de nivel de archivo.