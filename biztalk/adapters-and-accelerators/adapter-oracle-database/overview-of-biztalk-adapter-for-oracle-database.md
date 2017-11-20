---
title: "Información general sobre el adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapter, overview
- ODP.NET
- Oracle Data Provider for .NET 2.0
ms.assetid: 852b8f82-ab34-45b8-ad7f-263d719a87f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b874b5523256342a4e8ae14b2c475ede11fe279
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="a98eb-102">Información general sobre el adaptador de BizTalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a98eb-102">Overview of BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="a98eb-103">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone la base de datos de Oracle como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="a98eb-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes the Oracle database as a WCF service.</span></span> <span data-ttu-id="a98eb-104">Los clientes de adaptador pueden realizar operaciones en la base de datos de Oracle mediante el intercambio de mensajes SOAP con el adaptador.</span><span class="sxs-lookup"><span data-stu-id="a98eb-104">Adapter clients can perform operations on the Oracle database by exchanging SOAP messages with the adapter.</span></span> <span data-ttu-id="a98eb-105">El adaptador utiliza el mensaje de WCF y realiza llamadas ODP.NET adecuadas para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="a98eb-105">The adapter consumes the WCF message and makes appropriate ODP.NET calls to perform the operation.</span></span> <span data-ttu-id="a98eb-106">El adaptador devuelve la respuesta de la base de datos de Oracle al cliente en forma de mensajes SOAP.</span><span class="sxs-lookup"><span data-stu-id="a98eb-106">The adapter returns the response from the Oracle database back to the client in the form of SOAP messages.</span></span>  
  
 <span data-ttu-id="a98eb-107">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] metadatos de las superficies de artefactos de base de datos de Oracle (tablas, funciones, procedimientos, etc.) que describen la estructura de SOAP del mensaje en forma de WSDL.</span><span class="sxs-lookup"><span data-stu-id="a98eb-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces metadata of Oracle database artifacts (tables, functions, procedures, etc.) that describes the structure of a SOAP message in the form of WSDL.</span></span> <span data-ttu-id="a98eb-108">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para permitir que los clientes de adaptador recuperar metadatos para las operaciones y genera los artefactos de programación que se pueden usar en la solución de programación.</span><span class="sxs-lookup"><span data-stu-id="a98eb-108">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], and [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to enable adapter clients to retrieve metadata for operations and generates programming artifacts that can be used in your programming solution.</span></span>  
  
 <span data-ttu-id="a98eb-109">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa el proveedor de datos de Oracle para .NET (ODP.NET) para comunicarse con la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a98eb-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the Oracle Data Provider for .NET (ODP.NET) to communicate with the Oracle database.</span></span> <span data-ttu-id="a98eb-110">Puede usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para comunicarse con la base de datos de Oracle de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="a98eb-110">You can use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to communicate with the Oracle database in the following ways:</span></span>  
  
-   <span data-ttu-id="a98eb-111">Al desarrollar aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a98eb-111">By developing BizTalk applications.</span></span> <span data-ttu-id="a98eb-112">Vea [desarrollar las aplicaciones de BizTalk](../../core/develop-your-biztalk-applications.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a98eb-112">See [Develop your BizTalk applications](../../core/develop-your-biztalk-applications.md) for more information.</span></span>  
  
-   <span data-ttu-id="a98eb-113">Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="a98eb-113">By using the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model.</span></span> <span data-ttu-id="a98eb-114">Vea [aplicaciones de desarrollar bases de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a98eb-114">See [Develop Oracle Database applications using the WCF Service model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) for more information.</span></span>  
  
-   <span data-ttu-id="a98eb-115">Mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="a98eb-115">By using the WCF channel model.</span></span> <span data-ttu-id="a98eb-116">Vea [aplicaciones de desarrollar bases de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="a98eb-116">See [Develop Oracle Database applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md) for more information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a98eb-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a98eb-117">In This Section</span></span>  
  
-   <span data-ttu-id="a98eb-118">[¿Cómo se conecta el adaptador en una base de datos de Oracle?](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="a98eb-118">[How Does the Adapter Connect to an Oracle Database?](https://msdn.microsoft.com/library/cc185360(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="a98eb-119">[¿Cómo los metadatos de adaptador Oracle expuesta?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="a98eb-119">[How Does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)</span></span>  
  
-   <span data-ttu-id="a98eb-120">[¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="a98eb-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>  
  
-   [<span data-ttu-id="a98eb-121">¿Cómo las transacciones de controlar adaptador?</span><span class="sxs-lookup"><span data-stu-id="a98eb-121">How does the Adapter Handle Transactions?</span></span>](https://msdn.microsoft.com/library/dd788428.aspx)  
  
-   [<span data-ttu-id="a98eb-122">Compatibilidad con Streaming para tipos de datos LOB en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a98eb-122">Streaming Support for LOB Data Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="a98eb-123">Las operaciones que son compatibles con el adaptador de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a98eb-123">What operations are supported by the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/what-operations-are-supported-by-the-oracle-database-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="a98eb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="a98eb-124">See Also</span></span>  
 [<span data-ttu-id="a98eb-125">Descripción del adaptador de Biztalk para base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a98eb-125">Understanding the Biztalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)