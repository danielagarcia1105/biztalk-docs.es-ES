---
title: Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2635ac4b21173fe1a12603c60263dfa70b5a18e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974205"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a><span data-ttu-id="04daa-102">Operaciones en funciones y procedimientos con tipos de registros de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="04daa-102">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>
<span data-ttu-id="04daa-103">Tipos de registros de Oracle se usan para representar información jerárquica de los parámetros pasados a los procedimientos y funciones de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="04daa-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="04daa-104">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos.</span><span class="sxs-lookup"><span data-stu-id="04daa-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> <span data-ttu-id="04daa-105">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite los siguientes tipos de los tipos de registros:</span><span class="sxs-lookup"><span data-stu-id="04daa-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="04daa-106">Tipos de registros que se declaran como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="04daa-106">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="04daa-107">Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL, por ejemplo, escriba rec_type1 es RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="04daa-107">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages for example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
- <span data-ttu-id="04daa-108">Tipos de registros que contienen registros anidados.</span><span class="sxs-lookup"><span data-stu-id="04daa-108">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="04daa-109">Tipos de registros que aparecen como IN, OUT o IN OUT parámetros a procedimientos o funciones.</span><span class="sxs-lookup"><span data-stu-id="04daa-109">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="04daa-110">Tipos de registros que son los valores devueltos de funciones.</span><span class="sxs-lookup"><span data-stu-id="04daa-110">RECORD types that are RETURN values of functions.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="04daa-111">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] no admite tipos BFILE como miembros de registro.</span><span class="sxs-lookup"><span data-stu-id="04daa-111">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
  <span data-ttu-id="04daa-112">Para obtener información acerca de:</span><span class="sxs-lookup"><span data-stu-id="04daa-112">For information about:</span></span>  
  
- <span data-ttu-id="04daa-113">Invocar una función o procedimiento que implican tipos de registros mediante el modelo de servicio WCF, vea [ejecutar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="04daa-113">Invoking a function or procedure involving RECORD types using the WCF service model, see [Run Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="04daa-114">Invocar una función o procedimiento que implica el registro de tipos que utilizan [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [invocar funciones y procedimientos con tipos de registros por mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="04daa-114">Invoking a function or procedure involving RECORD types using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Invoke Functions and Procedures with RECORD Types by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="04daa-115">Estructura XML de registro de los tipos compatibles con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para tipos de registros](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).</span><span class="sxs-lookup"><span data-stu-id="04daa-115">XML structure for RECORD types as supported by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for RECORD Types](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04daa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="04daa-116">See Also</span></span>  
 <span data-ttu-id="04daa-117">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="04daa-117">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>