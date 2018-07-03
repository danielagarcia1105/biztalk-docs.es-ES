---
title: Los metadatos y el modelo de servicio WCF con el adaptador de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4353ce67-f0e8-4f96-b1d9-95deeee7f3e6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfc6e490b2966a0b68d1a9c8669cf4601881743e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008229"
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a>Los metadatos y el modelo de servicio WCF con el adaptador de SQL
En el modelo de servicio WCF, se usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutile.exe) para hacer lo siguiente:  
  
- Generar un contrato de servicio, el contrato de servicio WCF: a través del cual el código puede recibir operaciones desde el adaptador. Esta interfaz .NET representa el contrato de servicio para las operaciones de destino.  
  
- Generar clases de proxy, la clase de cliente WCF: a través del cual el código puede invocar operaciones en el adaptador.  
  
- Anotado clases que representan el apoyo de los contratos de mensaje, contratos de operación y contratos de datos para el contrato de servicio.  
  
  Para obtener ayuda acerca de la estructura de este código generado, vea [comprensión de código de cliente generado](https://msdn.microsoft.com/library/ms733881.aspx). Este tema describe específicamente a código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
  Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF para artefactos de SQL Server ](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)