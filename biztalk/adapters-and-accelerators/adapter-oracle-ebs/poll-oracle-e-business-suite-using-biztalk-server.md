---
title: Sondeo Oracle E-Business Suite con BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9b5d0743d39dfcf6cbab7e1da20a8a3fb1382fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218012"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a><span data-ttu-id="a91c6-102">Sondeo Oracle E-Business Suite con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a91c6-102">Poll Oracle E-Business Suite using BizTalk Server</span></span>
<span data-ttu-id="a91c6-103">Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de sondeo de base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a91c6-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="a91c6-104">El adaptador proporciona dos maneras de sondeo de la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="a91c6-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
-   <span data-ttu-id="a91c6-105">**Utilizar las instrucciones SELECT**.</span><span class="sxs-lookup"><span data-stu-id="a91c6-105">**Using SELECT statements**.</span></span> <span data-ttu-id="a91c6-106">Puede especificar una instrucción SELECT simple para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a91c6-106">You can specify a simple SELECT statement to poll the Oracle database.</span></span> <span data-ttu-id="a91c6-107">El adaptador ejecuta la instrucción SELECT a los intervalos especificados y devuelve el resultado a los clientes de adaptador.</span><span class="sxs-lookup"><span data-stu-id="a91c6-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
-   <span data-ttu-id="a91c6-108">**Uso de procedimientos almacenados**.</span><span class="sxs-lookup"><span data-stu-id="a91c6-108">**Using stored procedures**.</span></span> <span data-ttu-id="a91c6-109">Puede especificar un procedimiento almacenado para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a91c6-109">You can specify a stored procedure to poll the Oracle database.</span></span> <span data-ttu-id="a91c6-110">El adaptador ejecuta el procedimiento almacenado a los intervalos especificados y devuelve el resultado a los clientes de adaptador.</span><span class="sxs-lookup"><span data-stu-id="a91c6-110">The adapter executes the stored procedure at specified intervals and returns the result to the adapter clients.</span></span>  
  
 <span data-ttu-id="a91c6-111">La diferencia clave en los dos enfoques es que los clientes de adaptador de manera especifican una instrucción de sondeo que el adaptador utiliza para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a91c6-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="a91c6-112">Mientras que la instrucción de sondeo para el primer enfoque es una instrucción SELECT, la instrucción de sondeo para el enfoque de procedimiento almacenado es un mensaje de solicitud que se ejecuta el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a91c6-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the stored procedure approach is a request message that executes the stored procedure.</span></span> <span data-ttu-id="a91c6-113">Los clientes de adaptador especificar la instrucción de sondeo, para cualquier enfoque para la **PollingInput** propiedad de enlace.</span><span class="sxs-lookup"><span data-stu-id="a91c6-113">Adapter clients specify the polling statement, for either approach, for the **PollingInput** binding property.</span></span> <span data-ttu-id="a91c6-114">Para obtener más información acerca de las propiedades de enlace, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a91c6-114">For more information about the binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
 <span data-ttu-id="a91c6-115">Los temas de esta sección proporcionan instrucciones sobre cómo sondear mediante una instrucción SELECT y un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="a91c6-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a91c6-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a91c6-116">In This Section</span></span>  
  
-   [<span data-ttu-id="a91c6-117">Sondeo Oracle E-Business Suite con la instrucción SELECT</span><span class="sxs-lookup"><span data-stu-id="a91c6-117">Poll Oracle E-Business Suite Using SELECT Statement</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [<span data-ttu-id="a91c6-118">Uso de procedimientos almacenados de sondeo Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="a91c6-118">Poll Oracle E-Business Suite Using Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="a91c6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a91c6-119">See Also</span></span>  
[<span data-ttu-id="a91c6-120">Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="a91c6-120">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)