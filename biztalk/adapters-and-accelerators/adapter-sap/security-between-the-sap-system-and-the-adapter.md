---
title: Seguridad entre el sistema SAP y el adaptador | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72e0125887483cf9092b0ef4f73d7ca19fd3790c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982557"
---
# <a name="security-between-the-sap-system-and-the-adapter"></a>Seguridad entre el sistema SAP y el adaptador
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es compatible con las comunicaciones de red segura (SNC) de SAP o usuario credenciales de contraseña de nombre para permitir una comunicación segura entre éste y el servidor SAP. Las credenciales de contraseña de nombre de usuario solo proporcionan autorización para la conexión con el sistema SAP. no proporciona ninguna seguridad en los datos que se intercambian a través de la conexión. No se puede utilizar las credenciales de contraseña del nombre SNC y usuario simultáneamente.  
  
## <a name="sap-secure-network-communications"></a>Comunicaciones de red seguras de SAP  
 Las comunicaciones de red segura (SNC) es una capa de software en la arquitectura del sistema SAP que puede ayudar a proporcionar seguridad de nivel de aplicación en los datos intercambiados entre el cliente de SAP y un servidor de aplicaciones de SAP.  
  
 SNC proporciona las siguientes ventajas:  
  
- SNC tiene como destino la seguridad de nivel de aplicación, to-end. SNC ayuda a proteger todas las comunicaciones entre dos componentes SNC protegida (por ejemplo, entre el SAPgui y un servidor de aplicaciones del sistema SAP).  
  
- Puede implementar las características de seguridad adicionales que el sistema de SAP no proporcionan directamente (por ejemplo, inicio de sesión único o el uso de tarjetas inteligentes para autenticación).  
  
- Puede personalizar la implementación de SNC. Puede usar el producto de seguridad de su elección y elegir los algoritmos que se va a utilizar.  
  
- Puede cambiar el producto de seguridad en cualquier momento sin afectar a las aplicaciones de negocio del sistema SAP.  
  
  Para usar SNC, debe configurar el servidor SAP y el cliente que ejecuta el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
- Configurar las comunicaciones de red seguro (SNC) en el servidor SAP. Consulte la documentación de SAP para obtener instrucciones.  
  
- En el equipo que el cliente SAP archivos DLL y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] instalado, también debe tener el SNC relacionados con los archivos DLL. Para obtener más información acerca de estos archivos DLL, consulte el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] [requisitos previos de software](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md).  
  
- Para configurar el adaptador para que utilice SNC, debe establecer el parámetro UseSnc en el URI de conexión de SAP. Para obtener más información sobre el URI de conexión de SAP, consulte [configurar el URI de conexión para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md). Además, debe establecer el **SncLibrary** y **SncPartnerName** propiedades de enlace. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
## <a name="user-name-password-credentials"></a>Credenciales de contraseña de nombre de usuario  
 Puede proporcionar credenciales de contraseña de nombre de usuario para el adaptador en el URI de conexión. El adaptador usa estas credenciales para autenticar al usuario en el sistema SAP cuando se abre la conexión. Estas credenciales proporcionan un nivel de autorización para la conexión con el sistema SAP. Sin embargo, no proporcionan nivel de transporte o mensaje de autenticación (o autorización) para los datos viajan a través de la red.  
  
 Por este motivo, debe proporcionar un mecanismo de seguridad para ayudar a garantizar niveles adecuados de autorización, autenticación, integridad de los datos para los intercambios de datos entre el adaptador y el sistema SAP y privacidad de los datos.  
  
> [!IMPORTANT]
>  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies el **AcceptCredentialsInUri** enlaza la propiedad. Esta propiedad determina si se permiten las credenciales del sistema SAP en el URI de conexión. De forma predeterminada, **AcceptCredentialsInUri** es false y el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce una excepción si las credenciales se incluyen en el URI. Para obtener más información, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 Un posible mecanismo para ayudar a proporcionar más seguridad a través de la red es el protocolo de seguridad de Internet (IPsec). IPsec es un marco de estándares abiertos para proteger las comunicaciones a través de redes de protocolo de Internet (IP).  
  
 El nombre de usuario y la contraseña se especifican como texto no cifrado en el URI de conexión. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] proporciona una serie de métodos a través del cual forma más segura puede proporcionar estas credenciales.  
  
-   Para obtener información acerca de cómo proporcionar las credenciales de sistema SAP en soluciones de BizTalk de forma más segura, consulte [seguridad con el adaptador de SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).  
  
-   Para obtener información acerca de cómo proporcionar las credenciales de sistema SAP en soluciones de programación de forma más segura, consulte [programación segura con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md).  
  
## <a name="security-concerns-for-inbound-scenarios"></a>Cuestiones de seguridad para escenarios de entrada  
 Cualquier agente de escucha que tiene acceso a un identificador de programa SAP potencialmente puede recibir todos los artefactos SAP (RFC, trfc e idoc) enviados a ese identificador de programa. Si más de un agente de escucha está registrado con el identificador de programa, SAP aleatoriamente asignará los artefactos que llegan a ese identificador de programa a uno de los agentes de escucha. Por lo tanto, debe garantizar que sólo los agentes de escucha que desea recibir mensajes mediante un identificador de programa específico tienen acceso a ese identificador de programa. Además, dado que SAP envía aleatoriamente los artefactos a los agentes de escucha conectados a un identificador de programa, es una práctica recomendada para dedicar los identificadores de programa a un único agente de escucha.  
  
## <a name="see-also"></a>Vea también  
[Procedimientos recomendados para proteger el adaptador de SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[Proteger las aplicaciones SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)