---
title: Servicio Web de las operaciones de BizTalk | Microsoft Docs
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
ms.openlocfilehash: 0b9a78dddbbd76566c5c97b1e571e5ad80073d4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997973"
---
# <a name="the-biztalk-operations-web-service"></a>El servicio Web de las operaciones de BizTalk
El servicio Web de operaciones de Microsoft BizTalk expone información sobre los objetos y los mensajes en BizTalk Server. Es el nombre del servicio **ESB.BizTalkOperationsService**, y el servicio expone una amplia variedad de métodos que devuelven elementos como una lista de hosts, las orquestaciones, las aplicaciones y el estado de la aplicación de BizTalk.  
  
 Están disponibles los siguientes métodos:  
  
-   **Aplicaciones**. Este método no toma ningún parámetro y devuelve el nombre y la descripción de todas las aplicaciones instaladas de BizTalk como una colección de **BTApplication** objetos.  
  
-   **ApplicationStatus**. Este método toma como parámetro el nombre de la aplicación, y devuelve información acerca de la aplicación de BizTalk especificada como un **BTSysStatus** instancia. Esta información incluye las orquestaciones, puertos de envío, ubicaciones de recepción y los detalles del host.  
  
-   **GetLiveMessageBody**. Este método toma como parámetros un identificador de mensaje y un identificador de instancia y devuelve el cuerpo del mensaje, desde el entorno de producción como un **BTMsgBody** instancia.  
  
-   **GetMessageInstances**. Este método toma como parámetro, el tipo de mensaje y devuelve todos los mensajes coincidentes como una colección de **BTMsgInstance** objetos.  
  
-   **GetOrchestrationInstances**. Este método toma como parámetros el nombre de una orquestación y devuelve una colección de **BTOrchestrationInstance** objetos que contienen información detallada de las orquestaciones coincidentes.  
  
-   **GetTrackedMessageBody**. Este método toma como parámetro un GUID del mensaje y devuelve el cuerpo del mensaje, como un **BTMsgBody** instancia una vez que se procesa en BizTalk.  
  
-   **Hosts**. Este método toma como parámetro el nombre de un host, y devuelve información acerca de la instancia de host especificado como una colección de **BTHost** instancias. Utilice una cadena vacía para el parámetro de nombre de host para devolver información sobre todas las instancias de host.  
  
-   **MessageFlowTree**. Este método toma como parámetro un identificador de instancia y devuelve los detalles del flujo de mensajes para ese mensaje como un **RouteTreeNode** instancia.  
  
-   **Orquestaciones**. Este método toma como parámetro el nombre de una orquestación y devuelve toda la información de esa orquestación como un **BTSysStatus** instancia. Use una cadena vacía para el parámetro de nombre de la orquestación para devolver información sobre todas las orquestaciones.  
  
-   **ReceiveLocations**. Este método toma como parámetro el nombre de una ubicación de recepción y devuelve toda la información para la coincidencia de ubicaciones, como un **BTSysStatus** instancia. Use una cadena vacía para el parámetro de nombre de las ubicaciones de recepción para devolver información sobre todas las ubicaciones.  
  
-   **ReceiveLocationsByDescription**. Este método toma como parámetro de la descripción de una ubicación de recepción y devuelve toda la información para la coincidencia de ubicaciones, como un **BTSysStatus** instancia. Use una cadena vacía para el parámetro description para devolver información sobre todas las ubicaciones.  
  
-   **Puertos de envío**. Este método toma como parámetro el nombre de un puerto de envío y devuelve toda la información para la coincidencia de puertos como un **BTSysStatus** instancia. Utilice una cadena vacía para el parámetro de nombre de puerto de envío para devolver información acerca de todos los puertos.  
  
-   **SendPortsByDescription**. Este método toma como parámetro de la descripción de un puerto de envío y devuelve toda la información para la coincidencia de puertos como un **BTSysStatus** instancia. Utilice una cadena vacía para el parámetro description para devolver información acerca de todos los puertos.  
  
-   **StatusChanged**. Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de IIS y el servidor que hospeda el servicio UDDI con IPSec de nivel de red y los permisos adecuados de ACL de nivel de archivo.  
  
-   **SystemStatus**. Este método no toma ningún parámetro y devuelve los detalles sobre el estado del sistema de BizTalk como un **BTSysStatus** instancia.  
  
-   **UpdateReceiveLocationDescription**. Este método actualiza la descripción de una ubicación de recepción especificada con valores de parámetros que contienen el nombre de la aplicación, el nombre del puerto de recepción, el nombre de la ubicación de recepción y la descripción de la ubicación de recepción. Devuelve una cadena que indica el resultado de la operación. Tenga en cuenta que la aplicación de cliente de prueba lee esta información de su archivo App.config.  
  
-   **UpdateSendPortDescription**. Este método actualiza la descripción de un puerto de envío especificado con valores de parámetros que contienen el nombre del puerto de envío y la descripción del puerto de envío. Devuelve una cadena que indica el resultado de la operación. Tenga en cuenta que la aplicación de cliente de prueba lee esta información de su archivo App.config.  
  
## <a name="configuring-the-biztalk-operations-web-service"></a>Configuración del servicio Web de las operaciones de BizTalk  
 El servicio Web de las operaciones de BizTalk o bien se comunica directamente con las bases de datos de administración de BizTalk Server mediante Windows Management Instrumentation (WMI) o utiliza las operaciones de BizTalk y el Explorador de API para obtener la información necesaria. Por lo tanto, debe asegurarse de que su sistema cumple las condiciones siguientes y que configure la configuración de permisos de seguridad siguientes:  
  
- Establecer el **allowOverride** atributo en el archivo Web.config de nivel de equipo a **false** para asegurarse de que los desarrolladores no pueden cambiar el nivel de confianza de sus aplicaciones.  
  
- De forma predeterminada, el servicio Web de las operaciones de BizTalk no está configurado para que requiera Secure Sockets Layer (SSL) cuando obtiene acceso a los clientes. Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de Internet Information Services (IIS) y el equipo que ejecuta SQL Server que hospeda la base de datos BizTalkMgmtDb mediante IPSec de nivel de red y permisos de lista (ACL) del control de acceso de nivel de archivo adecuado.  
  
- Los usuarios acceder al servicio Web de las operaciones de BizTalk deben ser miembros del grupo de administradores de BizTalk Server predeterminado para algunos métodos y miembros del grupo de usuarios de la aplicación de BizTalk predeterminada para otros métodos.  
  
- Debe asegurarse de que el servicio Web de las operaciones de BizTalk reside en un directorio virtual denominado ESB.BizTalkOperationsService que tiene deshabilitado el acceso anónimo.  
  
- Los usuarios deben tener **seleccione** permiso de varias tablas en SQL Server se encuentra en la base de datos BizTalkMgmtDb y la base de datos BizTalkMsgBoxDb. Use SQL Server Management Studio para establecer los permisos siguientes:  
  
  -   En la base de datos BizTalkMgmtDb, configure el rol de base de datos BTS_ADMIN_USERS con **seleccione** permiso en las tablas siguientes:  
  
      -   adm_Server2HostMapping  
  
      -   adm_Server  
  
      -   adm_hostInstance  
  
  -   En la base de datos BizTalkMsgBoxDb, configure el rol de base de datos BTS_ADMIN_USER con **seleccione** permiso en la tabla ProcessHeartbeats.  
  
  En SQL Server Management Studio, puede configurar los permisos necesarios. Para ello, expanda **seguridad** en la vista de árbol del panel izquierdo del explorador de objetos, expanda **Roles**, expanda **DatabaseRoles**, seleccione la función BTS_ADMIN_USERS y, a continuación, edite la propiedades de este rol, tal como se muestra en la figura 1.  
  
  ![SQL Server Management Studio](../esb-toolkit/media/ch4-sqlservermgmtstudio.gif "Ch4-SQLServerMgmtStudio")  
  
  **Figura 1**  
  
  **Editar permisos para el rol de base de datos BTS_ADMIN_USERS en Microsoft SQL Server Management Studio**  
  
> [!NOTE]
>  Debe configurar este servicio para usar seguridad integrada de Windows y ejecutar en la cuenta de servicio de red integrada. También debe habilitar la autenticación Kerberos en el servidor Web de IIS para que envíe el encabezado **Negotiate, NTLM** al cliente. Para obtener más información, consulte [cómo configurar IIS para que admita el protocolo Kerberos y el protocolo NTLM para la autenticación de red](http://go.microsoft.com/fwlink/?LinkId=186430)([http://go.microsoft.com/fwlink/?LinkId=186430](http://go.microsoft.com/fwlink/?LinkId=186430)).  
>   
>  De forma predeterminada, el servicio Web de las operaciones de BizTalk no está configurado para requerir SSL cuando obtiene acceso a los clientes. Debe configurar el servicio para que requiera SSL para el acceso de cliente y proteger la conexión entre el equipo de host del servicio Web de IIS y el servidor que hospeda el servicio UDDI con IPSec de nivel de red y los permisos adecuados de ACL de nivel de archivo.