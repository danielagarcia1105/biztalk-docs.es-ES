---
title: Comprender el adaptador de BizTalk para aplicaciones Siebel eBusiness | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ad8aecf0faa0a9a0117feaf91e5fa91203fa63f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a>Comprender el adaptador de BizTalk para Siebel eBusiness Applications
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
-   **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño común y fácil de usar para la exploración, búsqueda y recuperación de metadatos de artefactos de LOB.  
  
-   **Opciones de programación de variados**. Los adaptadores proporcionan una opción de modelo de programación incluyen Windows Communication Foundation (WCF) servicios Web ADO.NET, modelo de servicio de modelo del canal, WCF o BizTalk admite modelos.  
  
-   **Uniformes experiencia a través de LOB**. Los adaptadores estandarización sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y, por tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
 Como se mencionó, los adaptadores se generan en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones cliente como el servidor BizTalk Server y Microsoft Office. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Alinee la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación. La documentación se instala junto con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], normalmente en \<unidad de instalación >: \Program archivos\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.  
  
 Para realizar operaciones en un sistema Siebel, los clientes de adaptador deben tener acceso a los servicios de negocios expuestos por el sistema Siebel. Una aplicación Siebel expone los datos como objetos de negocios y componentes empresariales. Un Siebel *componente empresarial* es una entidad lógica que asocia las columnas de una o más tablas en una única estructura. Un Siebel *objeto comercial* implementa un modelo de negocio al unir un conjunto de componentes empresariales interrelacionados. Con la [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)], los clientes de adaptador pueden exponer los objetos de negocios de Siebel y componentes empresariales.  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] también incluye el [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]). El [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] proporciona una interfaz de ADO a un sistema Siebel extendiendo las interfaces ADO.NET.  
  
 En esta sección se describe las características de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] y [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general del adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Características clave en el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [Limitaciones del adaptador de BizTalk para Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [Acerca del proveedor de datos para Siebel](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)