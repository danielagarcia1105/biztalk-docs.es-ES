---
title: Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d7f731-cd0f-4970-a3cd-072f09312989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f4a7b5d016adf1cc7fa8bb73772e1e5d7145520
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002077"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a><span data-ttu-id="08360-102">Obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="08360-102">Get metadata for Oracle E-Business Suite operations in Visual Studio</span></span>
<span data-ttu-id="08360-103">El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede usar para ayudar a desarrollar soluciones con el adaptador:</span><span class="sxs-lookup"><span data-stu-id="08360-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter:</span></span>  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
- [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
  <span data-ttu-id="08360-104">Los clientes del adaptador deben usar estos componentes para conectarse a Oracle E-Business Suite y, a continuación, generar los metadatos para las operaciones que desean realizar.</span><span class="sxs-lookup"><span data-stu-id="08360-104">Adapter clients must use these components to connect to Oracle E-Business Suite, and then generate metadata for the operations they want to perform.</span></span> <span data-ttu-id="08360-105">Todos estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:</span><span class="sxs-lookup"><span data-stu-id="08360-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
- <span data-ttu-id="08360-106">Proporcionar una interfaz de Microsoft Windows a través del cual puede examinar y buscar para las operaciones que desea usar en la solución.</span><span class="sxs-lookup"><span data-stu-id="08360-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
- <span data-ttu-id="08360-107">Recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="08360-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
- <span data-ttu-id="08360-108">Convertir los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y agregarlo al proyecto.</span><span class="sxs-lookup"><span data-stu-id="08360-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
  <span data-ttu-id="08360-109">Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08360-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08360-110">Si ha creado una solución mediante el adaptador en una versión determinada de Oracle E-Business Suite y ahora desea implementar la solución en una versión diferente de Oracle E-Business Suite, a continuación, debe probar la solución antes de implementarla.</span><span class="sxs-lookup"><span data-stu-id="08360-110">If you have created a solution using the adapter on a particular version of Oracle E-Business Suite, and now want to deploy the solution on a different version of Oracle E-Business Suite then you should test the solution before deploying it.</span></span> <span data-ttu-id="08360-111">Que se produzcan problemas al implementar la solución en una versión diferente de Oracle E-Business Suite, porque los metadatos del artefacto subyacente pueden ser diferente.</span><span class="sxs-lookup"><span data-stu-id="08360-111">You might face issues while deploying the solution on a different version of Oracle E-Business Suite because the metadata of the underlying artifact might be different.</span></span> <span data-ttu-id="08360-112">Para resolver este problema, debe volver a generar los metadatos mediante el adaptador en la misma versión de Oracle E-Business Suite en el que va a implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="08360-112">To resolve this issue, you should regenerate the metadata using the adapter on the same version of Oracle E-Business Suite on which you intend to deploy the solution.</span></span>  
  
