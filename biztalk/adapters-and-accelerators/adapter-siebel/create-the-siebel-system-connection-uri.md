---
title: Crear el URI de conexión del sistema de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- connecting to Siebel, using the connection URI
- how to, connect using connection URI
- connecting using connection URI
ms.assetid: 8cc78149-1c20-40db-aece-aab520ee04e7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3360433e97b9b7d21a06d3ad5c304f37a924589f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000621"
---
# <a name="create-the-siebel-system-connection-uri"></a>Crear el URI de conexión del sistema de Siebel
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] URI de conexión contiene propiedades que el adaptador utiliza para establecer una conexión con el sistema Siebel.  

 En este tema se proporciona información sobre el URI de conexión de Siebel y también proporciona vínculos a otros temas que explican cómo especificar un URI de conexión en diferentes situaciones de programación.  

## <a name="connection-uri-for-the-siebel-adapter"></a>URI de conexión para el adaptador de Siebel  
 Una típica [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] dirección de punto de conexión URI se representa como sigue:  

```  
scheme://userinfoparams@hostinfoparams?query_string  
```  

 La dirección URI del extremo contiene los siguientes componentes:  

- esquema es el nombre de esquema.  

- userinfoparams es una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario por el punto de conexión.  

- hostinfoparams es la información necesaria para establecer la conexión al host; Por ejemplo, una ruta de acceso.  

- QUERY_STRING es una colección de nombre y valor opcional de parámetros que se delimitan mediante un signo de interrogación (?).  

  El URI de conexión de Siebel sigue este formato general y se implementa como sigue:  

```  
siebel://Username=[USER_NAME];Password=[PASSWORD]@[SERVER]:[PORT]?SiebelObjectManager=[SIEBEL_OBJECT_MANAGER_NAME]&SiebelEnterpriseServer=[SERVER_NAME]&Language=[LANGUAGE]&Transport=[TRANSPORT]&Encryption=[ENCRYPTION]&Compression=[COMPRESSION]&SiebelServer=[SIEBEL_SERVER_NAME]&SiebelRepository=[SIEBEL_REPOSITORY_NAME]  
```  

 Las secciones siguientes describen las propiedades implementadas para cada componente de URI de conexión de Siebel.  

### <a name="the-scheme-for-the-siebel-connection-uri"></a>El esquema para el URI de conexión de Siebel  
 El esquema para el URI de conexión de Siebel es "siebel".  

### <a name="user-information-in-the-siebel-connection-uri"></a>Información de usuario en el URI de conexión de Siebel  
 De forma predeterminada, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce una excepción cuando se especifican las credenciales del sistema de Siebel en el URI de conexión. Esto es porque estas credenciales se representan como texto sin formato, lo que supone un riesgo de seguridad inherente. Puede establecer el **AcceptCredentialsInUri** enlaza la propiedad para controlar si el URI de conexión puede contener las credenciales. Si el **AcceptCredentialsInUri** propiedad es **false**, [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] produce una excepción si el URI de conexión contiene credenciales; si la propiedad es **true**, se produce ninguna excepción.  

> [!IMPORTANT]
>  Debido a los riesgos inherentes de seguridad que suponen pasando las credenciales en las cadenas como texto sin formato, es mejor no deben especificar las credenciales del sistema de Siebel en el URI de conexión.  

 Hay varias maneras de proporcionar las credenciales del sistema de Siebel sin especificarlos en el URI de conexión.  

- En el código, puede establecer el **ClientCredentials** propiedad en el objeto adecuado.  

- Cuando se usa el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], puede escribir las credenciales seleccionando la **seguridad** pestaña de la **configurar el adaptador** cuadro de diálogo.  

- Al especificar un puerto de envío o recepción de enlace de la ubicación en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución, puede escribir las credenciales seleccionando la **seguridad** ficha del cuadro de diálogo correspondiente.  

  La información de usuario (userinfoparams) en la conexión de Siebel que URI se representa como una colección de nombre y valor de los parámetros necesarios para la autenticación de usuario. En la tabla siguiente se describe estos parámetros.  

| Property |                                                                                                                                                                                                          Descripción                                                                                                                                                                                                          |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre de usuario |      El nombre de usuario en el sistema Siebel; Este valor distingue mayúsculas de minúsculas. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión. **Nota:** el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] conserva el caso del valor que especifique para el nombre de usuario cuando se abre una conexión en el sistema Siebel.       |
| Contraseña | La contraseña del usuario en el sistema Siebel; Este valor distingue mayúsculas de minúsculas. Debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para especificar el nombre de usuario y la contraseña en el URI de conexión. **Nota:** el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] conserva el caso del valor que escriba la contraseña cuando se abre una conexión en el sistema Siebel. |

### <a name="host-information-in-the-siebel-connection-uri"></a>Información del host en el URI de conexión de Siebel  
 La información de host de Siebel (hostinfoparams) especifica la dirección del sistema Siebel en el siguiente formato: [servidor]: [puerto]. Según la versión del servidor de Siebel, la información de host de Siebel toma valores diferentes:  

- **Para la versión 7.5 y versiones anterior de Siebel**, el parámetro de información de host toma el nombre del equipo en el servidor de puerta de enlace de Siebel está instalado y el número de puerto de la puerta de enlace de Siebel.  

- **Para la versión 7.7 y versiones posterior de Siebel**, el parámetro de información de host toma el nombre del equipo en el que el servidor está instalado de Siebel y la conexión de Siebel broker número de puerto.  

  > [!IMPORTANT]
  >  Cuando se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para conectarse a un sistema de Siebel, se debe proporcionar la información de host para la propiedad de conexión "SiebelGateway".  

### <a name="query-information-in-the-siebel-connection-uri"></a>Información de la consulta en el URI de conexión de Siebel  
 La información de consulta (query_string) en el URI de conexión de Siebel se utiliza para especificar las propiedades de conexión adicionales.  


|        Property        |                                                                                                                                          Descripción                                                                                                                                           |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  SiebelObjectManager   |                                                                                                  El nombre del Administrador de objetos Siebel del servidor de empresa. Este parámetro es obligatorio.                                                                                                   |
| SiebelEnterpriseServer |                                                                                                             El nombre del servidor de empresa de Siebel. Este parámetro es obligatorio.                                                                                                              |
|        Idioma        |                                             El idioma del Administrador de objetos. Este parámetro es opcional. Si no se especifica, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] proporciona un valor predeterminado (ESN).                                              |
|       Transporte        |                                                                        El transporte; solamente se admite tcpip. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (TCP/IP).                                                                         |
|       Cifrado       | El tipo de cifrado debe utilizar entre el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y el sistema Siebel. Los valores admitidos son none, mscrypto, o rsa. Este parámetro es opcional. Si no se especifica, el sistema de Siebel suministra el valor predeterminado es (ninguno). |
|      Compresssion      |    El algoritmo de compresión debe utilizar entre el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y el sistema Siebel. Los valores admitidos son none o zlib. Este parámetro es opcional. Si no se especifica, el sistema Siebel proporciona un valor predeterminado (zlib).     |
|      SiebelServer      |                                                                                 El servidor de Siebel. Necesario para todas las conexiones de servidor Siebel 7.5 (7.5.2, 7.5.3, etcetera.); en caso contrario, no establezca este parámetro.                                                                                  |
|    SiebelRepository    |                          El repositorio de Siebel. Necesario si existe más de un repositorio en el servidor. en caso contrario, es opcional. **Nota:** si existe más de un repositorio en el servidor, debe especificar un repositorio de destino en el parámetro SiebelRepository.                           |

 Para obtener más información acerca de los parámetros de Siebel a la que se establecen en la información de consulta, consulte la documentación de Siebel.  

## <a name="using-reserved-characters-in-the-connection-uri"></a>Utilizar caracteres reservados en el URI de conexión  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no admite la especificación de un URI que incluye caracteres especiales para cualquiera de los valores de parámetro de conexión. Si los valores de parámetro de conexión contienen caracteres especiales, asegúrese de que se realice una de las siguientes acciones:  

- Si va a especificar el URI en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] mediante [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], deberá especificarlos como-está en el **propiedades de URI** pestaña, es decir, sin usar cualquier carácter de escape. Si especifica el URI directamente en el **configurar un URI** campo y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  

- Si se especifica el URI al crear un envío o recepción de puerto en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración y los parámetros de conexión contienen caracteres reservados, debe especificar los parámetros de conexión con los caracteres de escape adecuados.  

## <a name="using-the-connection-uri-to-connect-to-the-siebel-system"></a>Usar el URI de conexión para conectarse al sistema Siebel  
 El siguiente es un URI de conexión de Siebel de ejemplo.  

```  
siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=entserver&Language=enu  
```  

> [!NOTE]
>  Este URI de ejemplo contiene las credenciales de sistema de Siebel; debe establecer el **AcceptCredentialsInUri** enlazar la propiedad a **true** para usar un URI que contiene las credenciales de conexión.  

 Para obtener información acerca de cómo establecer una conexión con el sistema Siebel (incluida la configuración de las propiedades de conexión) al:  

- Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).  

- Configurar un puerto de envío o recepción (ubicación) del puerto en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución, consulte [configurar manualmente un enlace de puerto físico para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md).

- Utilizar el modelo de canal WCF en una solución de programación, vea [crean un canal mediante Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md).  

- Utilizar el modelo de servicio WCF en una solución de programación, vea [configurar un cliente de WCF para un sistema Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md).  

- Utilice WCF ServiceModel Metadata Utility Tool (svcutil.exe), consulte [uso ServiceModel Metadata Utility Tool con el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md).  

## <a name="see-also"></a>Vea también  
 [Crear una conexión con el sistema de Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-connection-to-the-siebel-system.md)   
[Desarrollar aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)   
 [Desarrollar aplicaciones de Siebel con el Model3 de canal de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)   
 [Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)