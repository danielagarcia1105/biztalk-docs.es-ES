---
title: Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99dfa0c69500b86fe086ce0daa81e3ffb62857d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a><span data-ttu-id="f8f34-102">Desarrollar aplicaciones de Oracle E-Business Suite mediante el modelo de canal de WCF</span><span class="sxs-lookup"><span data-stu-id="f8f34-102">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>
<span data-ttu-id="f8f34-103">Puede usar el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo del canal para consumir el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] mediante el envío de mensajes XML directamente a través de una instancia del canal creado con el enlace de Oracle EBS.</span><span class="sxs-lookup"><span data-stu-id="f8f34-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] by sending XML messages directly over a channel instance created with the Oracle EBS Binding.</span></span>  
  
 <span data-ttu-id="f8f34-104">Una ventaja de usar el modelo de canal WCF con respecto a las clases fuertemente tipadas y los métodos que se la expone de modelo de servicio WCF es que el modelo del canal proporciona un control más minucioso sobre las operaciones que se realizan en Oracle E-Business Suite.</span><span class="sxs-lookup"><span data-stu-id="f8f34-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle E-Business Suite.</span></span> <span data-ttu-id="f8f34-105">Este control procede del hecho de que en el modelo de canal WCF, puede controlar directamente el contenido de los mensajes que envía a través del canal.</span><span class="sxs-lookup"><span data-stu-id="f8f34-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="f8f34-106">En determinados escenarios, este nivel adicional de control puede ser beneficioso.</span><span class="sxs-lookup"><span data-stu-id="f8f34-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="f8f34-107">Por ejemplo, cuando se usa el modelo de canal WCF para realizar una operación de actualización en una tabla, puede actualizar selectivamente las columnas de las filas de destino mediante la omisión de las columnas de la plantilla de actualización que se pasa en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="f8f34-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="f8f34-108">Las únicas columnas que son necesarias son los que tienen "nillable = false" en el archivo WSDL.</span><span class="sxs-lookup"><span data-stu-id="f8f34-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="f8f34-109">El método de actualización expuesto por un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente utiliza un parámetro de registro fuertemente tipada de la plantilla que incluye todas las columnas en el esquema de tabla.</span><span class="sxs-lookup"><span data-stu-id="f8f34-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="f8f34-110">Los temas de esta sección explican cómo realizar operaciones en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mediante el modelo de canal WCF.</span><span class="sxs-lookup"><span data-stu-id="f8f34-110">The topics in this section explain how to perform operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8f34-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f8f34-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f8f34-112">Información general sobre el modelo de canal WCF con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="f8f34-112">Overview of the WCF channel model with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="f8f34-113">Crear un canal con Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="f8f34-113">Create a channel using Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [<span data-ttu-id="f8f34-114">Ejecutar una operación de inserción en una tabla de interfaz en Oracle E-Business Suite mediante el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="f8f34-114">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="f8f34-115">Sondeo Oracle E-Business Suite con la instrucción SELECT con el modelo de canal WCF</span><span class="sxs-lookup"><span data-stu-id="f8f34-115">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a><span data-ttu-id="f8f34-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8f34-116">See Also</span></span>  
[<span data-ttu-id="f8f34-117">Desarrollar las aplicaciones de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="f8f34-117">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)