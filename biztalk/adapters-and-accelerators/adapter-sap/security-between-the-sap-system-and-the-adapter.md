---
title: Seguridad entre el sistema SAP y el adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Secure Network Communications
- SNC
- security, user name password credentials
- security, for inbound scenarios
- security considerations, between SAP system and adapter
- user name password credentials
ms.assetid: fa21df0b-a364-4a52-8c38-49c5ee6267cc
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1c0e37662b9c554d05b73ecf234da4b2ee547fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-between-the-sap-system-and-the-adapter"></a>Seguridad entre el sistema SAP y el adaptador
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] admite credenciales de contraseña de nombre de las comunicaciones de red segura (SNC) de SAP o usuario para ayudar a una comunicación segura entre él y el servidor SAP. Las credenciales de contraseña de nombre de usuario sólo proporcionan autorización para la conexión con el sistema SAP. no proporciona ninguna seguridad en los datos que se intercambian a través de la conexión. No puede usar las credenciales de contraseña de nombre SNC tanto del usuario al mismo tiempo.  
  
## <a name="sap-secure-network-communications"></a>Comunicaciones de red seguras de SAP  
 Las comunicaciones de red segura (SNC) es una capa de software en la arquitectura del sistema SAP que puede ayudar a proporcionar seguridad de nivel de aplicación en los datos intercambiados entre el cliente SAP y un servidor de aplicaciones de SAP.  
  
 SNC proporciona las siguientes ventajas:  
  
-   SNC tiene como destino la seguridad de nivel de aplicación, to-end. SNC ayuda a proteger todas las comunicaciones entre dos componentes SNC protegido (por ejemplo, entre el SAPgui y un servidor de aplicaciones del sistema SAP).  
  
-   Puede implementar las características de seguridad adicionales que el sistema SAP no proporciona directamente (por ejemplo, el inicio de sesión único o el uso de tarjetas inteligentes para la autenticación).  
  
-   Puede personalizar su implementación SNC. Puede usar el producto de seguridad de su elección y elegir los algoritmos que se va a utilizar.  
  
-   Puede cambiar el producto de seguridad en cualquier momento sin que afecte a las aplicaciones de negocio del sistema SAP.  
  
 Para usar SNC, debe configurar el servidor SAP y el cliente que ejecuta la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
-   Configurar las comunicaciones de red seguro (SNC) en el servidor SAP. Consulte la documentación de SAP para obtener instrucciones.  
  
-   En el equipo que el cliente SAP archivos DLL y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] instalado, también debe tener el SNC relacionados con archivos DLL. Para obtener más información acerca de estos archivos DLL, consulte la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] [requisitos previos de software](../../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md).  
  
-   Para configurar el adaptador para que utilice SNC, debe establecer el parámetro UseSnc en el URI de conexión de SAP. Para obtener más información sobre el URI de conexión de SAP, consulte [configurar el URI de conexión para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md). Además, debe establecer el **SncLibrary** y **SncPartnerName** propiedades de enlace. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
## <a name="user-name-password-credentials"></a>Credenciales de contraseña de nombre de usuario  
 Puede proporcionar credenciales de contraseña de nombre de usuario para el adaptador en el URI de conexión. El adaptador utiliza estas credenciales para autenticar al usuario en el sistema SAP al abrirse la conexión. Estas credenciales proporcionan un nivel de autorización para la conexión con el sistema SAP. Sin embargo, no proporcionan nivel de transporte o mensaje de autenticación (o autorización) para los datos viajan a través de la red.  
  
 Por esta razón, debe proporcionar un mecanismo de seguridad para ayudar a garantizar niveles adecuados de autorización, autenticación, privacidad de los datos e integridad de datos para los intercambios de datos entre el adaptador y el sistema SAP.  
  
> [!IMPORTANT]
>  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies la **AcceptCredentialsInUri** propiedad de enlace. Esta propiedad determina si se permiten las credenciales del sistema SAP en el URI de conexión. De forma predeterminada, **AcceptCredentialsInUri** es false y el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce una excepción si las credenciales se incluyen en el URI. Para obtener más información, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).  
  
 Un mecanismo posibles para ayudar a proporcionar mayor seguridad a través de la red es el protocolo de seguridad de Internet (IPsec). IPsec es un marco de estándares abiertos para proteger las comunicaciones a través de redes de protocolo de Internet (IP).  
  
 El nombre de usuario y la contraseña se especifican como texto no cifrado en el URI de conexión. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] proporciona una serie de métodos a través del cual se pueden proporcionar estas credenciales forma más segura.  
  
-   Para obtener información sobre cómo proporcionar las credenciales de sistema SAP en soluciones de BizTalk de forma más segura, consulte [seguridad con el adaptador SAP y BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).  
  
-   Para obtener información sobre cómo proporcionar las credenciales de sistema SAP en las soluciones de programación de forma más segura, consulte [programación segura con el adaptador SAP](../../adapters-and-accelerators/adapter-sap/secure-programming-with-the-sap-adapter.md).  
  
## <a name="security-concerns-for-inbound-scenarios"></a>Cuestiones de seguridad para escenarios de entrada  
 Cualquier agente de escucha que tiene acceso a un identificador de programa SAP potencialmente puede recibir todos los artefactos SAP (RFC, IDOC y tRFCs) enviados a ese identificador de programa. Si más de un agente de escucha está registrado con el identificador de programa, SAP aleatoriamente asignará los artefactos que llegan a ese identificador de programa a uno de los agentes de escucha. Por lo tanto, debe garantizar que sólo los agentes de escucha que desea recibir mensajes mediante un identificador de programa específico tengan acceso a ese identificador de programa. Además, dado que SAP aleatoriamente envía los artefactos a los agentes de escucha que se adjunta a un identificador de programa, es recomendable dedicar identificadores de programa a un agente de escucha único.  
  
## <a name="see-also"></a>Vea también  
[Prácticas recomendadas para proteger el adaptador SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
[Proteger las aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)