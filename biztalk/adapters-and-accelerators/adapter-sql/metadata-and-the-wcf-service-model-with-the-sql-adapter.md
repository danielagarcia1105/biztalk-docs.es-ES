---
title: Metadatos y el modelo de servicio de WCF con el adaptador de SQL | Documentos de Microsoft
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
ms.openlocfilehash: c95ed3188c01f0f6d568bd745decd9e601e6ee3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222436"
---
# <a name="metadata-and-the-wcf-service-model-with-the-sql-adapter"></a>Metadatos y el modelo de servicio de WCF con el adaptador de SQL
En el modelo de servicio WCF, use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o el ServiceModel Metadata Utility Tool (svcutile.exe) para hacer lo siguiente:  
  
-   Generar un contrato de servicio, el contrato de servicio WCF: a través del cual el código puede operaciones de recepción del adaptador. Esta interfaz .NET representa el contrato de servicio para las operaciones de destino.  
  
-   Generar clases de proxy, la clase de cliente WCF: a través del cual el código puede invocar las operaciones en el adaptador.  
  
-   Anotado clases que representan los auxiliares contratos de mensaje, los contratos de operación y los contratos de datos para el contrato de servicio.  
  
 Para obtener ayuda acerca de la estructura de este código generado, consulte [comprensión de código de cliente generado](https://msdn.microsoft.com/library/ms733881.aspx). Este tema describe específicamente código que genera svcutil.exe, pero su contenido también es aplicable al código que el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] genera.  
  
 Para obtener información acerca de cómo generar una clase de cliente WCF o el contrato de servicio WCF para las operaciones de destino y las diferencias entre svcutil.exe y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [generar un cliente de WCF o un contrato de servicio WCF de artefactos de SQL Server ](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).  
  
## <a name="see-also"></a>Vea también  
[Desarrollar aplicaciones de SQL con el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)