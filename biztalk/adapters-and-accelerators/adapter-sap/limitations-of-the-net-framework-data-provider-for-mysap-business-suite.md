---
title: Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9efcf7fb18471c92c504e08df43482fbc64064d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999821"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="39057-102">Limitaciones del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="39057-102">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="39057-103">Lo siguiente es limitaciones conocida de la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="39057-103">The following are known limitations of the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]):</span></span>  
  
- <span data-ttu-id="39057-104">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite la conexión a un sistema SAP mediante la conexión de red seguro (SNC).</span><span class="sxs-lookup"><span data-stu-id="39057-104">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support connecting to an SAP system using Secure Network Connection (SNC).</span></span> <span data-ttu-id="39057-105">Para obtener más información acerca de SNC, consulte [seguridad entre el sistema SAP y el adaptador](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="39057-105">For more information about SNC, see [Security between the SAP system and the adapter](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md).</span></span>
  
- <span data-ttu-id="39057-106">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite el `DbType` o `Size` propiedades de la `SAPParameter`.</span><span class="sxs-lookup"><span data-stu-id="39057-106">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support the `DbType` or `Size` properties of the `SAPParameter`.</span></span> <span data-ttu-id="39057-107">En su lugar, cuando el usuario especifica un valor para el `SAPParameter`, el valor se convierte internamente en un tipo de datos de .NET según la asignación establecida entre los tipos de datos de .NET y SAP.</span><span class="sxs-lookup"><span data-stu-id="39057-107">Instead, when the user specifies a value for the `SAPParameter`, the value is cast internally to a .NET data type according to the established mapping between .NET and SAP data types.</span></span>  
  
- <span data-ttu-id="39057-108">La longitud máxima permitida para los valores de campo de tipos de datos SAP `CURR`, `DEC`, y `QUAN` es 29 dígitos.</span><span class="sxs-lookup"><span data-stu-id="39057-108">The maximum length allowed for field values of SAP data types `CURR`, `DEC`, and `QUAN` is 29 digits.</span></span> <span data-ttu-id="39057-109">Aunque SAP proporciona 31 lugares para estos valores de tipo de datos de forma nativa, el tipo de datos decimal de .NET al que se convierten impone un límite de 29 dígitos.</span><span class="sxs-lookup"><span data-stu-id="39057-109">Although SAP provides 31 places for these data-type values natively, the .NET decimal data type to which they are converted imposes a 29-digit limit.</span></span>  
  
- <span data-ttu-id="39057-110">Una limitación de la asignación entre el tipo de datos de .NET `Double` y SAP `FLTP` tipo de datos puede producir un error de desbordamiento al leer los datos desde el sistema SAP en el tipo. NET.</span><span class="sxs-lookup"><span data-stu-id="39057-110">A mapping limitation between the .NET data type `Double` and the SAP `FLTP` data type can cause an overflow error when reading data from the SAP system into the .NET type.</span></span> <span data-ttu-id="39057-111">Aunque el tipo de .NET puede representar un número de 64 bits de precisión doble con valores comprendidos entre negativo 1, 79769313486232E308 y 1, 79769313486232E308 positivo, SAP `FLTP` tipo analiza el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no puede superar los 19 + 1.8446744073709552E; el límite real para el `FLTP` tipo es el intervalo negativo 1.8446744073709552E + 19 1.8446744073709552E + 19 positivo.</span><span class="sxs-lookup"><span data-stu-id="39057-111">Although the .NET type can represent a double-precision 64-bit number with values ranging from negative 1.79769313486232e308 to positive 1.79769313486232e308, an SAP `FLTP` type parsed by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] cannot exceed 1.8446744073709552E+19; the effective limit for the `FLTP` type is the range negative 1.8446744073709552E+19 to positive 1.8446744073709552E+19.</span></span>  
  
- <span data-ttu-id="39057-112">Debido a problemas con el control de tiempo de espera por la biblioteca de cliente subyacente, el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no es compatible con el tiempo de espera de conexión y comando.</span><span class="sxs-lookup"><span data-stu-id="39057-112">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support command and connection timeout.</span></span>  
  
- <span data-ttu-id="39057-113">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] no admite el comportamiento del comando asincrónico.</span><span class="sxs-lookup"><span data-stu-id="39057-113">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] does not support asynchronous command behavior.</span></span>  
  
- <span data-ttu-id="39057-114">Cuando se usa con un proyecto de SQL Server Integration Services (SSIS), el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] se produce un error al recuperar datos para las columnas que contienen valores con más de 8.000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="39057-114">When used with a SQL Server Integration Services (SSIS) project, the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] fails to retrieve data for columns that contain values with more than 8000 characters.</span></span> <span data-ttu-id="39057-115">Esto es debido a una restricción de SSIS, según el cual:</span><span class="sxs-lookup"><span data-stu-id="39057-115">This is due to an SSIS restriction according to which:</span></span>  
  
  -   <span data-ttu-id="39057-116">No se admiten los valores mayores que 4000 caracteres en la variable SSIS.</span><span class="sxs-lookup"><span data-stu-id="39057-116">Values greater than 4000 characters in SSIS variable are not supported.</span></span>  
  
  -   <span data-ttu-id="39057-117">No se admiten los valores mayores que 4000 caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="39057-117">Values greater than 4000 wide characters are not supported.</span></span>  
  
  -   <span data-ttu-id="39057-118">No se admiten los valores mayores de 8000 caracteres de byte único.</span><span class="sxs-lookup"><span data-stu-id="39057-118">Values greater than 8000 single-byte characters are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39057-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="39057-119">See Also</span></span>  
 [<span data-ttu-id="39057-120">Acerca del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="39057-120">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)