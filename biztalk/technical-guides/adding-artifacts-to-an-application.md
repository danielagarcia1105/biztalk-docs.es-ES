---
title: "Agregar artefactos a una aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9b5e92e-2e55-41d7-9959-f62753bbeb04
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c08fa95dddad06efb2c51d93df56b757ae4caca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adding-artifacts-to-an-application"></a><span data-ttu-id="94f06-102">Agregar artefactos a una aplicación</span><span class="sxs-lookup"><span data-stu-id="94f06-102">Adding Artifacts to an Application</span></span>
<span data-ttu-id="94f06-103">Puede agregar y configurar artefactos, como el envío y puertos de recepción, ubicaciones de recepción y orquestaciones, con la administración de la consola.</span><span class="sxs-lookup"><span data-stu-id="94f06-103">You can add and configure artifacts, such as send and receive ports, receive locations, and orchestrations, by using the Administration console.</span></span> <span data-ttu-id="94f06-104">También puede generar archivos de enlace y agregarlos a la aplicación si desea aplicar diferentes enlaces a la que desea importar la aplicación en entornos diferentes.</span><span class="sxs-lookup"><span data-stu-id="94f06-104">You can also generate binding files and add them to the application if you want to apply different bindings for the different environments that you will import the application into.</span></span>  
  
 <span data-ttu-id="94f06-105">Puede agregar más (normalmente externos a BizTalk Server) artefactos, como scripts, certificados y archivos Léame, a la aplicación en el nodo de recursos.</span><span class="sxs-lookup"><span data-stu-id="94f06-105">You can add additional (typically non-BizTalk Server) artifacts, such as scripts, certificates, and Readme files, to the application under the Resources node.</span></span> <span data-ttu-id="94f06-106">Para ello, use la consola de administración o BTSTask.</span><span class="sxs-lookup"><span data-stu-id="94f06-106">To do so, use the Administration console or BTSTask.</span></span>  
  
 <span data-ttu-id="94f06-107">Para obtener más información acerca de artefactos, vea [cómo crear o agregar un artefacto](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.Microsoft.com/fwlink/?) LinkID = 154724), [administrar artefactos](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.Microsoft.com/fwlink/?) LinkID = 154725) y [archivos de enlace e implementación de la aplicación](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.Microsoft.com/fwlink/?) LinkID = 154726).</span><span class="sxs-lookup"><span data-stu-id="94f06-107">For more information about artifacts, see [How to Create or Add an Artifact](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.microsoft.com/fwlink/?LinkID=154724), [Managing Artifacts](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725) and [Binding Files and Application Deployment](http://go.microsoft.com/fwlink/?LinkID=154726) (http://go.microsoft.com/fwlink/?LinkID=154726).</span></span>  
  
## <a name="factoring-artifacts-into-multiple-biztalk-applications"></a><span data-ttu-id="94f06-108">Factorizar artefactos en varias aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="94f06-108">Factoring Artifacts into Multiple BizTalk Applications</span></span>  
 <span data-ttu-id="94f06-109">Durante el proceso de desarrollo, es posible que se hayan implementado los ensamblados en una única aplicación por comodidad.</span><span class="sxs-lookup"><span data-stu-id="94f06-109">During the development process, you may have deployed your assemblies into a single application for convenience.</span></span> <span data-ttu-id="94f06-110">Puede que, por distintas razones, desee descomponer los artefactos en varias aplicaciones antes de que se implementen en la producción.</span><span class="sxs-lookup"><span data-stu-id="94f06-110">For various reasons, you may want to factor the artifacts into multiple applications before they are deployed into production.</span></span>  
  
 <span data-ttu-id="94f06-111">Antes de implementar, debe realizar un análisis detallado de la factorización de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94f06-111">Before deploying, you should perform an in-depth analysis of the factoring of an assembly.</span></span> <span data-ttu-id="94f06-112">Determinar si es no necesario realizar ninguna factorización, dividir completa o factorización óptimo.</span><span class="sxs-lookup"><span data-stu-id="94f06-112">Determine whether you should perform No factoring, Full factoring, or Optimal factoring.</span></span>  
  
 <span data-ttu-id="94f06-113">**No hay factorización**</span><span class="sxs-lookup"><span data-stu-id="94f06-113">**No Factoring**</span></span>  
  
 <span data-ttu-id="94f06-114">Todos los artefactos de BizTalk están en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94f06-114">All BizTalk artifacts are in one assembly.</span></span> <span data-ttu-id="94f06-115">Esto es más fácil de comprender e implementar, pero proporciona la menor cantidad de flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="94f06-115">This is the easiest to understand and deploy, but provides the least amount of flexibility.</span></span>  
  
 <span data-ttu-id="94f06-116">**Factorización completa**</span><span class="sxs-lookup"><span data-stu-id="94f06-116">**Full Factoring**</span></span>  
  
 <span data-ttu-id="94f06-117">Cada artefacto de BizTalk está en su propio ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94f06-117">Each BizTalk artifact is in its own assembly.</span></span> <span data-ttu-id="94f06-118">Esto ofrece la máxima flexibilidad, pero es la más compleja para implementar y comprender.</span><span class="sxs-lookup"><span data-stu-id="94f06-118">This provides the most flexibility, but is the most complex to deploy and understand.</span></span>  
  
 <span data-ttu-id="94f06-119">**Factorización óptimo**</span><span class="sxs-lookup"><span data-stu-id="94f06-119">**Optimal Factoring**</span></span>  
  
 <span data-ttu-id="94f06-120">Factorización óptimo comprendida entre n factorización y factorización completa en función de un análisis exhaustivo de las aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="94f06-120">Optimal factoring falls between No Factoring and Full Factoring based on in-depth analysis of your BizTalk applications.</span></span> <span data-ttu-id="94f06-121">Además de las versiones, esto permite que más fácil implementan el diseño de host de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="94f06-121">In addition to versioning, this allows you to more easily implement your BizTalk host design.</span></span> <span data-ttu-id="94f06-122">Esto se logra mediante la búsqueda de relaciones entre artefactos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="94f06-122">This is achieved by looking for relationships among BizTalk artifacts.</span></span> <span data-ttu-id="94f06-123">Si es posible, coloque los artefactos que están siempre con control de versiones en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="94f06-123">If possible, put artifacts that are always versioned together in the same assembly.</span></span> <span data-ttu-id="94f06-124">Si es necesaria crear versiones independientes de los artefactos, debe colocar en distintos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="94f06-124">If independent versioning of the artifacts is required, then they must be put in different assemblies.</span></span> <span data-ttu-id="94f06-125">Este es el nivel de factorización de la que se desea lograr.</span><span class="sxs-lookup"><span data-stu-id="94f06-125">This is the level of factoring that you want to achieve.</span></span>