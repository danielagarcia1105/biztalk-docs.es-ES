---
title: Modelo con SAP del servicio WCF y metadatos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1900cf66-a0d0-46f4-896b-7f6de3b51875
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f06cd33c0776df70e5ff2554d355915908012abb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="metadata-and-the-wcf-service-model-with-sap"></a>Metadatos y el modelo de servicio WCF con SAP
En el modelo de servicio WCF, use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]. o bien el ServiceModel Metadata Utility Tool (svcutile.exe) para generar clases de proxy a través del cual el código puede:  
  
-   Invocar las operaciones en el adaptador (una clase de cliente WCF)  
  
-   Operaciones de recepción del adaptador (un contrato de servicio WCF)  
  
 Estas herramientas generan clases de .NET que representan un contrato de servicio para las operaciones de destino (así como el apoyo de los contratos de mensaje, contratos de operación y contratos de datos) de los metadatos expuestos por la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]. Para obtener ayuda acerca de la estructura de este código generado, consulte [comprensión de código de cliente generado](https://msdn.microsoft.com/library/ms733881.aspx). Este tema describe específicamente código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera. Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF (interfaz) para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente WCF o un contrato de servicio WCF para SAP artefactos de la solución](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SAP mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)