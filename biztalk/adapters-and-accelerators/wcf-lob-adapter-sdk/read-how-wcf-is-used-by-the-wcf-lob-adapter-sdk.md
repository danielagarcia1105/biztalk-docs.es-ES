---
title: Leer el uso de WCF mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 183dd134-7273-4767-bad0-c42ae125985e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb84124213df8cf1bd401ab80db25586f5ca4534
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226100"
---
# <a name="read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk"></a>Leer el uso de WCF mediante el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] amplía la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal y depende de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] en tiempo de ejecución para proporcionar los servicios de mensajes básicos necesarios para exponer la funcionalidad del adaptador e intercambiar información. 
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona un marco para escribir adaptadores, así como la exposición en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]o complementarse con elementos comunes de adaptador como metadatos y la agrupación de conexiones. También consta de las herramientas de soporte técnico para mejorar la experiencia como la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para las aplicaciones .NET y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones y el [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)].  
  
 Es responsabilidad de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] para exponer los servicios para una amplia gama de consumo de aplicaciones, para administrar el flujo de mensajes entre distintos puntos de conexión y para proporcionar un SDK y herramientas para personalizar, configurar y supervisar el flujo de mensajes. Por ejemplo, un desarrollador puede personalizar el comportamiento de un [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extendiendo su canal con controladores de mensajes personalizados.  
  
 La relación entre el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] se muestra en la siguiente ilustración de arquitectura de alto nivel.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/asdk-wcf.gif "ASDK_WCF")  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se basa en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] como una extensión a la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal. Proporciona un modelo de objetos específicos del dominio y simplificada y un conjunto de herramientas para crear adaptadores como personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales. Adaptadores generada mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparecen como personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces.  
  
 La siguiente ilustración muestra el intercambio de mensajes salientes utilizando un enlace determinado adaptador.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/58609452-d09e-4dbd-b470-c92a29977858.gif "58609452-d09e-4dbd-b470-c92a29977858")  
  
 La siguiente ilustración muestra el intercambio de mensajes entrantes mediante un enlace determinado adaptador.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b62d5040-7e40-4edd-ac7b-69768131c51b.gif "b62d5040-7e40-4edd-ac7b-69768131c51b")  
  
 Para obtener más información sobre la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de canales, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).  
  
## <a name="wcf-services-and-the-wcf-lob-adapter-sdk"></a>Servicios WCF y el SDK del adaptador LOB de WCF  
 Al desarrollar una típica [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el primer paso es crear el contrato para el servicio que se comparte con el mundo externo que se describe cómo comunicarse con el servicio. Básicamente, este contrato especifica la colección y estructura de mensajes necesarios para tener acceso a las operaciones que ofrece el servicio.  
  
 Una vez que este contrato se expone como un servicio, el [Service Model Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx) puede utilizarse para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente para usarlo. El contrato proporciona información sobre un conjunto estático de operaciones y mensajes que no deben cambiar. 
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a410af83-ee3b-46d0-9afd-d32970f5ba0a.gif "a410af83-ee3b-46d0-9afd-d32970f5ba0a")  
  
 En cambio, los adaptadores integrados mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporcionan un conjunto dinámico de metadatos sobre la colección de operaciones y los datos que están disponibles dentro de un sistema de línea de negocio. El sistema de línea de negocio a menudo tiene demasiadas operaciones para describir en un contrato y pueden haber nuevas operaciones de agregado para responder a las nuevas necesidades empresariales.  
  
 Por ejemplo, un sistema de línea de negocio puede proporcionar cuenta las operaciones de administración. Después de identificar una necesidad para simplificar la creación de nuevas cuentas de cliente, la compañía actualiza el sistema de línea de negocio para incluir la operación de nuevo. Un adaptador que se generan con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] expone esta operación en los metadatos proporciona a los clientes.  
  
 En tiempo de diseño, la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-adaptador según genera contratos dinámicamente para satisfacer las necesidades del sistema de línea de negocio.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2f4d896a-14d9-43f4-8cdc-f816c5eab46d.gif "2f4d896a-14d9-43f4-8cdc-f816c5eab46d")  
  
 Proporciona el ASDK [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas para el consumidor de adaptador generar contratos dinámicos en tiempo de diseño.  
  
 En tiempo de ejecución, cuando el mensaje fluye en el adaptador que se escriben con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], el adaptador a menudo debe realizar una serie de acciones en el mensaje de recepción. Estas acciones incluyen:  
  
-   Buscar metadatos que pertenecen al mensaje  
  
-   Abrir el mensaje  
  
-   Interpretar el mensaje  
  
-   Llamar a las funciones adecuadas en el sistema de línea de negocio  
  
 En el caso de un [!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)] servicio, mensajes basta con pasan a través sin que se resuelven a través de metadatos.  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de BizTalk para la base de datos de Oracle y el SDK del adaptador LOB de WCF](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)