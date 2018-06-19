---
title: Cómo desarrollar vocabularios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2644cc938cbe5e42f4e124453d863741755d965d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249060"
---
# <a name="how-to-develop-vocabularies"></a><span data-ttu-id="8e6b0-102">Cómo desarrollar vocabularios</span><span class="sxs-lookup"><span data-stu-id="8e6b0-102">How to Develop Vocabularies</span></span>
<span data-ttu-id="8e6b0-103">Las condiciones y acciones de reglas se basan en orígenes que pueden tener información de enlace detallada y de difícil lectura y que cuentan al usuario poco o nada acerca de aquello a lo que se refieren.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-103">Rule conditions and actions are based on sources that may have detailed, difficult-to-read binding information that tells the user little or nothing about what they refer to.</span></span> <span data-ttu-id="8e6b0-104">El marco de trabajo de reglas de negocios permite crear vocabularios para simplificar el desarrollo de reglas mediante terminología intuitiva para el usuario y específica del dominio, y que los usuarios pueden asociar con condiciones y acciones de reglas.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-104">The Business Rules Framework enables you to create vocabularies to simplify the development of rules by offering users intuitive, domain-specific terminology that users can associate with rule conditions and actions.</span></span>  
  
 <span data-ttu-id="8e6b0-105">Puede identificar orígenes de datos para utilizar y crear un nuevo vocabulario y agregarle a éste definiciones. </span><span class="sxs-lookup"><span data-stu-id="8e6b0-105">You can identify data sources to use, create a new vocabulary, and add vocabulary definitions to it.</span></span> <span data-ttu-id="8e6b0-106">Puede guardar una versión del vocabulario en el almacén de reglas y, cuando esté completa, publicarla para proporcionar a los usuarios un conjunto de términos bien definidos e inmutables enlazados con referencias de datos.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-106">You can save a version of your vocabulary to the rule store, and when it is complete, you can publish it to provide users with a well-defined, immutable set of terms that are bound to data references.</span></span>  
  
 <span data-ttu-id="8e6b0-107">Si necesita realizar cambios en el vocabulario más adelante, puede crear sencillamente una nueva versión del vocabulario que refleje los cambios.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-107">If you need to make changes to your vocabulary in the future, you can simply create a new version of the vocabulary that reflects the changes.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8e6b0-108">Cuando se crea una nueva versión de un vocabulario, las reglas generadas a partir de una versión anterior seguirán apuntando hacia la versión anterior. </span><span class="sxs-lookup"><span data-stu-id="8e6b0-108">When a new version of a vocabulary is created, the rules built from a previous version will still point to the previous version.</span></span>  
  
### <a name="to-create-a-vocabulary"></a><span data-ttu-id="8e6b0-109">Para crear un vocabulario.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-109">To create a vocabulary</span></span>  
  
1.  <span data-ttu-id="8e6b0-110">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-110">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
2.  <span data-ttu-id="8e6b0-111">Haga clic en el **vocabularios** carpeta y, a continuación, haga clic en **Agregar nuevo vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-111">Right-click the **Vocabularies** folder, and then click **Add New Vocabulary**.</span></span>  
  
     <span data-ttu-id="8e6b0-112">Un nuevo **vocabulario** carpeta aparece debajo de la **vocabularios** carpeta.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-112">A new **vocabulary** folder appears under the **Vocabularies** folder.</span></span>  
  
3.  <span data-ttu-id="8e6b0-113">Haga clic en el nuevo **vocabulario** carpeta y, a continuación, edite el nombre en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-113">Click the new **vocabulary** folder, and then edit the name in the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e6b0-114">Debe guardarlo todo (todas las versiones de las definiciones) antes de poder cambiar el nombre a un vocabulario o a una directiva.</span><span class="sxs-lookup"><span data-stu-id="8e6b0-114">You must save everything (all versions of the definitions) before you can rename a vocabulary or a policy.</span></span>