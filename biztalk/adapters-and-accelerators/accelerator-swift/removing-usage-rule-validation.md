---
title: Quitar la validación de la regla de uso | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deleting rules
- rules
ms.assetid: b2b0dabf-8f99-4b85-95da-6bbf3e79ad41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e5ffc3e1ca36e200055a26e8e78f341b125d8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975549"
---
# <a name="removing-usage-rule-validation"></a><span data-ttu-id="cd823-102">Quitar la validación de la regla de uso</span><span class="sxs-lookup"><span data-stu-id="cd823-102">Removing Usage Rule Validation</span></span>
<span data-ttu-id="cd823-103">Reglas de uso se definen en los estándares de SWIFT y aplica [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] directivas empresariales específicas de cada tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd823-103">Usage rules are defined in SWIFT standards and enforced by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business policies specific to each message type.</span></span> <span data-ttu-id="cd823-104">Estas reglas de uso son directrices que puede usar para proporcionar validación adicional para un campo.</span><span class="sxs-lookup"><span data-stu-id="cd823-104">These usage rules are guidelines that you can use to provide extra validation for a field.</span></span> <span data-ttu-id="cd823-105">A diferencia de las reglas de validación de red, que son obligatorias, puede elegir para que no necesite reglas de uso para un tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd823-105">Unlike network validation rules, which are mandatory, you can choose not to require usage rules for a message type.</span></span> <span data-ttu-id="cd823-106">Si es así, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd823-106">If that is the case, you can do either of the following:</span></span>  

-   <span data-ttu-id="cd823-107">Puede quitar una regla de negocios específicas que se aplica una regla de uso de la directiva de validación de tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd823-107">You can remove a specific business rule that enforces a usage rule from the message-type validation policy.</span></span>  

    > [!IMPORTANT]
    >  <span data-ttu-id="cd823-108">Si quita una regla de la directiva se quitará permanentemente.</span><span class="sxs-lookup"><span data-stu-id="cd823-108">Removing a rule from the policy will remove it permanently.</span></span>  

-   <span data-ttu-id="cd823-109">Si no desea aplicar cualquiera de las reglas de uso, puede anular la implementación de la directiva de validación para un tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="cd823-109">If you do not want to enforce any of the usage rules, you can undeploy the validation policy for a message type.</span></span>  

### <a name="to-remove-a-rule-from-a-policy"></a><span data-ttu-id="cd823-110">Para quitar una regla de una directiva</span><span class="sxs-lookup"><span data-stu-id="cd823-110">To remove a rule from a policy</span></span>  

1.  <span data-ttu-id="cd823-111">En un editor de texto como Bloc de notas, abra la directiva de validación que desee cambiar, por ejemplo, MT103_Validation_Policy en  *\<unidad\>*: Acelerador de Microsoft BizTalk para SWIFT \ProgramFiles\\<versión\> mensaje Pack\SWIFT Messages\A4SWIFT-SRG\<versión\>\Category 1\MT103.</span><span class="sxs-lookup"><span data-stu-id="cd823-111">In a text editor, such as Notepad, open the validation policy that you want to change, for example, MT103_Validation_Policy in *\<drive\>*:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MT103.</span></span>  

2.  <span data-ttu-id="cd823-112">Quite el nodo de regla que no desee y, a continuación, guardar la directiva.</span><span class="sxs-lookup"><span data-stu-id="cd823-112">Remove the rule node that you do not want, and then save the policy.</span></span>  

3.  <span data-ttu-id="cd823-113">Use el Asistente para implementación de motor de reglas de negocios para publicar e implementar la directiva.</span><span class="sxs-lookup"><span data-stu-id="cd823-113">Use the Business Rules Engine Deployment Wizard to publish and deploy the policy.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cd823-114">También puede quitar una regla de una directiva de validación mediante la creación de una copia de la directiva, quitar la regla específica y, a continuación, implementar la Directiva modificada.</span><span class="sxs-lookup"><span data-stu-id="cd823-114">You can also remove a rule from a validation policy by creating a copy of the policy, removing the specific rule, and then deploying the modified policy.</span></span> <span data-ttu-id="cd823-115">Anular la implementación de la versión anterior de la directiva.</span><span class="sxs-lookup"><span data-stu-id="cd823-115">Undeploy the previous version of the policy.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="cd823-116">En el Compositor de reglas de negocio, no se puede eliminar una regla de una directiva publicada o implementada.</span><span class="sxs-lookup"><span data-stu-id="cd823-116">In Business Rule Composer, you cannot delete a rule from a published or deployed policy.</span></span>  

### <a name="to-remove-the-policy-for-a-message-type"></a><span data-ttu-id="cd823-117">Para quitar la directiva para un tipo de mensaje</span><span class="sxs-lookup"><span data-stu-id="cd823-117">To remove the policy for a message type</span></span>  

1. <span data-ttu-id="cd823-118">Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **compositor**.</span><span class="sxs-lookup"><span data-stu-id="cd823-118">Click **Start**, point to **Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  

2. <span data-ttu-id="cd823-119">En el Explorador de directivas, busque la directiva de validación implementados para el tipo de mensaje, por ejemplo, MT103_Validation_Policy.</span><span class="sxs-lookup"><span data-stu-id="cd823-119">In Policy Explorer, find the deployed validation policy for the message type, for example, MT103_Validation_Policy.</span></span>  

3. <span data-ttu-id="cd823-120">Haga clic en la directiva, haga clic en **Undeploy**, haga clic en **eliminar**y, a continuación, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cd823-120">Right-click the policy, click **Undeploy**, click **Delete**, and then click **Yes**.</span></span>
