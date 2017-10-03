---
title: "Cómo mantener versiones de vocabulario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, versioning
- vocabularies, publishing
- versioning, vocabularies
- updating, vocabularies
- vocabularies, updating
ms.assetid: 43593c6f-4590-4940-ac17-4015928e5838
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3c67d79878c59e3b0dcba6dcd15955f34ad97c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-vocabulary-versions"></a><span data-ttu-id="544d4-102">Cómo mantener versiones de vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-102">How to Maintain Vocabulary Versions</span></span>
<span data-ttu-id="544d4-103">Cuando haya agregado definiciones de vocabulario a una versión, puede guardar la versión en el almacén de reglas para su posterior desarrollo, o puede publicar la versión para crear un conjunto de términos enlazados con datos bien definido e inmutable que esté disponible para que los usuarios lo vayan agregando a las reglas conforme desarrollen directivas.</span><span class="sxs-lookup"><span data-stu-id="544d4-103">When you have added vocabulary definitions to a version of your vocabulary, you can save the version to the rule store for further development, or you can publish the version to create a well-defined, immutable set of data-bound terms that are available to users to add to rules as they develop their policies.</span></span> <span data-ttu-id="544d4-104">Observe que las reglas existentes seguirán señalando a las versiones antiguas.</span><span class="sxs-lookup"><span data-stu-id="544d4-104">Note that fact that existing rules will still point to the old versions.</span></span>  
  
 <span data-ttu-id="544d4-105">Este tema contiene procedimientos para las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="544d4-105">This topic contains procedures for the following tasks:</span></span>  
  
-   <span data-ttu-id="544d4-106">Guardar una versión de vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-106">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="544d4-107">Publicar una versión de vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-107">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="544d4-108">Crear una versión actualizada de un vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-108">To create an updated version of a vocabulary</span></span>  
  
-   <span data-ttu-id="544d4-109">Crear una nueva versión vacía de un vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-109">To create an empty new version of a vocabulary</span></span>  
  
### <a name="to-save-a-vocabulary-version"></a><span data-ttu-id="544d4-110">Guardar una versión de vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-110">To save a vocabulary version</span></span>  
  
-   <span data-ttu-id="544d4-111">Haga clic en la versión y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="544d4-111">Right-click the version, and then click **Save**.</span></span>  
  
### <a name="to-publish-a-vocabulary-version"></a><span data-ttu-id="544d4-112">Publicar una versión de vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-112">To publish a vocabulary version</span></span>  
  
-   <span data-ttu-id="544d4-113">Haga clic en la versión y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="544d4-113">Right-click the version, and then click **Publish**.</span></span>  
  
### <a name="to-create-an-updated-version-of-a-vocabulary"></a><span data-ttu-id="544d4-114">Crear una versión actualizada de un vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-114">To create an updated version of a vocabulary</span></span>  
  
1.  <span data-ttu-id="544d4-115">Haga clic en una versión existente y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="544d4-115">Right-click an existing version, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="544d4-116">Haga clic en la carpeta de vocabulario y, a continuación, haga clic en **pegar**.</span><span class="sxs-lookup"><span data-stu-id="544d4-116">Right-click the vocabulary folder, and then click **Paste**.</span></span>  
  
     <span data-ttu-id="544d4-117">Se crea una nueva versión, con los mismos elementos que la versión copiada.</span><span class="sxs-lookup"><span data-stu-id="544d4-117">A new version is created, with the same elements as the copied version.</span></span>  
  
### <a name="to-create-an-empty-new-version-of-a-vocabulary"></a><span data-ttu-id="544d4-118">Crear una nueva versión vacía de un vocabulario</span><span class="sxs-lookup"><span data-stu-id="544d4-118">To create an empty new version of a vocabulary</span></span>  
  
-   <span data-ttu-id="544d4-119">Haga clic en la carpeta de vocabulario y, a continuación, haga clic en **agregar nueva versión**.</span><span class="sxs-lookup"><span data-stu-id="544d4-119">Right-click the vocabulary folder, and then click **Add New Version**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="544d4-120">Solo puede utilizar definiciones de vocabulario de vocabularios publicados.</span><span class="sxs-lookup"><span data-stu-id="544d4-120">You can only use vocabulary definitions from published vocabularies.</span></span>