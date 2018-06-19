---
title: Obtiene los metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7ac720-e573-4564-8d15-8212a815f1f7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec993dd308abf0f364eb73f6f35d48d618d6807e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222156"
---
# <a name="get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter"></a><span data-ttu-id="9c330-102">Obtiene los metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL</span><span class="sxs-lookup"><span data-stu-id="9c330-102">Get metadata for SQL Server operations in Visual Studio using the SQL adapter</span></span>
<span data-ttu-id="9c330-103">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede utilizar para ayudarle a desarrollar soluciones con el adaptador: el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c330-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter—the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)].</span></span> <span data-ttu-id="9c330-104">Los clientes de adaptador deben usar estos componentes para conectarse a SQL Server y, a continuación, generar metadatos para las operaciones que deseen realizar.</span><span class="sxs-lookup"><span data-stu-id="9c330-104">Adapter clients must use these components to connect to SQL Server and then generate metadata for the operations they want to perform.</span></span>  
  
 <span data-ttu-id="9c330-105">Todos estos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:</span><span class="sxs-lookup"><span data-stu-id="9c330-105">All these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
-   <span data-ttu-id="9c330-106">Proporcionar una interfaz de Microsoft Windows a través del cual se puede examinar y buscar para las operaciones que desea utilizar en la solución.</span><span class="sxs-lookup"><span data-stu-id="9c330-106">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
-   <span data-ttu-id="9c330-107">Al recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="9c330-107">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
-   <span data-ttu-id="9c330-108">Convertir que los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y lo agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c330-108">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
 <span data-ttu-id="9c330-109">Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]y el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c330-109">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
