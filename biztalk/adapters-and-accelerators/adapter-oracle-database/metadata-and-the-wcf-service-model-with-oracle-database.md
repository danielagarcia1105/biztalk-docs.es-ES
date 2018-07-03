---
title: Modelo de base de datos de Oracle de servicio de WCF y metadatos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service model, metadata
- WCF client class
- WCF service contract
ms.assetid: b55cf4ed-c41a-4986-bbaf-88e80c32b01f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3b1c3eed2ab71282a50ccbb6709601aa69ca733
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973301"
---
# <a name="metadata-and-the-wcf-service-model-with-oracle-database"></a>Los metadatos y el modelo de servicio WCF con la base de datos de Oracle
En el modelo de servicio WCF, se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].o el ServiceModel Metadata Utility Tool (svcutile.exe) para generar clases de proxy a través del cual el código puede:  
  
- Invocar operaciones en el adaptador (una clase de cliente WCF)  
  
- Operaciones de recepción del adaptador (un contrato de servicio WCF)  
  
  Estas herramientas generan clases de .NET que representan un contrato de servicio para las operaciones de destino (así como el apoyo de los contratos de mensaje, los contratos de operación y los contratos de datos) de los metadatos expuestos por el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener ayuda acerca de la estructura de este genera código, vea "Descripción genera código de cliente" en [ http://go.microsoft.com/fwlink/?LinkId=98365 ](http://go.microsoft.com/fwlink/?LinkId=98365). Este tema describe específicamente a código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera. Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para la base de datos de Oracle Artefactos de la solución](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)