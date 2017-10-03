---
title: "Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture of SAP adapter
- adapters, architecture
ms.assetid: 1b45edb0-2476-427b-b6cd-41e38ed815e0
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d571cdd3beea2bc9a57ec7ad15f865e7ef51e53a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite"></a>Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] implementa un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado, que contiene un elemento de enlace de transporte personalizado único que permite la comunicación con un sistema SAP. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ajustada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] en tiempo de ejecución y se expone a las aplicaciones a través de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se comunica con el sistema SAP a través de la versión de 64 bits o de 32 bits del SDK de RFC de Unicode de SAP (librfc32u.dll). 

En la siguiente ilustración muestra la arquitectura de-to-end de soluciones que se desarrollan usando la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
 ![Final SAP &#45; a &#45; Finalizar la arquitectura](../../adapters-and-accelerators/adapter-sap/media/9ba0c31f-90df-444d-8192-42743c893d51.gif "9ba0c31f-90df-444d-8192-42743c893d51")  
  
## <a name="consuming-the-adapter"></a>Consumir el adaptador  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone el sistema SAP como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio a las aplicaciones cliente. Las aplicaciones de cliente intercambian mensajes SOAP con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales que se va a realizar operaciones como obtener acceso a datos en el sistema SAP. La ilustración anterior muestra cuatro maneras en que la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] puede ser utilizado.  
  
-   A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales de aplicación que realiza operaciones en el sistema SAP mediante el uso de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal para intercambiar SOAP mensajes directamente con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información sobre cómo desarrollar soluciones para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] utilizando [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] programación del modelo de canales, vea [desarrollar aplicaciones mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md).  
  
-   A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación de modelo que se llama a métodos de servicio un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente para realizar operaciones en el sistema SAP. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente modela las operaciones expuestas por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como métodos. NET. Puede usar el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] o la herramienta svcutil.exe para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] clase de cliente de los metadatos expuestos por la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Para obtener más información acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] programación del modelo de servicio y la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [desarrollar aplicaciones mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md).  
  
-   A través de un puerto de BizTalk que está configurado para utilizar el adaptador personalizado de WCF de BizTalk con el enlace de SAP configurado como el enlace para el tipo de transporte de WCF-Custom en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación. El adaptador personalizado de WCF de BizTalk permite la comunicación entre un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicación y un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio. El adaptador personalizado de WCF de BizTalk admite personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] tipo, lo que permite configurar cualquiera de transporte de enlaces a través de su WCF-Custom [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlace expuesta al sistema de configuración como el enlace utilizado por el adaptador de BizTalk WCF-Custom. Para obtener más información sobre cómo usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] soluciones, consulte [BizTalk desarrollar aplicaciones](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md). Las transacciones de BizTalk son compatibles con el elemento de enlace de canal de BizTalk en capas que se puede cargar estableciendo una propiedad de enlace en el enlace de SAP.  
  
-   A través de un servicio Web hospedado en IIS. En este escenario, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se expone a través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] proxy del servicio, que se hospeda en IIS mediante el uso de uno de los estándar [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces HTTP.  
  
-   A través de la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se ejecuta en la parte superior de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y proporciona una interfaz ADO.NET a un sistema SAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y la biblioteca de RFC de SAP siempre se hospedan en proceso con la aplicación o servicio que utiliza el adaptador.  
  
## <a name="sap-adapter-and-wcf"></a>WCF y el adaptador SAP  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]presenta un modelo de programación basado en el intercambio de mensajes SOAP a través de canales entre clientes y servicios. Estos mensajes se envían entre los extremos expuestos por un cliente y un servicio de comunicación.  
  
 Un extremo está compuesto por un *dirección de extremo* que especifica la ubicación en la que se reciben mensajes, un *enlace* que especifica los protocolos de comunicación que se usan para intercambiar mensajes y un *contrato* que especifica los tipos de operaciones y los datos expuestos por el punto de conexión. Un enlace está compuesto de uno o más elementos de enlace que se apilan uno sobre otro para definir cómo se intercambian los mensajes con el punto de conexión.  
  
 Como mínimo, un enlace debe especificar el transporte y codificación utilizados para intercambiar mensajes con el punto de conexión. Intercambio de mensajes entre los puntos de conexión se produce en una pila de canales que se compone de uno o más canales. Cada canal es una implementación concreta de uno de los elementos de enlace en el enlace configurado para el extremo.  
  
El [documentación de WCF](http://go.microsoft.com/fwlink/?LinkID=196850) incluye más detalles acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]y el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de programación.  
  
 El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] expone un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlace personalizado, el enlace de SAP (**Microsoft.Adapters.SAP.SAPBinding**). De forma predeterminada, este enlace contiene un elemento de enlace de transporte personalizado único, el elemento de enlace del adaptador de SAP (**Microsoft.Adapters.SAP.SAPAdapter**), lo que permite las operaciones en un sistema SAP. Cuando se usa el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede establecer la **EnableBizTalkCompatibilityMode** enlace de propiedad que se va a cargar un elemento de enlace personalizado, el BizTalk superpuesto canal de elemento de enlace en la parte superior del enlace del adaptador SAP Elemento. El elemento de enlace de canal de BizTalk en capas se implementa internamente el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y no se expone fuera el enlace de SAP.  
  
 **Microsoft.Adapters.SAP.SAPBinding** (el enlace de SAP) y **Microsoft.Adapters.SAP.SAPAdapter** (la SAP adaptador de elemento de enlace) son las clases públicas y también se exponen al sistema de configuración. Dado que el elemento de enlace del adaptador de SAP se exponen públicamente, puede crear su propio personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces capaces de ampliar la funcionalidad de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. Por ejemplo, podría implementar un enlace personalizado para admitir Enterprise Single Sign-On (SSO) en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canal o [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio solución de programación de modelo, para operaciones de agregado de la base de datos en una sola operación multifunción, o para realizar la transformación de esquema entre las operaciones que se implementa una aplicación personalizada y operaciones en el sistema SAP.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y se ejecuta en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una infraestructura de marco de trabajo y herramientas de software que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] aprovecha para proporcionar un amplio conjunto de características para los usuarios y los clientes de adaptador.  

## <a name="sap-adapter-and-the-wcf-lob-adapter-sdk"></a>Adaptador SAP y el SDK de adaptador LOB de WCF
El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] implementa un conjunto de componentes principales que aprovechan la funcionalidad proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporcionar conectividad con el sistema SAP a través de la biblioteca del SDK de RFC de SAP Unicode (librfc32u.dll).  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] actúa como la capa de software a través del cual el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] interactúa con [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)], y RFC SDK actúa como la capa a través del cual el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] interfaces con el sistema SAP. La siguiente ilustración muestra las relaciones entre los componentes internos de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y entre estos componentes y RFC SDK.  
  
 ![La relación de componentes de adaptador internos](../../adapters-and-accelerators/adapter-sap/media/10f97b95-4e82-4592-ba07-0f58478305c2.gif "10f97b95-4e82-4592-ba07-0f58478305c2")  
  
## <a name="connection-to-the-sap-system"></a>Conexión con el sistema SAP  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se conecta con el sistema SAP a través de la biblioteca del SDK de RFC de SAP Unicode (librfc32u.dll). El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con los 32 bits y las versiones de 64 bits del SDK de RFC de SAP. El SDK de RFC de SAP permite a los programas externos llamar a funciones ABAP en un sistema SAP.  
  
 Establecer una conexión a un sistema SAP proporcionando un URI de conexión para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es compatible con los siguientes tipos de conexiones a un sistema SAP:  
  
-   Una aplicación basada en host: conexión (A), en el que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se conecta directamente a un servidor de aplicaciones de SAP.  
  
-   Una conexión (B), en la que equilibrar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se conecta a un servidor de mensajería de SAP.  
  
-   Una destino conexión (D), en el que se especifica la conexión al sistema SAP mediante un destino en el archivo de configuración saprfc.ini. A, B y R se admiten conexiones de tipo.  
  
-   Una conexión de agente de escucha (R), en el que el adaptador recibe las solicitudes de cambio, tRFC e IDOC a través de un destino RFC en el sistema SAP que se especifica mediante un host de agente de escucha, un servicio de puerta de enlace de agente de escucha y un identificador de programa del agente de escucha, ya sea directamente en el URI de conexión o por un valor de R según destino en el archivo de configuración saprfc.ini.  
  
 Para obtener más información acerca del archivo saprfc.ini, vea "el SAPRFC. INI"en la [documentación de SAP](https://help.sap.com/doc/PRODUCTION/saphelp_nwpi711/7.1.1/en-US/48/c4168eca64581de10000000a42189c/frameset.htm).  
  
 Para obtener más información acerca de cómo los [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] se conecta a un sistema SAP, consulte [crear una conexión con el sistema SAP](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).  
  
## <a name="see-also"></a>Vea también  
 [Comprender el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)