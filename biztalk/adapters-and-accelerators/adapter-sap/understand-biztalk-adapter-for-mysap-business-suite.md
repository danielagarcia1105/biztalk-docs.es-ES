---
title: Comprender el adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d04c435208e316c343ac7b307943e0f91b8af7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a>Comprender el adaptador de BizTalk para mySAP Business Suite
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
-   **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño común y fácil de usar para la exploración, búsqueda y recuperación de metadatos de artefactos de LOB.  
  
-   **Opciones de programación de variados**. Los adaptadores proporcionan una opción de modelo que incluye el modelo de canal de Windows Communication Foundation (WCF), modelo de servicio WCF, ADO.NET, los servicios web o BizTalk admitida modelos de programación.  
  
-   **Uniformes experiencia a través de LOB**. Los adaptadores estandarización sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y, por tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
 Como se mencionó, los adaptadores se generan en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones cliente como el servidor BizTalk Server y Microsoft Office. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Alinee la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación. La documentación se instala junto con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], normalmente en \<unidad de instalación\>: \Program archivos\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.  
  
 Para llevar a cabo operaciones en un sistema SAP, los clientes de adaptador deben tener acceso al relevante llamadas a funciones remotas (RFC), Interfaces de programación de aplicaciones empresariales (BAPI) e IDOC (o documentos intermedios). Un sistema SAP R/3 expone RFC y BAPI, IDOC para la integración de negocios. Las solicitudes de cambio son módulos de función remota que implementan la lógica empresarial específica. Esta lógica se puede invocar desde una aplicación externa como BizTalk Server o una aplicación. NET. BAPI es interfaces de método para objetos de negocios SAP, que a su vez se exponen a través de interfaces RFC estándar. IDOC es un mecanismo para resumir el nivel de comunicación de datos electrónicos interchange (EDI) para la comunicación entre sistemas ajenos a SAP y SAP. Con [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], puede tener acceso a los documentos de RFC, BAPI, y expone un sistema SAP IDOC.  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también incluye [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], que proporciona una interfaz de ADO al sistema SAP.  
  
 En esta sección se enumera las características de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [Características clave en el adaptador SAP](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [Limitaciones del adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [Acerca del proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a>Vea también  
[Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)