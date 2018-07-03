---
title: Comprender el adaptador de BizTalk para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 709833ecec71a98e0e09d2cd660b68bf5b647d8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985613"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a>Comprender el adaptador de BizTalk para mySAP Business Suite
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
- **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.  
  
- **Variar las opciones de programación**. Los adaptadores ofrecen una selección de modelo que incluye el modelo de canal de Windows Communication Foundation (WCF), modelo de servicio WCF, servicios web, ADO.NET o BizTalk admitida modelos de programación.  
  
- **Uniforme de experiencia en LOB**. Los adaptadores de estandarizan sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y, por tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
  Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF. El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office. El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).
  
  Para realizar operaciones en un sistema SAP, los clientes del adaptador deben tener acceso al relevantes llamadas a funciones remotas (RFC), Interfaces de programación de aplicaciones empresariales (BAPI) y los IDOC (o documentos intermedios). Un sistema SAP R/3 expone RFC, BAPI y los IDOC para integración empresarial. Las solicitudes de cambio son módulos de una función remota que implementan la lógica empresarial específica. Esta lógica se puede invocar desde una aplicación externa, como BizTalk Server o una aplicación. NET. BAPI es interfaces de método a los objetos de negocio SAP, que a su vez se exponen a través de interfaces RFC estándares. IDOC son un mecanismo para abstraer la capa de comunicación de electronic data interchange (EDI) para la comunicación entre los sistemas que no sean de SAP y SAP. Con [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], puede tener acceso a la RFC, BAPI, y exponen un sistema SAP IDOC.  
  
  El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también incluye [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], que proporciona una interfaz ADO al sistema SAP.  
  
  En esta sección se enumera las características para la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [Características clave del adaptador de SAP](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [Limitaciones del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [Acerca del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a>Vea también  
[Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)