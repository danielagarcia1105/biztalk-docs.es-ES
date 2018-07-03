---
title: Lea cómo WCF usa el SDK de adaptador LOB de WCF | Microsoft Docs
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
ms.openlocfilehash: 8991590d97d70fc0e2090f11f05f8882b0ca3396
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004719"
---
# <a name="read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk"></a>Lea cómo WCF usa el SDK de adaptador LOB de WCF
El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] amplía la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal y depende de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] en tiempo de ejecución para proporcionar los servicios de mensajería básicos necesarios para exponer la funcionalidad del adaptador y la información de exchange. 
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona un marco para escribir adaptadores, exponiéndolos en [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]o complementarse con elementos comunes de adaptador, como metadatos y la agrupación de conexiones. También se compone de las herramientas de soporte técnico para mejorar la experiencia como la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para aplicaciones .NET y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] aplicaciones y el [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)].  
  
 Es responsabilidad de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] para exponer los servicios a una amplia gama de consumo de aplicaciones, para administrar el flujo de mensajes entre distintos puntos de conexión y para proporcionar un SDK y herramientas para personalizar, configurar y supervisar el flujo de mensajes. Por ejemplo, un desarrollador puede personalizar el comportamiento de un [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] extendiendo su canal con controladores de mensajes personalizados.  
  
 La relación entre el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] y [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] se muestra en la siguiente ilustración de arquitectura de alto nivel.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/asdk-wcf.gif "ASDK_WCF")  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] se basa en la parte superior de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] como una extensión a la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal. Proporciona un modelo de objetos específicos de dominio y simplificada y un conjunto de herramientas para crear adaptadores como personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales. Adaptadores generada mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparecen como personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces.  
  
 La siguiente ilustración muestra el intercambio de mensajes de salida mediante un enlace de adaptador dada.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/58609452-d09e-4dbd-b470-c92a29977858.gif "58609452-d09e-4dbd-b470-c92a29977858")  
  
 La siguiente ilustración muestra el intercambio de mensajes entrantes mediante un enlace de adaptador dada.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b62d5040-7e40-4edd-ac7b-69768131c51b.gif "b62d5040-7e40-4edd-ac7b-69768131c51b")  
  
 Para obtener más información sobre la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de canales, vea [información general del modelo de canal](https://msdn.microsoft.com/library/ms729840.aspx).  
  
## <a name="wcf-services-and-the-wcf-lob-adapter-sdk"></a>Servicios WCF y el SDK del adaptador LOB de WCF  
 Al desarrollar una típica [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio, el primer paso es crear el contrato de servicio que se comparte con el exterior que describa cómo comunicarse con el servicio. Este contrato especifica esencialmente la colección y la estructura de mensajes necesarios para tener acceso a las operaciones que ofrece el servicio.  
  
 Una vez que este contrato se expone como un servicio, el [Service Model Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx) puede usarse para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente lo consuman. El contrato proporciona información sobre un conjunto estático de operaciones y mensajes que no deben cambiar. 
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a410af83-ee3b-46d0-9afd-d32970f5ba0a.gif "a410af83-ee3b-46d0-9AFD-d32970f5ba0a")  
  
 En cambio, los adaptadores integrados mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporcionan un conjunto dinámico de los metadatos acerca de la colección de operaciones y los datos que están disponibles dentro de un sistema de línea de negocio. El sistema de línea de negocio a menudo tiene demasiadas operaciones que se describirá en un contrato y es posible que haya nuevas operaciones de agregado para responder a las nuevas necesidades empresariales.  
  
 Por ejemplo, un sistema de línea de negocio puede proporcionar cuenta las operaciones de administración. Después de identificar la necesidad de optimizar la creación de nuevas cuentas de cliente, la compañía actualiza el sistema de línea de negocio para incluir la operación de nuevo. Un adaptador creado mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] expone esta operación en los metadatos proporciona a los clientes.  
  
 En tiempo de diseño, la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]-en función de adaptador genera contratos dinámicamente para satisfacer las necesidades del sistema de línea de negocio.  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/2f4d896a-14d9-43f4-8cdc-f816c5eab46d.gif "2f4d896a-14d9-43f4-8cdc-f816c5eab46d")  
  
 Proporciona el ASDK [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] y [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] herramientas para el consumidor del adaptador generar contratos dinámicos en tiempo de diseño.  
  
 En tiempo de ejecución, cuando el mensaje fluye hacia el adaptador escrito utilizando el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], el adaptador a menudo debe realizar una serie de acciones en el mensaje de recepción. Estas acciones incluyen:  
  
- Buscar metadatos que pertenecen al mensaje  
  
- Abrir el mensaje  
  
- Interpretar el mensaje  
  
- Llamar a las funciones correspondientes en el sistema de línea de negocio  
  
  En el caso de un [!INCLUDE[nextref_btsWinCommFoundation_md](../../includes/nextref-btswincommfoundation-md.md)] servicio, los mensajes simplemente pasan a través sin que se resuelve a través de metadatos.  
  
## <a name="see-also"></a>Vea también  
 [Adaptador de BizTalk para Oracle Database y el SDK del adaptador LOB de WCF](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)