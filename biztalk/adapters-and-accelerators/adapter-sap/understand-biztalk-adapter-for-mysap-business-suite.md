---
title: Comprender el adaptador de BizTalk para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 709833ecec71a98e0e09d2cd660b68bf5b647d8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985613"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="525c2-102">Comprender el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="525c2-102">Understand BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="525c2-103">El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="525c2-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="525c2-104">Los adaptadores proporcionan las siguientes ventajas a los clientes:</span><span class="sxs-lookup"><span data-stu-id="525c2-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="525c2-105">**Experiencia en tiempo de diseño coherente**.</span><span class="sxs-lookup"><span data-stu-id="525c2-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="525c2-106">Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.</span><span class="sxs-lookup"><span data-stu-id="525c2-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="525c2-107">**Variar las opciones de programación**.</span><span class="sxs-lookup"><span data-stu-id="525c2-107">**Varied programming options**.</span></span> <span data-ttu-id="525c2-108">Los adaptadores ofrecen una selección de modelo que incluye el modelo de canal de Windows Communication Foundation (WCF), modelo de servicio WCF, servicios web, ADO.NET o BizTalk admitida modelos de programación.</span><span class="sxs-lookup"><span data-stu-id="525c2-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="525c2-109">**Uniforme de experiencia en LOB**.</span><span class="sxs-lookup"><span data-stu-id="525c2-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="525c2-110">Los adaptadores de estandarizan sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y, por tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.</span><span class="sxs-lookup"><span data-stu-id="525c2-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="525c2-111">Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF.</span><span class="sxs-lookup"><span data-stu-id="525c2-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="525c2-112">El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="525c2-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="525c2-113">El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="525c2-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="525c2-114">Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span><span class="sxs-lookup"><span data-stu-id="525c2-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="525c2-115">Para realizar operaciones en un sistema SAP, los clientes del adaptador deben tener acceso al relevantes llamadas a funciones remotas (RFC), Interfaces de programación de aplicaciones empresariales (BAPI) y los IDOC (o documentos intermedios).</span><span class="sxs-lookup"><span data-stu-id="525c2-115">To perform operations on an SAP system, adapter clients must have access to the relevant Remote Function Calls (RFCs), Business Application Programming Interfaces (BAPIs), and IDOCs (or intermediate documents).</span></span> <span data-ttu-id="525c2-116">Un sistema SAP R/3 expone RFC, BAPI y los IDOC para integración empresarial.</span><span class="sxs-lookup"><span data-stu-id="525c2-116">An SAP R/3 system exposes RFCs, BAPIs, and IDOCs for business integration.</span></span> <span data-ttu-id="525c2-117">Las solicitudes de cambio son módulos de una función remota que implementan la lógica empresarial específica.</span><span class="sxs-lookup"><span data-stu-id="525c2-117">RFCs are remote function modules that implement specific business logic.</span></span> <span data-ttu-id="525c2-118">Esta lógica se puede invocar desde una aplicación externa, como BizTalk Server o una aplicación. NET.</span><span class="sxs-lookup"><span data-stu-id="525c2-118">This logic can be invoked from an external application such as BizTalk Server or a .NET application.</span></span> <span data-ttu-id="525c2-119">BAPI es interfaces de método a los objetos de negocio SAP, que a su vez se exponen a través de interfaces RFC estándares.</span><span class="sxs-lookup"><span data-stu-id="525c2-119">BAPIs are method interfaces to SAP business objects, which are in turn exposed through standard RFC interfaces.</span></span> <span data-ttu-id="525c2-120">IDOC son un mecanismo para abstraer la capa de comunicación de electronic data interchange (EDI) para la comunicación entre los sistemas que no sean de SAP y SAP.</span><span class="sxs-lookup"><span data-stu-id="525c2-120">IDOCs are a mechanism to abstract the electronic data interchange (EDI) communication layer for communication between SAP and non-SAP systems.</span></span> <span data-ttu-id="525c2-121">Con [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], puede tener acceso a la RFC, BAPI, y exponen un sistema SAP IDOC.</span><span class="sxs-lookup"><span data-stu-id="525c2-121">With [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], you can access the RFCs, BAPIs, and IDOCs exposed by an SAP system.</span></span>  
  
  <span data-ttu-id="525c2-122">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] también incluye [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], que proporciona una interfaz ADO al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="525c2-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also includes [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], which provides an ADO interface to the SAP system.</span></span>  
  
  <span data-ttu-id="525c2-123">En esta sección se enumera las características para la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="525c2-123">This section lists the features for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="525c2-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="525c2-124">In This Section</span></span>  
  
-   [<span data-ttu-id="525c2-125">Introducción a la arquitectura del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="525c2-125">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="525c2-126">Características clave del adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="525c2-126">Key Features in the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="525c2-127">Limitaciones del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="525c2-127">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="525c2-128">Acerca del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="525c2-128">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a><span data-ttu-id="525c2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="525c2-129">See Also</span></span>  
[<span data-ttu-id="525c2-130">Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="525c2-130">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)