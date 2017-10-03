---
title: "Introducción a la arquitectura del adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture of Siebel adapter
- Siebel COM Data Control
- adapters, architecture
ms.assetid: b048937f-207b-4c64-8837-7bfeecedfa03
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d78bf2104d5383f3c8aa34984a5781fa8f4dbfb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>Introducción a la arquitectura del adaptador de BizTalk para Siebel eBusiness Applications
Describe la arquitectura de soluciones de extremo a extremo que usan el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para operar en un sistema Siebel y también la arquitectura interna de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
 Una descripción de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] arquitectura le permitirá:  
  
-   Comprender la relación entre el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].  
  
-   Comprender los límites de seguridad, por lo que puede mejorar la seguridad de datos en la solución.  
  
-   Comprender el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] propiedades de enlace.  
  
-   Solucionar problemas de instalación.  

## <a name="adapter-architecture-overview"></a>Información general de arquitectura de adaptador
El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y se ejecuta en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tiempo de ejecución. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una infraestructura de marco de trabajo y herramientas de software que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] emplea para proporcionar un amplio conjunto de características para los usuarios y los clientes de adaptador.  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un enlace personalizado de WCF. Este enlace contiene un elemento de enlace de transporte personalizado único que permite la comunicación con un sistema Siebel. El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] ajustada por el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tiempo de ejecución y se expone a las aplicaciones a través de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal.  
  
## <a name="siebel-com-data-control"></a>Control de datos de Siebel COM  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se conecta con el sistema Siebel a través de la biblioteca de controles de datos de Siebel COM (sstchca.dll) y la biblioteca Microsoft.Adapters.Siebel.SiebelBusinessObjectInterface.dll. El Control de datos de Siebel COM es un componente de cliente Web de Siebel. 
  
 Las interfaces de Control de datos de Siebel COM permiten que un cliente externo como el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para conectarse y comunicarse con un administrador de objetos de aplicación de Siebel en un servidor de empresa de Siebel. El Administrador de objetos de Siebel y Siebel Enterprise Server, así como otros parámetros de conexión se especifican en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] URI de conexión. Para obtener más información sobre el URI de conexión, consulte [cree el URI de conexión del sistema Siebel](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).  
  
 En la siguiente ilustración muestra la arquitectura de-to-end de soluciones que se desarrollan usando la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
 ![Extremo de Siebel &#45; a &#45; Finalizar la arquitectura](../../adapters-and-accelerators/adapter-siebel/media/1ae1955e-b7d7-44a0-80c1-1e835edab356.gif "1ae1955e-b7d7-44a0-80c1-1e835edab356")  
  
## <a name="consuming-the-adapter"></a>Consumir el adaptador  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone el sistema Siebel como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio a las aplicaciones cliente. Para realizar operaciones y obtener acceso a datos en el sistema Siebel, las aplicaciones de cliente intercambian mensajes SOAP con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales. La ilustración anterior muestra cuatro maneras en que la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede ser utilizado.  
  
-   A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]modelo de solicitud de canal. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación de modelo del canal realiza operaciones en el sistema Siebel usando la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal para intercambiar SOAP mensajes directamente con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para obtener más información sobre cómo desarrollar soluciones para el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] mediante el uso de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de canales, vea [aplicaciones desarrollar SQL mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).  
  
-   A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio llama a métodos en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente para realizar operaciones en el sistema Siebel. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente modela las operaciones expuestas por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] como métodos. NET. Puede usar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] o el ServiceModel Metadata Utility Tool (svcutil.exe) para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] clase de cliente de los metadatos expuestos por la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Para obtener más información sobre la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio y la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [aplicaciones desarrollar SQL utilizando el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md).  
  
-   A través de un BizTalk ubicación de recepción o puerto de envío que está configurado para usar el adaptador de Microsoft BizTalk WCF-Custom. El adaptador WCF-Custom habilita el uso de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] características de extensibilidad. Mediante el adaptador de WCF-Custom puede seleccionar y configurar el enlace de Siebel y el comportamiento de la ubicación de recepción o puerto de envío. Las transacciones de BizTalk son compatibles con el BizTalk superpuesto canal de elemento de enlace que se pueden cargar estableciendo una propiedad de enlace en el enlace de Siebel. Para obtener más información sobre cómo usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] soluciones, consulte [desarrollar las aplicaciones de BizTalk](../../core/develop-your-biztalk-applications.md).
  
-   A través de un servicio Web hospedado en IIS. En este escenario, un proxy de servicio WCF generado mediante el adaptador se hospeda en IIS mediante el enlace de Http de WCF estándar. Esto expone el contrato de servicio como un servicio Web a los usuarios externos. IIS aloja automáticamente el adaptador en tiempo de ejecución, que, a su vez, se comunica con el sistema Siebel.  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y el Control de datos de Siebel COM biblioteca siempre están hospedados en proceso con la aplicación o servicio que utiliza el adaptador.  
  
## <a name="siebel-adapter-and-wcf"></a>Adaptador de Siebel y WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]presenta un modelo de programación basado en el intercambio de mensajes SOAP a través de canales entre clientes y servicios. Estos mensajes se envían entre los extremos expuestos por un cliente y un servicio de comunicación. Un punto de conexión consta de:  
  
-   Un *dirección de extremo*, que especifica la ubicación a la que se reciben los mensajes.  
  
-   A *enlace*, que especifica los protocolos de comunicación que se usan para intercambiar mensajes.  
  
-   A *contrato*, que especifica los tipos de operaciones y los datos expuestos por el punto de conexión.  
  
 Un enlace está compuesto de uno o más elementos de enlace que se apilan uno sobre otro para definir cómo se intercambian los mensajes con el punto de conexión. Como mínimo, un enlace debe especificar el transporte y codificación que se usan para intercambiar mensajes con el punto de conexión. Intercambio de mensajes entre los puntos de conexión se produce en una pila de canales que se compone de uno o más canales. Cada canal es una implementación concreta de uno de los elementos de enlace en el enlace que está configurado para el extremo. El [documentación de WCF](http://go.microsoft.com/fwlink/?LinkID=196850) incluye más detalles acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]y el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de programación.  
  
 El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] expone un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlace personalizado, el enlace de Siebel (**Microsoft.Adapters.Siebel.SiebelBinding**). De forma predeterminada, este enlace contiene un elemento de enlace de transporte personalizado único, el elemento de enlace del adaptador de Siebel (**Microsoft.Adapters.Siebel.SiebelAdapter**), lo que permite las operaciones en un sistema Siebel. Cuando se usa el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], puede establecer la **EnableBizTalkCompatibilityMode** propiedad para cargar un elemento de enlace personalizado de enlace: el elemento de enlace de canal en capas de BizTalk, sobre el adaptador de Siebel Elemento de enlace. El elemento de enlace de canal de BizTalk en capas se implementa internamente el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y no se expone fuera el enlace de Siebel.  
  
 **Microsoft.Adapters.Siebel.SiebelBinding** (el enlace de Siebel) y **Microsoft.Adapters.Siebel.SiebelAdapter** (la Siebel adaptador de elemento de enlace) son las clases públicas y también se exponen a la configuración sistema. Dado que el elemento de enlace del adaptador de Siebel se exponen públicamente, puede crear su propio personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces capaces de ampliar la funcionalidad de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]. Por ejemplo, podría implementar un enlace personalizado para admitir el inicio de sesión único empresarial (SSO) en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] de canal o programación del modelo de servicio. Las razones para esto son en:  
  
-   Operaciones de agregado de la base de datos en una sola operación multifunción.  
  
-   Realizar la transformación de esquema entre las operaciones que se implementan mediante una aplicación personalizada y operaciones en el sistema Siebel.  

## <a name="siebel-adapter-and-wcf-lob-adapter-sdk"></a>Adaptador de Siebel y SDK de adaptador LOB de WCF

El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] implementa un conjunto de componentes principales que:  
  
-   Aprovecha la funcionalidad proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].  
  
-   Proporcionar conectividad con el sistema Siebel a través de la biblioteca de controles de datos de Siebel COM (sstchca.dll).  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es la capa de software a través del cual el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] interfaces con WCF; Control de datos de Siebel COM es la capa a través del cual el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] interfaces con el sistema Siebel. La siguiente ilustración muestra las relaciones entre los componentes internos de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y entre estos componentes y el Control de datos de COM de Siebel.  
  
 ![Arquitectura interna del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/media/e4accea7-86b2-4f2a-937a-edff7e1100ec.gif "e4accea7-86b2-4f2a-937a-edff7e1100ec")
   
## <a name="see-also"></a>Vea también  
 [Proteger las aplicaciones de Siebel](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
 [Comprender el adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)