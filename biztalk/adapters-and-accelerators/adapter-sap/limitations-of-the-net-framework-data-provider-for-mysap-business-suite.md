---
title: Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fd4ad3a57e2b762a53582ceb77eb65f23a535fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a>Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite
Los siguientes se conocen las limitaciones de la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):  
  
-   El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite la conexión a un sistema SAP mediante la conexión de red segura (SNC). Para obtener más información acerca de SNC, consulte [seguridad entre el sistema SAP y el adaptador](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md).
  
-   El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite el `DbType` o `Size` propiedades de la `SAPParameter`. En su lugar, cuando el usuario especifica un valor para el `SAPParameter`, el valor se convierte internamente en un tipo de datos de .NET según la asignación establecida entre los tipos de datos de .NET y SAP.  
  
-   La longitud máxima permitida para los valores de campo de tipos de datos SAP `CURR`, `DEC`, y `QUAN` es 29 dígitos. Aunque SAP proporciona 31 lugares para estos valores de tipo de datos de forma nativa, el tipo de datos decimal de .NET al que se convierten impone un límite de 29 dígitos.  
  
-   Una limitación de la asignación entre el tipo de datos de .NET `Double` y SAP `FLTP` tipo de datos puede producir un error de desbordamiento al leer los datos desde el sistema SAP en el tipo. NET. Aunque el tipo .NET puede representar un número de 64 bits de precisión doble con valores comprendidos entre negativo 1. 79769313486232e308 al positivo 1. 79769313486232e308, SAP `FLTP` tipo analizado por la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no puede superar los 1.8446744073709552E + 19; el límite real para el `FLTP` tipo es el intervalo negativo 1.8446744073709552E + 19 a 19 + 1.8446744073709552E positivo.  
  
-   Debido a problemas con el control de tiempo de espera por la biblioteca de cliente subyacente, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no es compatible con el tiempo de espera de conexión y comando.  
  
-   El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite el comportamiento del comando asincrónico.  
  
-   Cuando se usa con un proyecto de SQL Server Integration Services (SSIS), el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se produce un error al recuperar datos para las columnas que contienen valores con más de 8.000 caracteres. Esto es debido a una restricción de SSIS según los cuales:  
  
    -   No se admiten valores superiores a 4.000 caracteres en la variable SSIS.  
  
    -   No se admiten valores superiores a 4.000 caracteres anchos.  
  
    -   No se admiten valores mayores que 8000 caracteres de byte único.  
  
## <a name="see-also"></a>Vea también  
 [Sobre el proveedor de datos de .NET Framework para mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)