---
title: El modelo de servicio mediante WCF sondeo Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96670a39-4fec-49bf-85d1-947b1a1bc750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2f8c9f16ed93e2866da0cbd55021edfdb2bd863
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995349"
---
# <a name="poll-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="012aa-102">Sondear Oracle E-Business Suite mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="012aa-102">Poll Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="012aa-103">Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes basados en sondeos de la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="012aa-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive polling-based messages from the Oracle database.</span></span> <span data-ttu-id="012aa-104">El adaptador proporciona dos maneras de sondear la base de datos de Oracle:</span><span class="sxs-lookup"><span data-stu-id="012aa-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
- <span data-ttu-id="012aa-105">**Utilizar las instrucciones SELECT**.</span><span class="sxs-lookup"><span data-stu-id="012aa-105">**Using SELECT statements**.</span></span> <span data-ttu-id="012aa-106">Puede especificar una instrucción SELECT simple para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="012aa-106">You can specify a simple SELECT statement to poll the Oracle database.</span></span> <span data-ttu-id="012aa-107">El adaptador ejecuta la instrucción SELECT a intervalos especificados y devuelve el resultado a los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="012aa-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
- <span data-ttu-id="012aa-108">**Uso de procedimientos almacenados**.</span><span class="sxs-lookup"><span data-stu-id="012aa-108">**Using stored procedures**.</span></span> <span data-ttu-id="012aa-109">Puede especificar un procedimiento almacenado para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="012aa-109">You can specify a stored procedure to poll the Oracle database.</span></span> <span data-ttu-id="012aa-110">El adaptador ejecuta el procedimiento almacenado a intervalos especificados y devuelve el resultado a los clientes del adaptador.</span><span class="sxs-lookup"><span data-stu-id="012aa-110">The adapter executes the stored procedure at specified intervals and returns the result to the adapter clients.</span></span>  
  
  <span data-ttu-id="012aa-111">La diferencia clave en los dos enfoques es que los clientes del adaptador de manera especifican una instrucción de sondeo que utiliza el adaptador para sondear la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="012aa-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="012aa-112">Aunque la instrucción de sondeo para el primer enfoque es una instrucción SELECT simple, la instrucción de sondeo para el enfoque de procedimiento almacenado es un mensaje de solicitud que se ejecuta el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="012aa-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the stored procedure approach is a request message that executes the stored procedure.</span></span> <span data-ttu-id="012aa-113">Los clientes del adaptador especifican la instrucción de sondeo para cualquier enfoque, para el **PollingInput** enlaza la propiedad.</span><span class="sxs-lookup"><span data-stu-id="012aa-113">Adapter clients specify the polling statement, for either approach, for the **PollingInput** binding property.</span></span> <span data-ttu-id="012aa-114">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="012aa-114">For more information about the binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
  <span data-ttu-id="012aa-115">Los temas de esta sección proporcionan instrucciones sobre cómo sondear con una instrucción SELECT y un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="012aa-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="012aa-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="012aa-116">In This Section</span></span>  
  
-   [<span data-ttu-id="012aa-117">Sondear Oracle E-Business Suite mediante la instrucción SELECT con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="012aa-117">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="012aa-118">Sondear Oracle E-Business Suite mediante procedimientos almacenados con el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="012aa-118">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="012aa-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="012aa-119">See Also</span></span>  
 [<span data-ttu-id="012aa-120">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="012aa-120">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)