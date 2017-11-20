---
title: Comprender la arquitectura y los distintos componentes del SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 293189be-61d7-44f4-8ba6-e5550516d9b4
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: feea57176512bb42306feb8b60a10a887a020145
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="understand-the-architecture-and-different-components-of-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="e2a31-102">Comprender la arquitectura y los distintos componentes del SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e2a31-102">Understand the architecture and different components of the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="e2a31-103">Obtenga información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] para ayudar a comprender los distintos componentes y el rol de WCF.</span><span class="sxs-lookup"><span data-stu-id="e2a31-103">Read about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] to help understand the different components, and the role of WCF.</span></span>  

<span data-ttu-id="e2a31-104">El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] es una colección de herramientas y componentes que proporcionan un marco coherente para desarrollar adaptadores reutilizables, con datos completos de metadatos para los sistemas de línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="e2a31-104">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is a collection of tools and components that provide a consistent framework for developing reusable, metadata-rich adapters for line-of-business systems.</span></span> <span data-ttu-id="e2a31-105">Adaptadores escritos mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aparecen como enlaces de WCF personalizados y puede ser utilizado por un cliente compatible con WCF.</span><span class="sxs-lookup"><span data-stu-id="e2a31-105">Adapters written using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] are surfaced as custom WCF bindings and can be consumed by a WCF-capable client.</span></span>  
  
## <a name="features-and-components-overview"></a><span data-ttu-id="e2a31-106">Información general de características y componentes</span><span class="sxs-lookup"><span data-stu-id="e2a31-106">Features and components overview</span></span>
<span data-ttu-id="e2a31-107">[¿Qué es la comunicación línea de negocio adaptador SDK de Windows Foundation](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md) proporciona información general de las características y componentes que conforman el SDK y describe los metadatos y la administración de conexiones y describe los términos comunes de WCF.</span><span class="sxs-lookup"><span data-stu-id="e2a31-107">[What Is the Windows Communication Foundation Line of Business Adapter SDK](what-is-the-windows-communication-foundation-line-of-business-adapter-sdk.md) provides an overview of the features and components that make up the SDK, and describes the metadata, connection management, and describes the common WCF terms.</span></span>

## <a name="role-of-wcf"></a><span data-ttu-id="e2a31-108">Rol de WCF</span><span class="sxs-lookup"><span data-stu-id="e2a31-108">Role of WCF</span></span>  
<span data-ttu-id="e2a31-109">[Leer el uso de WCF mediante el SDK de adaptador LOB de WCF](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md) explica la relación con el SDK y WCF.</span><span class="sxs-lookup"><span data-stu-id="e2a31-109">[Read how WCF is used by the WCF LOB Adapter SDK](read-how-wcf-is-used-by-the-wcf-lob-adapter-sdk.md) explains the relationship with the SDK and WCF.</span></span>

## <a name="architecture-overview"></a><span data-ttu-id="e2a31-110">Información general sobre la arquitectura</span><span class="sxs-lookup"><span data-stu-id="e2a31-110">Architecture Overview</span></span>  
<span data-ttu-id="e2a31-111">[Introducción a la arquitectura ](architecture-overview-of-the-wcf-lob-adapter-sdk.md) descrbied la arquitectura interna y los componentes principales de SDK de adaptador LOB de WCF.</span><span class="sxs-lookup"><span data-stu-id="e2a31-111">[Architecture overview ](architecture-overview-of-the-wcf-lob-adapter-sdk.md) descrbied the internal architecture and the main components of WCF LOB Adapter SDK.</span></span>
 
## <a name="connection-handler-metadata-custom-and-core-components"></a><span data-ttu-id="e2a31-112">Conexión, controlador, metadatos, personalizada y componentes principales</span><span class="sxs-lookup"><span data-stu-id="e2a31-112">Connection, handler, metadata, custom, and core components</span></span>
<span data-ttu-id="e2a31-113">[Componentes clave de SDK de adaptador LOB de WCF](key-components-of-the-wcf-lob-adapter-sdk.md) se describen estos componentes diferentes.</span><span class="sxs-lookup"><span data-stu-id="e2a31-113">[Key Components of the WCF LOB Adapter SDK](key-components-of-the-wcf-lob-adapter-sdk.md) describes these different components.</span></span>

## <a name="biztalk-server-and-the-sdk"></a><span data-ttu-id="e2a31-114">BizTalk Server y el SDK</span><span class="sxs-lookup"><span data-stu-id="e2a31-114">BizTalk Server and the SDK</span></span>  
[<span data-ttu-id="e2a31-115">Adaptador de BizTalk para la base de datos de Oracle y el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="e2a31-115">BizTalk Adapter for Oracle Database and the WCF LOB Adapter SDK</span></span>](../adapter-oracle-database/architecture-overview-of-the-biztalk-adapter-for-oracle-database.md)   
  
## <a name="see-also"></a><span data-ttu-id="e2a31-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2a31-116">See Also</span></span>  
 [<span data-ttu-id="e2a31-117">Introducción a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="e2a31-117">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)