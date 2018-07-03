---
title: Comprender el adaptador de BizTalk para aplicaciones Siebel eBusiness | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 788db9ba048141256cfaa3cc5017fa48bd6ec7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999237"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a>Comprender el adaptador de BizTalk para aplicaciones Siebel eBusiness
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
- **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.  
  
- **Variar las opciones de programación**. Los adaptadores proporcionan un modelo de programación incluyen Windows Communication Foundation (WCF) que prefiera modelo del canal, WCF del servicio servicios Web de model, ADO.NET, o modelos admitidos de BizTalk.  
  
- **Uniforme de experiencia en LOB**. Los adaptadores de estandarizan sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y, por tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
  Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF. El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office. El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).
  
  Para realizar operaciones en un sistema de Siebel, los clientes del adaptador deben tener acceso a servicios empresariales expuestos por el sistema Siebel. Una aplicación Siebel expone los datos como objetos de negocios y componentes empresariales. Un Siebel *componente empresarial* es una entidad lógica que asocia las columnas de una o varias tablas en una única estructura. Un Siebel *objeto comercial* implementa un modelo de negocio al unir un conjunto de componentes empresariales interrelacionados. Con la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)], los clientes del adaptador pueden exponer los objetos de negocios de Siebel y componentes empresariales.  
  
  El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] también incluye el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]). El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona una interfaz de ADO a un sistema de Siebel mediante la extensión de las interfaces ADO.NET.  
  
  En esta sección se describe las características de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Características clave del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [Limitaciones del adaptador de BizTalk para las aplicaciones de negocio electrónico de Siebel](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Acerca del proveedor de datos para Siebel](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)